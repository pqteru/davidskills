# Quality Workflow — Swift

Apply after `quality-neutral.md`. Fix failures before writing back to `task.md`.

## 1. Project tooling

| Bad | Good |
|-----|------|
| Editing generated Xcode project files without checking diffs | Review `.pbxproj` changes for accidental file removals, duplicate references, or target membership drift |
| Adding packages without lockfile awareness | Keep `Package.resolved` behavior consistent with the repo; commit it when the project already does |
| Running ad-hoc commands only | Prefer project scripts or documented `xcodebuild`, `swift build`, `swift test`, or XcodeBuildMCP commands |

## 2. Swift types and safety

- Avoid `!` force unwraps and forced casts in non-test code unless guarded by an invariant documented next to the use.
- Public APIs should expose clear parameter and return types; avoid `Any` except at Objective-C, JSON, plugin, or framework boundaries.
- Model invalid states explicitly with enums, optionals, throwing initializers, or typed errors rather than sentinel strings.
- Keep access control narrow: prefer `private` / `fileprivate` for implementation details and `internal` unless API exposure is required.

## 3. Concurrency and main actor isolation

| Bad | Good |
|-----|------|
| Blocking work on `MainActor` or UI callbacks | Move file, network, parsing, and CPU-heavy work off the main actor |
| `Task.detached` for ordinary UI work | Use structured tasks, explicit actor isolation, or dependency-owned async APIs |
| Updating UI state from background contexts | Mark UI models/views `@MainActor` or hop with `await MainActor.run` when required |
| Ignoring cancellation | Check `Task.isCancelled`, propagate cancellation, and clean up resources |

## 4. SwiftUI lifecycle and state

Act as an iOS SwiftUI engineer: **declarative UI** plus **unidirectional data flow**. Define these layers before wiring views:

| Layer | Responsibility |
|-------|----------------|
| **State** | Every representable screen state (loading, content, empty, error, etc.) |
| **Action** | User gestures and system events (tap, refresh, timer tick, task completion) |
| **Reducer / transition** | Pure mapping from `(State, Action) → State` (or equivalent store API) |
| **Side effects** | API calls, timers, navigation, analytics—owned outside `body`, driven by state or actions |
| **View** | Renders from **State** only; dispatches **Action**; no embedded business rules |

### Constraints (fail the gate when violated)

- **Views do not call APIs** — network and persistence live in effect handlers / stores / coordinators, not in `View` types.
- **Views do not own business state** — no duplicated domain flags in the view layer; one source of truth in the store or parent feature state.
- **No mutually exclusive booleans** — e.g. `isLoading && hasError` must be impossible; model exclusivity with an enum (or equivalent sum type).
- **Invalid states impossible** — prefer enums with associated values over parallel optionals or independent flags.
- **Async results flow through Action** — task completion, failures, and pagination must dispatch an action; the reducer (or store) updates **State**; never assign business fields from a `.task` or callback directly on the view.

### Implementation habits

- Keep side effects out of `body`; use `.task`, `.onAppear`, actions, or injected services with clear lifecycle ownership.
- Choose property wrappers by ownership: `@State` for local **UI-only** state (focus, sheet presentation tied to the widget), `@Binding` for parent-owned state, `@StateObject` / `@Observable` ownership per project baseline, and `@Environment` for shared dependencies.
- Avoid unstable identity in `ForEach`; use durable IDs rather than indices when rows can move, insert, or delete.
- Do not hide navigation, persistence, or network work inside computed view helpers.

## 5. Memory and resource management

- Capture `self` weakly in escaping closures when the owner can outlive the operation or the closure is retained by the owner.
- In async tasks owned by views or objects, define cancellation behavior and avoid retaining view models indefinitely.
- Close file handles, invalidate timers, remove observers, and cancel Combine subscriptions or tasks at the correct lifecycle boundary.
- Avoid retain cycles between delegates, coordinators, view models, publishers, and closures.

## 6. Security and privacy

| Bad | Good |
|-----|------|
| Secrets in `.xcconfig`, `.entitlements`, plist, Swift source, or committed sample configs | Use build settings, environment injection, CI secrets, Keychain, or documented local-only config |
| Logging tokens, PII, request bodies, or Keychain values | Redact sensitive fields and use privacy-aware logging |
| String-built SQL, predicates, JavaScript, or shell commands with user input | Use bound parameters, typed APIs, validated allowlists, or safe framework APIs |
| Broad entitlements without feature need | Keep entitlements minimal and aligned with target capabilities |

## 7. Error handling and observability

- Prefer typed or domain-specific errors where callers need recovery decisions.
- Do not swallow errors with `try?` unless the ignored failure is intentional and harmless.
- Avoid `fatalError`, `preconditionFailure`, and `assertionFailure` in runtime paths unless crashing is the explicit contract.
- Use `Logger` / `os_log` or the project's logging abstraction; include correlation context for async flows where available.

## 8. Tests and verification

Run the project's established verification command. Depending on the repo, acceptable evidence may include:

- `swift test`
- `xcodebuild test ...`
- XcodeBuildMCP `build_sim`, `test_sim`, or `build_run_sim`
- Project scripts such as `./utils/run_ios_tests.sh`

Fail the gate when changed behavior lacks relevant unit, integration, UI, or snapshot coverage required by `task.md` / `design.md`. Record exact command and outcome in `verification.md` when required.
