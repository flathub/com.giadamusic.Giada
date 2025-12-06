# Giada packaging

Some flatpak note for Giada.

## Permissions

- Filestystem = home: fltk doesn't do portals, and audio plugins.
- pw-jack permissions
- No wayland as this is incompatible with audio plugins and fltk
  doesn't support it.

## Patches

- `patches/giada-fs.patch` : still link against `-lstdc++fs` like it's
  Ubuntu.
- `patches/giada-path.patch` : need to set path for VST3.
- jsoncpp needs some build fixes.

## Wrapper script

This is needed for LV2_PATH.
