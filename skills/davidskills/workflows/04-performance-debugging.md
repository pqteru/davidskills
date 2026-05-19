# Performance & Debugging Workflow

Use for **measured** regressions, latency, or resource bottlenecks in services or apps under this project.

## Rules

1. Establish a **numeric baseline** before behavioral changes (P50/P95 latency, throughput, CPU, memory as relevant).
2. Prefer **profiling evidence** over guesses—use stack-appropriate tools (runtime profilers, APM, framework timings, structured logs). Never enable heavy debug hooks in production without explicit approval.
3. Tie conclusions to **hot paths** in code and to **documented** constraints in `architecture.md` / `task.md`.
4. If results imply an **architecture boundary change**, return to **Planning** before large implementation shifts.

Persist only durable findings and decisions back into SkillDocs.
