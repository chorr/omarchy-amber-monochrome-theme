# Amber Monochrome Theme

Custom Omarchy theme project — Retro CRT amber phosphor monochrome style.

## Scope

This repository contains only theme assets for Omarchy:

- Color definitions (`colors.toml`)
- Application themes (btop, icons, Neovim, VS Code)
- Wallpapers and lock screen assets
- Metadata for `omarchy theme install`

## Development Notes

- The theme is installed by cloning this repo into `~/.config/omarchy/themes/amber-monochrome/`
- After changes to source here, either:
  - Re-clone / rsync to the installed location, or
  - Run `omarchy theme set amber-monochrome` after manually syncing
- `omarchy theme refresh` or full `omarchy refresh` may be needed for some components (waybar, etc.)
- Previews (`preview.png`, `preview-unlock.png`) should be updated when the visual identity changes significantly.

## Retro CRT Concept

The palette is designed to feel like an old amber phosphor CRT terminal:

- Background is deep warm-black (#0c0c0c) — like the dark glass of a classic monitor.
- Main text uses soft glowing amber (#c9a36a) — the characteristic lit phosphor look.
- The single fixed accent (#e68e0d) is reserved for the brightest, most intense highlights (selections, shortcuts, graph peaks, cursor). This mimics the "full brightness" part of the phosphor when the beam is strongest.
- Every color in the 16-color ANSI set stays inside the black → dark amber-brown → golden amber → bright amber family. There are no cool grays or unrelated hues.

This creates a cohesive "everything is rendered on one old amber tube" feeling.

## Useful Commands (on target machine)

```bash
omarchy theme list
omarchy theme current
omarchy theme set amber-monochrome
omarchy theme bg next
omarchy restart waybar
omarchy restart terminal
```

## License

See upstream Matte Black and Omarchy for asset origins. Theme-specific configuration is provided under the same terms as the Omarchy project unless otherwise noted.
