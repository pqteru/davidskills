---
name: davidskills-quality-swift
description: Swift-specific quality rules for DavidSkills. Load alongside davidskills-quality when Swift, SwiftUI, iOS, macOS, Xcode, Swift Package, or App Intents source changed. Covers project tooling, concurrency, memory, SwiftUI (declarative UI, unidirectional State/Action/reducer/side effects), security, tests.
---

# DavidSkills: Quality — Swift

Load only when `.swift`, `Package.swift`, `.xcodeproj`, `.xcworkspace`, `.pbxproj`, `.storyboard`, `.xib`, `.entitlements`, or related Apple platform files are in scope. Confirm `../davidskills-quality/SKILL.md` was already followed for neutral checks.

## Load order

1. Read `../davidskills/workflows/quality-swift.md`
2. Apply checks to all touched Swift and Apple platform files

## Required behavior

- Fail the gate on main-thread blocking in async/UI paths, unsafe force unwraps in non-test code, unsafely detached concurrency, retained self cycles in escaping closures, secrets in committed Apple config, or missing runnable build/test evidence per the workflow examples.
