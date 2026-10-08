# Animated Oxygen White Cursors

Animated version of the Oxygen White cursors, converted to X11 (Xcursor) for Linux desktops.

Source animations: https://www.rw-designer.com/cursor-set/animated-oxygen-white

## Installation

Copy the `animated-oxygen-white` directory in `~/.local/share/icons`, then select **Animated Oxygen White** as your cursor theme in your desktop settings.

```bash
cp -r animated-oxygen-white ~/.local/share/icons/
```

This theme depends on the `Oxygen_White` theme, which must be installed on your system.

## Making of

Some pointers were left out:
- `Normal Select.ani` : too distracting for a default cursor.
- `Working in background.ani` : the existing Oygen busy cursor is already animated and looks better.
- `Text Select.ani` : too big and hides the underlying text.

The conversion requires [win2xcur](https://github.com/quantum5/win2xcur)

Then, from the directory containing the `.ani` files:

```bash
# Convert the .ani cursors to X11 cursors
mkdir -p cursors
win2xcur *.ani -o cursors/

cd cursors

# Rename the converted files to their X11 names and create aliases
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

## Credits and Licence

- Animated cursors: Exund. According to the [source page](https://www.rw-designer.com/cursor-set/animated-oxygen-white), the set was released to the public domain.
- Base cursors (Oxygen-White): Erik, from the [openSUSE Oxygen-White set](https://www.rw-designer.com/cursor-set/opensuse-oxygen), which is derived from the Oxygen cursors of KDE.
- Oxygen cursors: KDE, https://github.com/KDE/oxygen, licensed under the GNU LGPL v3.

Because this work is derived from the Oxygen cursors, the whole theme is distributed under the GNU Lesser General Public License v3.0. See [LICENSE](LICENSE).
