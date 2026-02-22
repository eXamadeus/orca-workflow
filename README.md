# Orca Workflow

A portable, shareable configuration for AI-assisted development workflows. Designed to work with [OpenCode](https://opencode.ai) and [OpenSpec](https://github.com/eXamadeus/openspec).

## What's Included

### `.opencode/` — Workflow Engine

- **`opencode.json`** — Main configuration wiring up the planner and builder agent prompts
- **`prompts/planner.md`** — Plan mode system prompt enforcing the Propose/Implement/Verify protocol. Plans are read-only, structured, and gated by user approval at each step.
- **`prompts/builder.md`** — Build mode system prompt for executing plans. Creates one TODO per step, follows strict dependency chains, and stops on failures.
- **`README.md`** — Documents the OpenCode directory structure and conventions

### `openspec/` — Spec Governance

- **`config.yaml`** — Project constitution (RFC 2119 compliance, value-centric specifications), artifact definitions, and rules for specs, proposals, and tasks
- **`specs/spec-governance/spec.md`** — Meta-specification defining how specifications are written: value-centric philosophy, no internal implementation references, product domain organization, testable scenarios

## Usage

Copy the `.opencode/` and `openspec/` directories into your project root. Adjust `opencode.json` to fit your project (model, MCP servers, permissions).

OpenSpec skills and commands are installed separately via the OpenSpec CLI.
