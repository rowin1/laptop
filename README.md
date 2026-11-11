# Laptop

Laptop is an idempotent script to set up a macOS laptop for web and mobile
development. It's safe to re-run: steps that are already done are skipped.

## New computer checklist

### 1. Before running anything

1. Install [Firefox](https://www.mozilla.org/firefox/) using Safari.
2. Log in to your work email in Firefox.
3. Log in to [Claude](https://claude.ai) in Firefox.
4. Ask Claude to review [`mac`](mac) with you and update anything that's out of
   date, such as versions (`PYTHON_VERSION`), Homebrew packages and apps that
   were renamed or are no longer needed, or settings you want to tweak.
   Commit any changes to this repo first, because the script runs from GitHub.

### 2. Run the setup script

```sh
bash <(curl -s https://raw.githubusercontent.com/rowin1/laptop/master/mac)
```

It asks for your password (sudo) and later your Apple ID for Xcode, so stay
nearby. The Xcode and iOS Simulator downloads are several GB.

### 3. After the script finishes

1. Quit Terminal and open **iTerm2**. It should use the Doom colors and the
   zeta prompt (Oh My Zsh).
2. Run the git script to set your git name/email, add your SSH key to GitHub
   and clone the work repos into `~/Workspace`:

   ```sh
   bash <(curl -s https://raw.githubusercontent.com/rowin1/laptop/master/git)
   ```

   * The `mac` script already made an SSH key, so answer **n** when it asks to
     overwrite `~/.ssh/id_ed25519`. The existing key is still copied to your
     clipboard to paste at https://github.com/settings/keys.
   * The name/email you enter replace the ones in `.gitconfig` on this
     machine, so use your work email if that's what this computer is for.
3. Run `claude` and log in to Claude Code.
4. Open **LinearMouse** and grant it Accessibility access
   (System Settings → Privacy & Security → Accessibility).
5. External Windows keyboard? Swap Command and Option in
   System Settings → Keyboard → Keyboard Shortcuts → Modifier Keys
   (see [`keyboard.md`](keyboard.md)).

You don't need to set up `.gitconfig`, `Doom.itermcolors`, `mouse.md` or the
VS Code profile by hand any more. The `mac` script does it (see below).

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
  * `mouse.md` → LinearMouse config with pointer acceleration disabled for mice
