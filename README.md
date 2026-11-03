# dotfiles

Personal config, stored for reference. Nothing is linked or auto-applied.

## VS Code

`vscode/Personal.code-profile`: full profile export (settings, keybindings, snippets, extensions).

### Restore

1. Command Palette → **Profiles: Import Profile...** → **Select File...** → `Personal.code-profile` → **Create**.
2. Switch to the profile.
3. In a WSL window, run **Install Local Extensions in 'WSL: Ubuntu'...** and select all.
4. Reload the window.

### Update

Profiles → Personal → `...` → **Export** → overwrite `vscode/Personal.code-profile` → commit.

### Per-repo extensions (Go, Python, etc.)

Not installed globally. Add to the repo instead:

`.vscode/extensions.json`

```json
{ "recommendations": ["golang.go"] }
```

Python: `["ms-python.python", "charliermarsh.ruff"]`, plus in `.vscode/settings.json`:

```json
{ "[python]": { "editor.defaultFormatter": "charliermarsh.ruff" } }
```