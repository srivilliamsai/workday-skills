# Workday Agent Skills

Agent skills that help AI coding assistants write and review Workday Extend apps, Orchestrate flows, Workday APIs, AI Gateway calls, and Workday Developer Copilot prompts. Samples come from the Workday-maintained catalog only. The rules target the mistakes agents actually make: wrong field types, invented routes, secrets in source, and orchestration files rewritten into a simplified shape.

The skills use the [Agent Skills](https://agentskills.io/home) format, so they work with Claude Code, Codex, Gemini, Cursor, and more.

## Skills

| Skill | Use when |
| --- | --- |
| `workday` | Starting an app, or the task touches more than one artifact |
| `workday-extend` | `.amd`, `.smd`, business objects, security domains, business processes, the app manifest |
| `workday-pmd` | `.pmd`, scripts, charts, localization properties |
| `workday-home-cards` | `.card`, `.carddefinition`, `.cardtenantsetting` |
| `workday-orchestrate` | `.orchestration`, `.suborchestration` |
| `workday-apis` | `.graphquery`, `.wqlquery`, REST, SOAP |
| `workday-ai-gateway` | AI Gateway document intelligence, WQL generation, or AWS starter calls |
| `workday-developer-copilot` | Prompts for the product Workday Developer Copilot |

## Installing

Install every skill for all projects:

```bash
npx skills add srivilliamsai/workday-skills -g -y --skill '*'
```

Install one skill:

```bash
npx skills add srivilliamsai/workday-skills -g -y --skill workday-extend
```

`npx` asks which agents to install into unless you pass `-y`. Use `-g` so the skills are available in every project. Omit `-g` to install into the current project only.

If you get `npx: command not found`, Node is not installed:

```bash
brew install node
```

If that fails, [install Homebrew](https://brew.sh) first.

Claude Code can install the plugin from this folder:

```
/plugin install workday-skills@workday-skills
```

You can also keep this folder where it is and symlink one skill at a time:

```bash
ln -sfn "$HOME/workday-skills/skills/workday-extend" "$HOME/.agents/skills/workday-extend"
```

## Using a skill

In Claude Code:

> /workday-extend

In Codex:

> $workday-extend

Add a focus when you want a partial review. For example, `/workday-pmd Check the grid bindings` or `$workday-apis Focus on WQL`.

Natural language works too:

> Use the Workday Extend skill to review this business object.

## License

These skills are available under the [MIT License](LICENSE), which permits commercial use, modification, distribution, and private use.
