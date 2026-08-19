# learn-hermes

`learn-hermes` **v1.0.0** is an **Agent Plugins 1.0.0** skill plugin that packages the durable-learning policy extracted from Hermes Agent's native self-improvement loop.

It gives compatible agents a portable way to:

- learn one reusable skill from files, URLs, notes, or a completed workflow;
- refine existing skill knowledge after user corrections or useful techniques;
- avoid learning transient failures as permanent constraints;
- apply Hermes-style ownership and read-before-write guards to autonomous skill maintenance.

## Why this is a skill, not a background hook

Agent Plugins 1.0 standardizes two component types: Agent Skills and MCP servers. Background hooks are outside the portable v1 format. Accordingly, this repo ships the learning/refinement policy as `skills/learn-hermes/SKILL.md` and documents Hermes's native post-turn integration contract in `references/native-loop.md` for hosts that support their own hook mechanism.

## Conformance

The portable package follows Agent Plugins Specification 1.0.0:

- root `plugin.json` targets `https://agent-plugins.org/schemas/1.0.0/plugin.schema.json`;
- the reusable component is discovered at `skills/learn-hermes/SKILL.md`;
- no non-standard hook fields are added to the portable manifest;
- Hermes post-turn scheduling remains optional host integration documented under `references/native-loop.md`.

## Layout

```text
plugin.json
skills/
  learn-hermes/
    SKILL.md
    references/
      authoring-standards.md
      native-loop.md
      ownership-guards.md
      review-policy.md
```

## Source provenance

The policy was extracted from Nous Research Hermes Agent revision `fe3a1cad6e5db98348a06ec0af8ae3c7b7527d05` and repackaged as a runtime-neutral Agent Plugin. The original Hermes checkout carried the MIT license.

Key upstream source areas used for the extraction:

- `agent/background_review.py`
- `agent/learn_prompt.py`
- `agent/turn_context.py`
- `agent/conversation_loop.py`
- `agent/turn_finalizer.py`
- `agent/tool_executor.py`
- `tools/skill_manager_tool.py`
- `run_agent.py`

## Install

Install this repository as an Agent Plugins-compatible plugin, or add `megamen32/megamen32-marketplace` and install `learn-hermes` from that catalog.
