# Amber Monochrome Theme

Custom Omarchy theme — retro CRT amber phosphor monochrome.

## Design Concept

- Background is deep warm-black (`#0c0c0c`), like old CRT glass
- Main text is soft glowing amber (`#c9a36a`)
- Single fixed accent (`#e68e0d`) is reserved for the brightest highlights: selections, shortcuts, graph peaks, workspace markers
- Every semantic color stays in the black → dark amber-brown → golden amber → bright amber family
- No cool grays or unrelated hues

## Color Palette

| Role | Color | Hex |
|------|-------|-----|
| Accent | brightest phosphor highlight, `blue` | `#e68e0d` |
| Selection | dim lit phosphor area | `#2a1f12` |
| Foreground | main phosphor text | `#c9a36a` |
| Bright foreground | full-intensity phosphor | `#f8e8c0` |
| Background | deep CRT black | `#0c0c0c` |
| Muted | comments, inactive | `#5f4635` |

## Color Rules

- Accent is the only high-saturation highlight
- "Red" slots stay dim amber-brown so alerts still read on an amber tube
- Yellow/green/cyan are golden or warm-amber variants, not cool hues
- Omarchy 4.0 maps terminal/editor cursor to `bright_foreground`; do not rely on a `cursor` key
- Active Hyprland border uses the accent at 45deg via `hyprland_active_border`

## Theme Files

- `colors.toml` - Omarchy 4.0 semantic palette (source of truth for generated app configs)
- `shell.lock.toml` - Lock-screen chrome override (amber borders)
- `bar/workspaces.qml` - 4.0 bar override: focused/urgent workspace markers use `accent`
- `btop.theme` - btop override to keep the CRT amber graph ramp
- `neovim.lua` - Neovim colorscheme (matteblack)
- `vscode.json` - VS Code theme (Matte Black)
- `keyboard.rgb` - Keyboard RGB color
- `icons.theme` - Icon theme (Yaru-dark)
- `unlock.png` - Lock-screen shape asset
- `preview.png` - Desktop preview
- `preview-unlock.png` - Lock-screen preview image
- `backgrounds/` - Wallpapers

## Local Development

Omarchy 4.0 copies the theme into `~/.local/state/omarchy/current/theme` and generates app configs from `colors.toml`. After editing theme files, run `omarchy theme refresh` (or `omarchy theme set <name>`). Saving a file is not enough.

A symlink from `~/.config/omarchy/themes/<name>` to a working copy is enough for iteration. `omarchy theme update` skips symlinks.

`bar/workspaces.qml` is a custom bar widget. To use it, point the `omarchy.workspaces` entry in `~/.config/omarchy/shell.json` at that file with `type = "qml"`.

## Public Repository

This repo is public. Keep committed docs and messages useful to any reader, not just this machine.

- Do not commit host-specific paths, clone names, or "this machine" setup
- Describe workflows in generic terms so they apply to anyone installing or developing the theme
- Commit messages follow the existing English history; do not mention local checkout layout or unpublished machine state
