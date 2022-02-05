# Add "Open in VS Code" to Nemos Context menu

```
echo "[Nemo Action]
Name=Open with VS Code
Comment=Opens VS Code in the current directory
Exec=code %P
Icon-Name=code
Selection=none
Extensions=any;
Quote=double
Dependencies=code;" > $HOME/.local/share/nemo/actions/open-vscode.nemo_action
```
