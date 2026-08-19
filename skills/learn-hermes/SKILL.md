---
name: learn-hermes
description: Learn durable skills from completed work using Hermes policy.
---

# Learn Hermes

Turn a completed workflow, correction, useful technique, source set, or explicit learning request into durable reusable skill knowledge. Use Hermes's native self-improvement policy as the curation standard, while staying portable across Agent-Skills-compatible hosts.

This skill does **not** claim that Agent Plugins 1.0 can schedule background reviews. The portable plugin format standardizes skills and MCP servers only. If the host has a post-turn hook, use the integration contract in [references/native-loop.md](references/native-loop.md); otherwise invoke this skill explicitly after meaningful work or when the user asks to learn/refine.

## When to Use

Use this skill when any of these signals appears:

- The user says “learn this”, “save this workflow”, “make this reusable”, “refine your skills”, or equivalent.
- The user corrects style, tone, format, verbosity, workflow, or sequencing in a way that should apply to future work of the same class.
- A non-trivial fix, workaround, debugging path, research method, or tool-use pattern proved useful.
- A skill used during the session was incomplete, wrong, or outdated.
- A host-provided post-turn review asks whether durable learning should be persisted.

Do not invoke merely because a task happened. One-off narratives and transient setup failures are not durable learning.

## Procedure

1. **Identify the durable signal.** Separate what will still be useful later from session state. Read [references/review-policy.md](references/review-policy.md) when deciding whether something deserves persistence.
2. **Gather every named source.** Read all files, directories, URLs, notes, and relevant conversation context the user identified. Treat requirements that follow a source path or URL as load-bearing constraints, not incidental prose.
3. **Choose the narrowest durable action.** Prefer, in order:
   1. Patch the currently relevant editable skill.
   2. Patch an existing class-level umbrella skill.
   3. Add a focused reference, template, or deterministic script under an existing umbrella and link it from `SKILL.md`.
   4. Create one new class-level umbrella skill only when no existing skill covers the class.
4. **Respect ownership.** Do not autonomously edit bundled, hub-installed, external, pinned, protected, or user-owned skills. Read the exact current target before any autonomous edit. If provenance is uncertain, fail closed. See [references/ownership-guards.md](references/ownership-guards.md).
5. **Author for retrieval.** Follow [references/authoring-standards.md](references/authoring-standards.md). Prefer exact commands, APIs, config keys, and verified procedures. Do not invent capabilities or persist unresolved failures as best practice.
6. **Persist with the host's skill-management mechanism.** Use the native skill tool if available. If the host only provides filesystem access, edit the target skill directly only when ownership is clear and the requested operation is permitted.
7. **Verify.** Re-read the resulting `SKILL.md`, confirm frontmatter and relative references are valid, and run any bundled deterministic check if one exists.
8. **Report succinctly.** State the skill updated/created and the durable learning captured. If there is genuinely nothing durable to save, say exactly: `Nothing to save.`

## Explicit Learn Mode

When the user explicitly asks to learn from a source or from “what we just did”:

- Gather **all** sources they named.
- Honor every scope/focus/exclusion requirement.
- Produce **one** reusable skill, not a router/index and not one skill per session artifact.
- Put non-trivial deterministic automation in `scripts/`, deeper knowledge in `references/`, and starter artifacts in `assets/` or the host's supported template location.
- If the user supplied no explicit source, use the completed conversation workflow as the source.

## Explicit Refine Mode

When the user asks to refine/self-improve without naming a source, review the completed conversation for both:

- **User preference signals:** durable ways the agent should perform this class of task for this user.
- **Technique signals:** proven methods, fixes, workflows, and missing skill knowledge.

Apply the same ownership and durability rules as explicit learn mode.

## Never Learn These as Durable Rules

- Missing binaries, unconfigured credentials, fresh-install paths, or other environment-dependent failures.
- Negative claims that a tool or feature “does not work” because one session failed.
- Transient errors that later succeeded; capture the successful retry/fix pattern instead.
- One-off task narratives such as today's PR, market snapshot, or temporary incident.
- Unresolved failed attempts presented as a reliable workflow.

## Verification

Before finishing, confirm:

- The learning is class-level and reusable.
- The chosen target is editable under the ownership rules.
- Existing targets were read before mutation.
- The skill name is lowercase kebab-case and matches its directory.
- The description is concise and routes to the intended use case.
- Referenced files exist and use relative paths.
- The saved procedure is based on observed or authoritative facts, not guesses.
