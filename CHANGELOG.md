# Added Wayland support
## Changes
- Added a portal-based screenshot backend to run on Wayland while keeping the existing X11 path
- Added a compositor-agnostic image buffer pipeline so rendering no longer assumes X11 BGRA layouts

## Usage
- Default: on Wayland (`WAYLAND_DISPLAY` set) Boomer will use the portal backend; otherwise X11
- Override: `./boomer --backend portal` or `BOOMER_BACKEND=portal ./boomer` (similarly, `x11` to force legacy)
- Install one portal helper that matches your compositor:
  - wlroots: `grim` (+ `xdg-desktop-portal-wlr`)
  - GNOME: `gnome-screenshot`
  - KDE: `spectacle`
 
## Other dependencies
- `stb_image >= 2.5`
