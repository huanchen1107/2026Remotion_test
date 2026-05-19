# 🚀 2026 StartEndShell Project Template (v2.1 Consolidated)

This is a premium, highly consolidated shell session framework designed for managing development workflows seamlessly with **Claude Code** and advanced AI coding agents. It automates first-run project bootstrapping, session state synchronization, workspace sanitization, and secure dialogue reconstruction.

## 🚀 Quick Start

```bash
./startup.sh   # Warm start: auto-verifies environment, handles first-run setup/cleanup, pulls, and launches Claude Code CLI
./ending.sh    # Session closer: auto-reconstructs dialogue, redacts keys, commits, and pushes to remote
```

---

## 🤖 Unified Flow (How it Works)

```mermaid
graph TD
    A[Run ./startup.sh] --> B{First Run?}
    B -- Yes --> C[Run clean_workspace: Wipes template files & resets Git]
    C --> D[Connect & Push to new GitHub repository]
    D --> E[Write .project_setup Lockfile]
    B -- No --> F[Perform git pull]
    F --> G[Print log.md task lists]
    E --> H[Launch cc.sh for Claude Code session]
    G --> H
    H --> I[Execute ./ending.sh to close session]
    I --> J[Run utils/reconstruct_dialog.py to save key-redacted user/dialog.md]
    J --> K[Auto-commit & Push session status to GitHub]
```

---

## 🧭 Project Structure

```text
.
├── startup.sh         # Opener: auto-detects first-run (resets git, sanitizes directories), pulls, and boots cc.sh
├── ending.sh          # Closer: rebuilds dialogue logs, auto-commits under timestamps, and pushes to remote
├── cc.sh              # Unified CLI Launcher: direct entry to Claude Code CLI
├── .env               # API Keys and target repository configurations (GIT IGNORED)
├── .env.bak           # Template for API Keys and repository settings configurations
├── log.md             # Chronological development log (read/updated in each session)
├── CLAUDE.md          # Karpathy-style behavior rules for AI coding agents
├── README.md          # Project guide (this file)
└── utils/
    └── reconstruct_dialog.py # Dialogue parser: compiles model brain logs to user/dialog.md with redacting
```

---

## 🛠️ Setup & Configuration

1. **API Credentials & Project Goal Setting**:
   - Copy `.env.bak` to `.env` in the root directory:
     ```bash
     cp .env.bak .env
     ```
   - Open `.env` and fill in your keys:
     - `ANTHROPIC_API_KEY`: Your official Anthropic key.
     - `REPO_NAME`: *(Optional)* Pre-assign your target GitHub repository name (e.g. `"2026Remotion_test"`). If left empty, `startup.sh` will guide you interactively.
   - Describe your core project goals in `project_initial.md` (which will be read upon setup).

2. **Run Initialization**:
   - Simply start by running:
     ```bash
     ./startup.sh
     ```
   - On the **first run**, `startup.sh` will automatically:
     - Reset your repository history to remove the template.
     - Prompt you to connect or automatically provision a repository under your GitHub account.
     - Sanitize all folder paths and files to build a pristine workspace.
     - Generate a lockfile (`.project_setup`) so subsequent runs boot straight into your session.

3. **Develop with Guardrails**:
   - The template loaded **Karpathy-style AI agent rules** inside `CLAUDE.md`. These guidelines instruct AI coding assistants to use surgical diffs, simplicity first, pre-coding statements, and regular log keeping to minimize mistakes.

4. **Conclude Sessions**:
   - When ending your workday, execute:
     ```bash
     ./ending.sh
     ```
   - This automatically updates `log.md`, processes key-redacted conversation logs into `user/dialog.md`, commits all changes with a timestamp, and pushes them up to GitHub.

---

## 📝 Prerequisites
- **Node.js & npx** — required to run the official Claude Code CLI.
- **Git & Curl** — for remote synchronization and status testing.
- **GitHub CLI (`gh`)** *(Optional)* — if you wish to allow `startup.sh` to automatically provision public/private repositories on your GitHub account.
