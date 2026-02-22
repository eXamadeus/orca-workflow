# OpenCode Agents

This directory contains configuration for OpenCode custom agents.

## Directory Structure

- `agents/` - Active agents (loaded by OpenCode)
- `skills/` - Active skills (loaded by OpenCode)
- `prompts/` - Active prompt templates (loaded by OpenCode)
- `plans/` - Folder that can be used to store plans
- `examples/` - Example agent templates
  - `examples/agents/` - Example agent configurations
  - `examples/skills/` - Example skill configurations
  - `examples/prompts/` - Example prompt templates


## Activating Agents

To activate an agent, copy it from `examples/agents/` to `agents/`:

```bash
cp .opencode/examples/agents/reviewer.md .opencode/agents/
```

Agents in the `agents/` directory will be automatically loaded by OpenCode.

## Creating Custom Agents/Prompts

You can create your own agents, skills, or prompts by adding `.md` or `.txt` files to the respective top level
directory. See the examples for the expected formats.

## Creating Custom Skills

Skills are a little different and require a special file naming convention. Each skill is called `SKILL.md` and must be
placed in a directory named after the skill. For example, to create a skill called `analyzer`, you would create the
following structure:

```
.opencode/
  skills/
    analyzer/
      SKILL.md
```

and `SKILL.md` would look something like this:

```markdown
---
name: analyzer
description: You analyze stuff
---

# How to analyze

...
```

For a full example see the [rspec-structure example skill](./examples/skills/rspec-structure/SKILL.md).

## Utilizing Custom Prompts

The `prompts/` directory can be used to store custom prompt templates. See the examples for the expected format.

If you wanted to update the default `Plan` agent system prompt to use what's in `prompts/planner.md`, you can add the following to your `opencode.json`:

```json
{
  // ...
  "agent": {
    "plan": {
      "prompt": "{file:./prompts/planner.md}"
    }
  }
}
```
