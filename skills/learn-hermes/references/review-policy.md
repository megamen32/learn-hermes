# Hermes-derived review policy

Use these durable-signal rules when deciding whether to persist learning.

## Strong signals

Any one of these is enough to justify a skill update when the learning is durable:

- User correction to style, tone, format, legibility, verbosity, workflow, approach, or sequence.
- A non-trivial technique, fix, workaround, debugging path, or tool-use pattern that worked.
- A loaded/consulted skill proved wrong, incomplete, or stale.

Prefer changing the skill that governs the class of task over storing a narrow session note. User preferences about *how to do this class of work* belong in the relevant skill, not only in user memory.

## Preferred placement

1. Update a relevant currently used editable skill.
2. Update an existing class-level umbrella.
3. Add a support file to an umbrella and link it from `SKILL.md`.
4. Create a new class-level umbrella only when no existing skill fits.

New skill names should describe a reusable class of work, never a PR number, error string, feature codename, or today-only task.

## Do not persist

- Environment-dependent failures such as missing packages, paths, credentials, or install state.
- Broad negative claims about tools/features derived from a failed session.
- Errors that were transient and resolved; keep the successful repair/retry pattern instead.
- One-off task narratives.
- Unresolved failed attempts masquerading as validated guidance.

If a setup problem produced a verified fix, capture the fix under setup/troubleshooting knowledge rather than a permanent “tool is broken” rule.

`Nothing to save.` is valid when the session contains no durable signal.
