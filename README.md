# Concept to Action Coach

[简体中文](README.zh-CN.md) | [Skill instructions](SKILL.md) | [Maintainer: kevin-12-ou](https://github.com/kevin-12-ou)

**An AI agent skill for explaining technical concepts to beginners and turning understanding into a small, verifiable action.**

Definitions alone do not explain when a tool is useful. A beginner can repeat “agent” or “workflow” and still have no idea what to try next.

This is an **Agent Skill: instructions and reference material for an AI assistant**, not a hosted service or an autonomous program. The package contains no installation hooks, application runtime, models, background services, or credentials; its Python script is only for development-time package validation. The assistant still operates under its host permissions and the user's authorization.

## When to use it

- Start from the learner’s existing experience and actual point of confusion.
- Explain the problem a concept addresses, its responsibilities, costs, and limits.
- Distinguish nearby ideas through inputs, outputs, state, decisions, and feedback.
- End with a small experiment, an observable result, and a way to check it.

## Install

Use Git and an assistant that supports Agent Skills. The optional Skills CLI below also requires Node.js/npm and is a separate executable tool to review before running. This skill itself needs no API key, database, or paid account; your chosen AI assistant may have its own costs.

```sh
npx skills add kevin-12-ou/concept-to-action-coach --skill concept-to-action-coach
```

Choose the agent and scope in the installer. For a project-local Codex installation, with copied files rather than symlinks:

```sh
npx skills add kevin-12-ou/concept-to-action-coach --skill concept-to-action-coach --agent codex --copy
```

Manual option: copy the complete repository into a skill directory named `concept-to-action-coach`, such as `.agents/skills/concept-to-action-coach/`, where supported by your assistant. Keep `SKILL.md` and its referenced files together; follow your client's skill-directory documentation.

## Example prompts

```text
Use $concept-to-action-coach. I use an AI coding assistant but confuse skills, workflows, and agents. Explain the differences using one small coding task, then give me a reversible first experiment.
```

```text
用 $concept-to-action-coach。我会用 AI 改代码，但分不清 Skill、Workflow 和 Agent。用同一个小任务解释，再带我做一个可回退的小实验。
```

```text
Use $concept-to-action-coach. I understand what an API is in theory, but cannot use one. Find the gap in my understanding and guide one public, read-only request.
```

```text
用 $concept-to-action-coach。我大概懂 API 的定义，但不会用。帮我找到理解断点，再做一次不需要密钥的只读请求。
```

Explicitly naming the skill helps make intent clear. Automatic selection depends on the model and client and is not guaranteed. The package follows the [Agent Skills specification](https://agentskills.io/specification); clients such as Codex and Claude Code can read this format, but equivalent behavior across every client is not claimed. Core instructions are primarily Chinese; this English README provides discovery and usage context.

## Boundaries and data

Not a general coding autopilot or a fixed lecture template. Simple facts can stay brief; a request to implement directly should not be turned into a compulsory lesson.

No private project history is bundled. File access, network requests, commands, and edits depend on the task and the assistant's tools. A text skill is not an isolation boundary or a mandatory security interceptor.

## Maintenance and feedback

For Skills CLI installs, `npx skills check` checks for updates and `npx skills update` updates installed skills. Review changes first. Disable the skill in your client, or move its installed directory out of discovery, to stop using it. Back up any personal additions before updating or removing it.

Report a sanitized example in [Issues](https://github.com/kevin-12-ou/concept-to-action-coach/issues). See [CONTRIBUTING.md](CONTRIBUTING.md) and [VALIDATION.md](VALIDATION.md) for contribution and validation boundaries.

## Related skills by kevin-12-ou

- [Don't Repeat Yourself](https://github.com/kevin-12-ou/dont-repeat-yourself) — An AI agent skill for saving verified coding solutions as searchable recipes and adapting them to future projects.
- [Deploy Onboarding Guide](https://github.com/kevin-12-ou/deploy-onboarding-guide) — A Chinese-first AI agent skill for assessing open-source software before installation and explaining setup, permissions, costs, and first use.
- [Release Migration Parity](https://github.com/kevin-12-ou/release-migration-parity) — An AI agent skill for preserving accepted UI, behavior, and data semantics when releasing an app or migrating it to another platform.

Maintained by [kevin-12-ou](https://github.com/kevin-12-ou). Developed from personal AI-assisted workflows. Licensed under [MIT](LICENSE); see [NOTICE.md](NOTICE.md) for provenance.
