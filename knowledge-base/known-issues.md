# Known Issues & Workarounds

## Issue 1: GitHub CLI & Vercel CLI Authentication in Non-Interactive Shell
- **Status**: Open
- **Description**: In automated agent execution sessions, interactive browser logins (`gh auth login` and `vercel login`) cannot open browser windows or accept interactive terminal inputs without user action or API tokens.
- **Fix**: User can provide GitHub Personal Access Token (PAT) and Vercel Token, or run one-time authentication commands in their local terminal.
