# DigiMinds Spec Kit

A Spec Kit workspace snapshot under `digiminds/`. The checked tree contains Claude Code skill instructions, Spec Kit workflow files, templates, integration metadata, and an optional Git extension. File presence does not prove that the host discovers or runs these workflows.

## Repository map

| Area | Verified paths |
|---|---|
| Claude Code instructions | `digiminds/.claude/skills/` |
| Spec Kit workflow and registry | `digiminds/.specify/workflows/` |
| Templates and project constitution | `digiminds/.specify/templates/` and `digiminds/.specify/memory/constitution.md` |
| Optional Git extension | [Extension guide](digiminds/.specify/extensions/git/README.md), manifest, commands, and shell scripts |
| Root context and security | [CLAUDE.md](digiminds/CLAUDE.md) and [SECURITY.md](SECURITY.md) |

The extension manifest names the [GitHub Spec Kit repository](https://github.com/github/spec-kit) as its repository. Whether this checkout matches upstream or works with a particular host version was not verified.

## Status and limits

The recursive tree on `docs/spec-kit-scope-and-verification` was checked on 2026-10-02. The root has no package manifest or documented root install command. No tests or workflow execution were verified. Review the extension configuration and scripts before enabling hooks: its declared workflow includes optional Git commit operations.

See [CONTENT_REVIEW.md](CONTENT_REVIEW.md) for the path corrections and review scope. See [SECURITY.md](SECURITY.md) before using the command or extension examples.
