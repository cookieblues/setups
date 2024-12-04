# First to-dos
1. Run `sudo pacman -Syu` to update all packages.
2. Generate ssh keys for git with `ssh-keygen -t rsa`.
3. Install vscode with `sudo pacman -S code`.
4. Uninstall everything zsh related from manjaro.
5. Install zsh again with `pacman -Ss zsh`.
6. [Change default shell](https://wiki.archlinux.org/title/Command-line_shell#Changing_your_default_shell) to be zsh. Restart or relog to take effect.
7. Install oh-my-zsh: `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
8. Install [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh) and [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#in-your-zshrc).
9. Install [powerlevel10k zsh theme](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#oh-my-zsh) and run through configuration.
10. Set vscode default terminal to zsh.
11. Press ctrl+shift+p to open Command Palette in vscode, then search for "Preferences: Open Keyboard Shortcuts (JSON)" and add the following keybindings:
```
// Place your key bindings in this file to override the defaults
[
    {
        "key": "ctrl+tab",
        "command": "workbench.action.nextEditor",
    },
    {
        "key": "ctrl+shift+tab",
        "command": "workbench.action.previousEditor",
    },
    {
        "key": "ctrl+.",
        "command": "workbench.action.terminal.focus",
    },
    {
        "key": "ctrl+.",
        "command": "workbench.action.focusActiveEditorGroup",
        "when": "terminalFocus"
    },
    {
        "key": "ctrl+up",
        "command": "cursorMove",
        "args": {
            "to": "up",
            "by": "line",
            "value": 10,
        },
        "when": "editorTextFocus"
    },
    {
        "key": "ctrl+down",
        "command": "cursorMove",
        "args": {
            "to": "down",
            "by": "line",
            "value": 10,
        },
        "when": "editorTextFocus"
    },
    {
        "key": "ctrl+=",
        "command": "editor.action.fontZoomIn",
    },
    {
        "key": "ctrl+-",
        "command": "editor.action.fontZoomOut",
    },
]
```
12. Install [uv](https://docs.astral.sh/uv/): `curl -LsSf https://astral.sh/uv/install.sh | sh`.