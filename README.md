# Adaptive Instruction — Archon Workflow Pack

A reusable, evidence-led instructional-writing workflow for [Archon](https://github.com/coleam00/Archon). The pipeline researches a section, establishes instructional boundaries, develops intermediate/advanced teaching, runs two independent three-iteration writer/editor review loops, synthesizes a complete manuscript and pauses for **author approval**. It **never installs or commits lesson content**.

## Install

Requires Archon 0.13+ and an authenticated **Codex provider**. In your Archon environment, install/enable the provider and verify it is available (`archon plugin list`). Then:

```bash
archon plugin add TBY86/archon-adaptive-instruction-workflow
```

Run inside a Git project containing instructional source files and any authorial style guidance:

```bash
archon workflow run TBY86/adaptive-instruction:adaptive-instruction "Develop intermediate and advanced instruction from the approved beginner material in section X; preserve the originals and respect later-section boundaries."
```

To review without executing agents, use the workflow's `--dry-run` option as supported by your installed Archon version. The Archon CLI will pause at an author approval wait; respond through your ordinary Archon attention workflow.

## What the stages do

1. **Inspect** the available baseline and author directives.
2. **Hierarchy** plans genuine intermediate and advanced learning outcomes.
3. **Research + boundaries** independently collect evidence and protect future lessons.
4. **Qualify evidence** distinguishes documentation, inference and open gaps.
5. **Editorial A** uses an optional voice MCP and up to three writer/editor rounds.
6. **Editorial B** uses an optional prose MCP and up to three writer/editor rounds.
7. **Assemble** synthesizes both approved editorial outputs into one manuscript.
8. **Author review** approves or rejects. No source files are written at either outcome.

The editorial loops deliberately **fail** after three unsuccessful review rounds instead of silently accepting unapproved prose. Both branches run under Codex by default; edit `provider` assignments after setting up another registered Archon provider.

## Optional MCP integrations

The workflow references optional **project-local** files; Archon skips absent optional MCP configurations. You must supply and review your own trusted servers under your target project:

| Path | Purpose |
| --- | --- |
| `.archon/mcp/adaptive-research.json` | Trusted web or scholarly research tools |
| `.archon/mcp/adaptive-voice.json` | Authorial style/voice review |
| `.archon/mcp/adaptive-prose.json` | Prose and editorial analysis |

An MCP config can be a JSON object mapping server names to command/args/env (or use `mcpServers`). **Never commit credentials, API keys, or personal writing samples without permission.** Tool identities and configuration are entirely the adopter's responsibility.

## Adapting the pack

Place authoritative source text and style constraints in your project. Replace `provider: codex` with another supported, installed provider if desired. Read the YAML and verify your prompt conventions and source policy before running: *original evidence*, *verified scholarly interpretation*, *authorial inference* and *theological application* should not be conflated. Actual manuscript integration belongs to a separately reviewed process.

This package is an **independently generalized community edition**, not a verbatim copy of the workbook-specific production YAML. It preserves the pipeline's research → dual editorial paths → synthesis → approval architecture, while omitting private documents, specialized MCP tools, and project-specific prompts.

**Not included in this initial release:** the planned Claude/OpenAI dual independent author proposal stage, four cross-editorial paths, deterministic provider alternation, and iterative free-form author feedback. Those are in the development roadmap and must be tested before being claimed as available.

## Maintenance / synchronization

The privately tailored workflow remains version-controlled in its own project. Public pack releases are adapted and validated independently; the two repositories **do not share Git histories**. A synchronized release means each approved change is checked against both artifacts, validated, and published separately. Do not configure a second push remote on the private workbook repository.

## Security and limitations

AI and MCP tools may have access to the current project. Inspect workflow prompts, provider permissions and MCP servers before running. Source research must be checked at passage level; a plausible citation or successful web fetch does not itself verify a claim. No automated production publishing is performed.

## License

MIT. See [LICENSE](LICENSE).
