# Animated Oxygen White Cursors

Animated Oxygen White Cursors from https://www.rw-designer.com/cursor-set/animated-oxygen-white, released as a linux theme.

## Installation

Copy the `animated-oxygen-white` directory in `$USER/.local/share/icons`, and select the theme in your preferred desktop environment.
It depends on the Oxygen White theme.

## Making of

Some pointers were ignored:
- `Normal Select.ani` : Too distracting for a default cursor
- `Working in background.ani` : The existing Oygen cursor is already animated, and looks better (in my opinion)
- `Text Select.ani` : Too big and hides the underlying text

```cmd
# Transforme the .ani cursors into X11 cursors
win2xcur *.ani

mv "Vertical Resize" ns-resize
for n in size_ver n-resize s-resize sb_v_double_arrow v_double_arrow 00008160000006810000408080010102; do
  ln -sfn ns-resize "$n"
done

mv "Horizontal Resize" ew-resize
for n in size_hor e-resize w-resize sb_h_double_arrow 028006030e0e7ebffc7f7070c0600140; do
  ln -sfn ew-resize "$n"
done

mv "Diagonal Resize 2" nesw-resize
for n in size_bdiag ne-resize sw-resize 50585d75b494802d0151028115016902; do
  ln -sfn nesw-resize "$n"
done

mv "Diagonal Resize 1" nwse-resize
for n in size_fdiag nw-resize se-resize; do
  ln -sfn nwse-resize "$n"
done

mv "Link Select" pointing_hand
for n in pointer hand1 hand2 9d800788f1b08800ae810202380a0822 e29285e634086352946a0e7090d73106; do
  ln -sfn pointing_hand "$n"
done

mv Move fleur
for n in all-scroll size_all move; do
  ln -sfn fleur "$n"
done

mv Handwriting pencil
```
