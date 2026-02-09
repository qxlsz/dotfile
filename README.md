# dotfiles

My dotfiles, managed with [chezmoi](https://chezmoi.io).

## What's included

| File | Description |
|---|---|
| `.zshrc` | Zsh config — oh-my-zsh, Powerlevel10k, plugins, PATH setup |
| `.p10k.zsh` | Powerlevel10k prompt theme config |

## Setup on a new machine

```bash
# Install chezmoi and apply dotfiles in one command
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply qxlsz --repo-url git@github.com:qxlsz/dotfile.git
```

Or if chezmoi is already installed:

```bash
chezmoi init --apply qxlsz --repo-url git@github.com:qxlsz/dotfile.git
```

### Dependencies

Install these after applying dotfiles:

- [oh-my-zsh](https://ohmyz.sh/)
- [Powerlevel10k](https://github.com/romkatv/powerlevel10k)
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
- [fzf](https://github.com/junegunn/fzf)

## Usage

```bash
# Track a new dotfile
chezmoi add ~/.some-config

# Edit a tracked file
chezmoi edit ~/.zshrc

# See what would change
chezmoi diff

# Apply changes from repo
chezmoi apply

# Pull and apply latest from remote
chezmoi update

# Commit and push changes
chezmoi cd
git add . && git commit -m "update" && git push
```

## Machine-specific config

Put machine-specific settings in `~/.zshrc.local` — this file is sourced automatically but not tracked by chezmoi.
