# Zacky Skills

A practical, editable agent skill pack for clarifying work, writing specifications, breaking work into tickets, implementing changes, and reviewing the result.

This is the 13-skill pack taught in Zacky's Agentic Skill Work Flow. It is adapted from [Matt Pocock’s open-source skills](https://github.com/mattpocock/skills), with the original names, supporting files, and MIT notices preserved. The setup skill is named `setup-zacky-skills` in this distribution.

## Install the workflow pack

Open a terminal in the project where you want the skills. You need Node.js 22.20 or later and Git.

```sh
npx skills@latest add MGT-TECHWARE/zacky-skills --skill '*'
```

Choose your coding agent when the installer asks. This installs into the current project by default. Restart or refresh your agent’s skill list afterward.

Then select `/setup-zacky-skills` in your coding agent once for that project. It configures where specifications and tickets live, the triage labels, and the project’s domain documentation. Invocation syntax depends on the agent; use its skill picker when slash commands are unavailable.

Prefer to choose individual skills interactively?

```sh
npx skills@latest add MGT-TECHWARE/zacky-skills
```

## Choose your agent explicitly

```sh
# Codex, in this project
npx skills@latest add MGT-TECHWARE/zacky-skills --skill '*' --agent codex

# Claude Code, in this project
npx skills@latest add MGT-TECHWARE/zacky-skills --skill '*' --agent claude-code

# Cursor, in this project
npx skills@latest add MGT-TECHWARE/zacky-skills --skill '*' --agent cursor
```

The installer also supports `--global` for user-wide installation. Keep one installation route for each skill so the agent does not discover duplicate copies from this pack and upstream.

## What is included

| Skill | Use it for |
| --- | --- |
| [`setup-zacky-skills`](skills/setup-zacky-skills/SKILL.md) | Configure a project’s tracker and documentation conventions |
| [`grill-with-docs`](skills/grill-with-docs/SKILL.md) | Clarify a feature with repository context |
| [`to-spec`](skills/to-spec/SKILL.md) | Save an agreed specification |
| [`to-tickets`](skills/to-tickets/SKILL.md) | Slice a plan into complete, demonstrable changes |
| [`implement`](skills/implement/SKILL.md) | Build one ready ticket |
| [`code-review`](skills/code-review/SKILL.md) | Review a diff against standards and the request |
| [`implement-spec`](skills/implement-spec/SKILL.md) | Coordinate a whole approved ticket graph |
| [`tdd`](skills/tdd/SKILL.md) | Test observable behavior one step at a time |
| [`grill-me`](skills/grill-me/SKILL.md) | Stress-test an idea or decision |
| [`grilling`](skills/grilling/SKILL.md) | Supply the interview discipline used by other skills |
| [`domain-modeling`](skills/domain-modeling/SKILL.md) | Resolve vocabulary, relationships, and decisions |
| [`codebase-design`](skills/codebase-design/SKILL.md) | Discuss module boundaries and deep interfaces |
| [`research`](skills/research/SKILL.md) | Investigate a focused question against primary sources |

For a larger feature, the main flow is:

```text
/grill-with-docs → /to-spec → /to-tickets → /implement → /code-review
```

Small, clear work can start at `/implement`. `implement-spec` needs a harness with subagents and worktrees. `implement` commits on the current branch unless you instruct it otherwise. Installation copies instructions; it does not run the workflow or deploy your project.

## Install a smaller selection

You can request skills by their actual names:

```sh
npx skills@latest add MGT-TECHWARE/zacky-skills --skill to-tickets
```

Some skills call other skills in this pack. Install the complete pack for the guided workflow, or include the helpers required by the skills you choose. Installing one wrapper does not automatically install its dependencies.

Preview the catalog without installing:

```sh
npx skills@latest add MGT-TECHWARE/zacky-skills --list
```

## Updates

```sh
npx skills@latest check
npx skills@latest update
```

Updates bring installed editable copies to the latest version offered by their recorded source. Re-run `add` to select newly added skills. Review local edits before updating. This repository is maintained independently; it does not automatically mirror every upstream change.

## Source and license

Original upstream skills © 2026 Matt Pocock, distributed under the MIT License. The full notice is in [LICENSE](LICENSE), [THIRD-PARTY-LICENSE.txt](THIRD-PARTY-LICENSE.txt), and every skill folder.

Zacky branding identifies this distribution and its learning material. It does not claim original authorship of the upstream skills or an affiliation with Matt Pocock. The source snapshot and file hashes are recorded in [SOURCE-MANIFEST.json](SOURCE-MANIFEST.json). This distribution preserves the workflow’s permission, review, and testing instructions.

Installer reference: [vercel-labs/skills](https://github.com/vercel-labs/skills). Learning hub: [Zacky.Viriot](https://zacky-creator-demo.pages.dev).
