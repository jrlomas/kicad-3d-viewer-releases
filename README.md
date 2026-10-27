# KiCad 3D Viewer for Windows (experimental)

Downloads of an experimental Vulkan ray-traced 3D viewer for KiCad PCBs. It installs next to a
normal KiCad 10 and adds a button to the PCB editor that opens the current board in the viewer.

This is an unofficial add-on. It is not made or supported by the KiCad project.

## Downloads

See [Releases](../../releases). Each release has:

- `kicad-3d-viewer-<version>-win64-setup.exe`: the installer (recommended).
- `kicad-3d-viewer-<version>-win64.zip`: a portable copy that does not need installing.
- `SHA256SUMS.txt`: checksums of both.

## Requirements

- Windows 10 or 11, 64-bit.
- KiCad 10.0.x from the official KiCad installer.
- A graphics card with a current driver that supports Vulkan.
- An internet connection the first time the PCB editor button is used, so KiCad can set up the
  plugin's Python environment.

## Installing

1. Run the setup program. It installs for your user only and needs no administrator rights.
   The installer is not signed, so Windows SmartScreen may warn about it: choose
   "More info", then "Run anyway".
2. In KiCad, open Preferences > Plugins and turn on the KiCad API server.
3. Restart the PCB editor. The first time, KiCad downloads the plugin's Python package
   (`kicad-python`), which can take a minute. After that, the "Open in Vulkan 3D viewer" button
   on the PCB editor's toolbar opens the current board in the viewer.

The viewer can also be started on its own from the Start menu ("KiCad 3D Viewer"): it asks for
a `.kicad_pcb` file, and you can drop another board file on its window to open it instead. It
finds 3D models through the path variables of the installed KiCad 10.

The viewer keeps its own copy of the KiCad libraries and its own settings. It does not change
the installed KiCad or the system `PATH`.

## Uninstalling

Use Settings > Apps > Installed apps > "KiCad 3D Viewer" > Uninstall. This removes the viewer,
its Start menu entry and the PCB editor plugin.

## Status

Experimental. The packages have so far been tested under Wine on Linux, not on a real Windows
machine. Problems with the graphics card, the toolbar button or 3D models are the most likely.

## License

GPL-3.0-or-later, like KiCad. The package includes the licenses of KiCad and of every bundled
library in its `licenses` folder. The source code of each build (KiCad plus the viewer changes,
at the commit named in the release notes) is available from the author on request.
