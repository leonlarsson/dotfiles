# dotfiles

Personal config, stored for reference. Nothing is linked or auto-applied.

## VS Code

```
vscode/
├─ settings.json
├─ keybindings.json
├─ extensions.txt
└─ snippets/
   └─ clog.code-snippets
```

### Restore into a new profile

1. Command Palette → **Profiles: New Profile** → name it, **Copy from: None**.
2. With that profile active:
   - **Preferences: Open User Settings (JSON)** → paste `settings.json`
   - **Preferences: Open Keyboard Shortcuts (JSON)** → paste `keybindings.json`
   - **Snippets: Configure Snippets** → **New Global Snippets file** → name it `clog` → paste the snippet file
3. Install extensions (PowerShell, from this folder):

   ```powershell
   Get-Content vscode/extensions.txt | % { code --profile "<ProfileName>" --install-extension $_ }
   ```

4. Open a WSL window and click **Install in WSL** on any extension that asks.

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

### Updating

When settings change in VS Code, copy them back here and commit. The profile is the live copy; this repo is the snapshot.
