# Laptop

Laptop is an idempotent script to set up a macOS laptop for web and mobile development.

## Install

### Mac OS X

Read, then run the script:

```sh
bash <(curl -s https://raw.githubusercontent.com/rowin1/laptop/master/mac)

bash <(curl -s https://raw.githubusercontent.com/rowin1/laptop/master/git)
```

## What it sets up

* custom macOS settings (Dock, Finder, keyboard, screenshots, ...)
* Homebrew, Homebrew zsh as the login shell
* [Oh My Zsh](https://ohmyz.sh/) with the [zeta theme](https://github.com/skylerlee/zeta-zsh-theme)
* Node (latest LTS, via fnm), Python (via uv), yarn
* Claude Code
* Xcode (via xcodes) and the iOS Simulator
* git, gh, diff-so-fancy, neovim, ripgrep, fd, fzf, bat, eza, tmux and more
* apps: caffeine, docker, iterm2, itsycal, linearmouse, rectangle, slack, textmate, visual studio code
* https://github.com/thoughtbot/dotfiles and https://github.com/ryanong/vim-bootstrap (via rcm)
* files from this repo:
  * `.gitconfig` → `~/.gitconfig` (machine-specific settings go in `~/.gitconfig.local`)
  * `Doom.itermcolors` → an iTerm2 "Doom" profile, set as the default
  * `rowin1.code-profile` → VS Code settings and extensions
  * `mouse.md` → LinearMouse config with pointer acceleration disabled

## Manual steps

* Grant LinearMouse Accessibility access when it asks.
* `keyboard.md`: swap Command and Option for an external Windows keyboard in
  System Settings → Keyboard → Keyboard Shortcuts → Modifier Keys.
