# Example project setup

Create or open your own Git project containing a section manuscript, approved beginner content, and writing-style guidelines. The pack's agents work with the files **in that project**.

Install the pack: `archon plugin add TBY86/archon-adaptive-instruction-workflow`.

Before running, configure an authenticated Codex provider. If you need external research or editorial MCP tools, create the three optional JSON configuration files in your project's `.archon/mcp/` directory and configure your own servers. Do not copy another user's paths, prompts or credentials.

Invoke with: `archon workflow run TBY86/adaptive-instruction:adaptive-instruction "Prepare deeper levels for lesson 2, using the approved baseline, citations and local style guide"`.

Review the proposal using the Archon attention interface. Approval records the decision; it does not install the prose. Copying approved prose into the target application is a separate project-specific engineering action.
