# Skill authoring standards

These standards are adapted from Hermes's `/learn` authoring rules while remaining compatible with the Agent Skills format.

## Frontmatter

Required by Agent Skills:

- `name`: lowercase letters, numbers, and hyphens; <=64 characters; no leading/trailing hyphen; match the skill directory.
- `description`: concise, non-empty description of capability and activation context.

Hermes convention for newly authored skills:

- Prefer a one-sentence description <=60 characters so compact skill indexes do not truncate routing text.
- Use class-level names, not one-session artifacts.
- Do not derive author identity from OS usernames, git config, hostnames, or other ambient machine data.

## Body

A useful order is:

1. Human title and 2–3 sentence scope.
2. When to Use.
3. Prerequisites.
4. How to Run.
5. Quick Reference.
6. Procedure.
7. Pitfalls.
8. Verification.

Omit empty sections. Keep `SKILL.md` scannable and move deep material to relative references.

## Accuracy

- Prefer exact commands, endpoints, signatures, paths, and config keys observed in authoritative sources.
- Never invent flags or APIs.
- Do not convert an unresolved failure into recommended procedure.
- Put deterministic reusable automation in `scripts/` rather than asking future agents to retype it.
- Keep references focused; do not mirror entire upstream documentation.
