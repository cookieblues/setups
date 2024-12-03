# Setup iTerm2 and vscode
1. Open (default) terminal and install [brew](https://brew.sh/): `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
2. Install iTerm 2: `brew install --cask iterm2`, and set to default terminal.
3. Install vscode with brew: `brew install --cask visual-studio-code`.
4. Install oh-my-zsh: `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
5. Install [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh) and [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#in-your-zshrc).
6. Install [powerlevel10k zsh theme](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#oh-my-zsh) and run through configuration.
7. Set vscode default terminal to be iTerm2 using the following settings.json:
```
{
    "terminal.integrated.shell.osx": "/bin/zsh",
    "terminal.integrated.defaultProfile.linux": "zsh",
    "terminal.integrated.fontFamily": "MesloLGS NF",
}
```
8. Press ctrl+shift+p to open Command Palette in vscode, then search for "Preferences: Open Keyboard Shortcuts (JSON)" and add the following keybindings:
```
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
        "key": "cmd+.",
        "command": "workbench.action.terminal.focus",
    },
    {
        "key": "cmd+.",
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
        "key": "cmd+=",
        "command": "editor.action.fontZoomIn",
    },
    {
        "key": "cmd+-",
        "command": "editor.action.fontZoomOut",
    },
]
```

# Setup pyenv, pipx, and poetry (if not using uv)
1. Install pyenv with brew and add `eval "$*(pyenv init --path)"` to your `.zshrc` (or whatever shell config) file.
2. Install at least one Python version from pyenv, e.g. `pyenv install 3.11.9`.
3. Potentially use an internal package place like Artifactory. Set up here.
4. Install pipx with pip: `python -m pip install pipx` and `python -m pipx ensurepath`.
5. Install poetry with pipx (as [recommended](https://python-poetry.org/docs/#installing-with-pipx)): `python -m pipx install poetry`.

Poetry should be be globally available, test with `poetry --version`.