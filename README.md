# morvane-i3-theme

The MorvaneOS look for i3: the Twilight wallpaper, and MorvaneOS colours for window
borders, titles and i3's bar. The focused window has a Pastel Pink border as well
as brighter title text, so it isn't told apart by colour alone.

i3's default config (`/etc/i3/config`) belongs to i3 and has no include directory,
so this package installs a copy of it with the MorvaneOS look added,
`/usr/share/morvane-i3-theme/config`. New users get a `~/.config/i3/config` that
just includes it:

```
include /usr/share/morvane-i3-theme/config
```

so they stay on the current theme after package updates, can add their own settings
below the include (later lines override earlier ones), and don't get i3's first-run
config wizard. Existing users keep their own config.

Terminal colours (xterm) come from
[morvane-wm-theme](https://github.com/MorvaneOS/morvane-wm-theme), apps from
[morvane-gtk-theme](https://github.com/MorvaneOS/morvane-gtk-theme). The MorvaneOS
installer installs this package with i3.

## Changing it

Edit `tools/build.py`, then run it on i3's default config (from the `i3-wm`
package, `/etc/i3/config`):

```
python tools/build.py [path/to/i3/config]
```

Needs only Python. Rebuild when i3's default config changes. Commit the output, bump
`pkgver`, build and publish.

## License

BSD-3-Clause, like i3, since the config is i3's default with the MorvaneOS look added.
