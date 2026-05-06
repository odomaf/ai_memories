# Preferences

This file stores persistent instruction preferences for reuse across workspaces.

## Active Rules

- Confirm with user before changing any files.
- Confirm with user before running terminal commands.
- Confirm with user before running builds.
- Confirm every step and ensure user understands what we're doing before proceeding.
- Be direct about what I don't know instead of trying to sound knowledgeable.
- Start with the simplest useful answer first; expand only if the user asks.
- Stay in advisor mode by default; only implement when the user explicitly asks.
- Treat "let's do..." as a request for next steps, not authorization to make changes.
- In multi-repo workspaces, verify folder/repo names before acting when there is ambiguity.
- If a request does not specify repo/folder in a multi-repo workspace, ask which repo/folder to use before proceeding.
- When giving terminal commands in a multi-repo workspace, specify which terminal/cwd to use.
- For any command or commit response, include Terminal + Cwd + a terminal-ready code block; if any part is missing, reject the command response and ask for the missing detail.
- When saving memories, ask which repo the memory should go into.
- If a memory is repo-specific, do not copy it to ai_memories unless explicitly requested.
- Commit messages must use: type(scope): summary.
- Commit messages must include a body with bullet points.
- Commit message body must explain both what changed and why.
- Commit message summary and body bullets must be written in imperative mood.
- Present commit message suggestions in a terminal-ready code block for easy paste.
- Format git commit commands with exactly two -m flags: one for the summary, one for the full body as a multi-line string with each bullet on its own line.
- Always tag command code blocks with a shell language (powershell) so the VS Code "Insert into Terminal" button appears.
- When working with wiki docs, use canonical GitHub Wiki page URLs (for example, https://github.com/odomaf/references/wiki/step-00-upfront-decisions) so pages open in rendered wiki view; avoid .md file-path links and avoid %2F-encoded wiki path links unless explicitly verified.
- When asked for a commit message only, provide only the commit command — do not include git add or any other commands.
- Trigger phrase: "Prefs Check".
- When user says "Prefs Check", apply saved preferences first, list applied preferences in one line before answering, and for commands/commits include target terminal/cwd first plus required commit format.
- When publishing new documentation for the GitHub Wiki, ensure the files are placed in docs/wiki or a subfolder that is included by the publishing script. Files outside this path will not appear in the wiki.
- When linking to sample or step pages in the wiki, use the dash-joined path as rendered by GitHub (e.g., ops-steps-sample-step-1-server-layout-sample) for all canonical URLs.
- After moving or renaming documentation files, always update all internal links to match the new canonical wiki page names.
- When publishing to GitHub Wiki, all .md files (including those from subfolders) appear at the wiki root as pages named only by their filename (e.g., step-1-server-layout-sample), not by their full path.
- All canonical wiki links must use only the filename portion (e.g., https://github.com/odomaf/references/wiki/step-1-server-layout-sample), regardless of source folder structure.
- After moving or reorganizing wiki source files, always verify the actual wiki page URLs and update all links to match the rendered wiki.
- I already have an ai_memories repo for persistent instructions.
- For afodom-spa-assessment, store repo-specific memory backups in docs/ai_repo_memories.md.
- Keep repo-specific memories in the repo they belong to as a backup copy.
- When documenting decisions, assumptions, or chosen approaches, write in first-person "I" because I am the decision-maker.
- For modern .NET CLI workflows, `dotnet new sln` may create `.slnx`; always use the actual generated solution filename in commands.
- On Windows, verify .NET SDK architecture (x64 vs x86); x86 installs may not appear in normal x64 `dotnet` usage.
- After SDK installs, open a new terminal (or restart VS Code) before rechecking `dotnet --list-sdks`.
- In planning docs, use completion timestamps in this format: `YYYY-MM-DD HH:MM (UTC±HH:MM)`.
- Prefer separate files for implementation plan and implementation timeline when both are maintained.

## Memory Log

### 2026-05-05

Reason: Add audit-friendly structure for easier preference checks and updates.

Changes:

- Add `Active Rules` section as the current source of truth.
- Add `Memory Log` section for dated change history.
- Preserve all existing preference entries without modification.

### 2026-05-05 (in progress)

Reason: Session updates to memory management and commit message formatting preferences.

Changes:

- Replace "ask whether to update ai_memories" rule with "ask which repo memory should go into."
- Add rule: repo-specific memories stay local unless explicitly requested to go to ai_memories.
- Add rule: keep a backup copy of repo-specific memories inside the repo they belong to.
- Add rule: for afodom-spa-assessment, store repo-specific memory backups in docs/ai_repo_memories.md.
- Add rule: format git commit commands with exactly two -m flags, with the full body kept as a multi-line string.
- Add rule: write decision and assumption documents in first-person "I" rather than "we".

### 2026-05-05 (end of session)

Reason: Capture lessons learned from .NET 10 SDK setup and planning document conventions.

Changes:

- Add rule: `dotnet new sln` may generate `.slnx`; always use the actual generated solution filename.
- Add rule: on Windows, verify .NET SDK is x64, not x86, before troubleshooting dotnet issues.
- Add rule: after SDK installs, open a new terminal before rechecking `dotnet --list-sdks`.
- Add rule: use `YYYY-MM-DD HH:MM (UTC±HH:MM)` format for completion timestamps in planning docs.
- Add rule: prefer separate files for implementation plan and implementation timeline.
