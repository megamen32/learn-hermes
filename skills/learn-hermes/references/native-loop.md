# Optional host integration: Hermes native loop

Agent Plugins 1.0 does not define background hooks, so this file is informative host-integration guidance, not portable plugin behavior.

Hermes's native self-improvement boundary is:

1. Track review cadence during the foreground session.
2. Deliver the user-visible response first.
3. Only after a non-empty, uninterrupted response, fork an isolated review turn.
4. Give that review only memory/skill-management capabilities.
5. Disable persistence of the review harness turn, recursive reviews, parent-session compression, external memory-plugin side effects, and interactive approvals.
6. Apply fail-closed ownership/read-before-write guards to autonomous skill mutations.
7. Surface a short summary of what the review changed.

Hermes defaults observed in the extracted source:

- Memory review cadence: every 10 eligible user turns.
- Skill review cadence: every 10 tool-calling iterations.
- Direct memory or skill writes reset the corresponding counter.

A host implementing this loop should treat the portable `learn-hermes` skill as the policy/instructions layer, not as a claim that the Agent Plugins package itself schedules background work.
