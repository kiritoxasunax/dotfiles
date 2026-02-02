# Dotfiles

Personal dotfiles managed with GNU Stow.

## Quick Start

```bash
# Clone with submodules
git clone --recurse-submodules https://github.com/kiritoxasunax/dotfiles.git ~/dotfiles

# Or if already cloned, init submodules
cd ~/dotfiles && git submodule update --init --recursive

# Deploy all configs
cd ~/dotfiles
stow shell zsh-custom alacritty kitty btop cava nvim niri dank-material-shell konsole
```

## Prerequisites

Before deploying, ensure these are installed:

- **zsh** + **oh-my-zsh** (clone oh-my-zsh separately, custom dir managed here)
- **alacritty** - GPU-accelerated terminal
- **kitty** - Another GPU terminal
- **btop** - Resource monitor
- **cava** - Audio visualizer
- **neovim** - Editor (uses LazyVim)
- **niri** - Scrollable tiling Wayland compositor
- **konsole** - KDE terminal

## Packages

| Package | Target | Description |
|---------|--------|-------------|
| `shell` | `~/` | zshrc, bashrc, p10k, fzf, nanorc |
| `zsh-custom` | `~/.oh-my-zsh/custom/` | Zsh plugins & themes (submodules) |
| `alacritty` | `~/.config/alacritty/` | Alacritty terminal config |
| `kitty` | `~/.config/kitty/` | Kitty terminal config |
| `btop` | `~/.config/btop/` | Btop resource monitor config |
| `cava` | `~/.config/cava/` | Cava audio visualizer shaders |
| `nvim` | `~/.config/nvim/` | Neovim/LazyVim config |
| `niri` | `~/.config/niri/` | Niri Wayland compositor config |
| `dank-material-shell` | `~/.config/DankMaterialShell/` | Material theme for shell bars |
| `konsole` | `~/.local/share/konsole/` | Konsole profiles |

## Deploy Individual Package

```bash
cd ~/dotfiles
stow alacritty  # Creates symlinks for alacritty config only
```

## Uninstall

```bash
cd ~/dotfiles
stow -D shell  # Remove symlinks for shell package
```

## Submodules

Zsh plugins are managed as git submodules:

- `zsh-autosuggestions` - Fish-like autosuggestions
- `zsh-syntax-highlighting` - Syntax highlighting for zsh
- `powerlevel10k` - Fast zsh theme

Update submodules:
```bash
git submodule update --remote --merge
```
