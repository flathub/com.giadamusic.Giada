# Giada packaging

Some flatpak note for Giada.

## Permissions

- Device = all for MIDI and other
- Filestystem = home: fltk doesn't do portals
- pw-jack permissions
- No wayland as this is incompatible with audio plugins and fltk
  doesn't support it.

## Patches

- `patches/giada-fs.patch` : still link against `-lstdc++fs` like it's
  Ubuntu.
- `patches/giada-path.patch` : need to set path for VST3.
- `patches/giada-fmt.patch` : patch to upstream: `fmt::format` expect
  a constexpr format.
- `patches/juce-616-header.patch` : some usual JUCE patches for newer
  gcc header layout.

## Wrapper script

This is needed for LV2_PATH.

## Buildsystem

giada doesn't build with `cmake-ninja`.

## AppStream

I seems that upstream doesn't update the release in the AppStream file
so this is done with *cough* `sed`. Let's hope appstream validate will
catch the silent failure of `sed`.
