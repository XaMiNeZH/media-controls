## What does this extension do?

Show controls and information of the currently playing media in the panel.

This is a maintenance fork of the archived [sakithb/media-controls](https://github.com/sakithb/media-controls) project. It keeps the original UUID so it can replace an existing install and preserves your settings. Version 2.5.0 adds GNOME 50 support for Fedora 44 (and other GNOME 50 desktops).

## Features

- Customize the extension the way you want it
- Basic media controls (play/pause/next/previous/loop/shuffle/seek)
- Mouse actions lets you run different actions via left/middle/right/scroll.
- Popup with album art and a slider to control the playback
- Scrolling animations
- Blacklist players

---

## How to install

Do **not** install from [extensions.gnome.org](https://extensions.gnome.org/extension/4470/media-controls/). That listing is still on 2.4.4 and only declares GNOME 46–49, so Fedora 44 / GNOME 50 will refuse to enable it.

#### Build from this repository (recommended)

Requires `pnpm`, `gnome-extensions`, `glib-compile-resources`, and `gettext`.

```bash
git clone https://github.com/xaminezh/media-controls.git
cd media-controls
pnpm install
pnpm build
gnome-extensions install --force dist/builds/mediacontrols@cliffniff.github.com.shell-extension.zip
```

On Wayland (Fedora Workstation default), log out and log back in, then enable the extension:

```bash
gnome-extensions enable mediacontrols@cliffniff.github.com
```

You can also enable it from Extension Manager after the session restart.

#### Install a release zip

- Download the archive from this fork's releases tab
- Open a terminal in the directory containing the downloaded file
- Run `gnome-extensions install --force extension.zip`
- Log out and back in on Wayland, then enable the extension

---

## Reporting issues

- Make sure your issue isn't a duplicate
- Include the following information when creating the issue,
  - Extension version
  - Gnome version
  - Your distribution
  - A screenshot if it is possible

---

## Development

This project uses pnpm for package management and script execution. Make sure you have pnpm installed.

### Available Scripts

**Building:**
- `pnpm build` - Build the extension
- `pnpm release` - Build release version (strips debug code)

**Development:**
- `pnpm debug` - Run a nested gnome session for debugging
- `pnpm translations` - Update translation files

**Extension Management:**
- `pnpm run ext:install` - Install the extension
- `pnpm run ext:uninstall` - Uninstall the extension
- `pnpm run ext:enable` - Enable the extension
- `pnpm run ext:disable` - Disable the extension
- `pnpm run ext:prefs` - Open extension preferences

### Quick Start for Contributors

1. Clone the repository
2. Install dependencies: `pnpm install`
3. Build and install: `pnpm build` then `pnpm run ext:install`
4. Enable the extension: `pnpm run ext:enable`
5. Open preferences to test: `pnpm run ext:prefs`

For active development, use `pnpm debug` (Wayland) to test changes.

---

## Get involved

Any type of contribution is appreciated! If you have any suggestions for new features feel free to open a new issue.

If you are interested in translating, download the [po file](https://github.com/xaminezh/media-controls/blob/main/assets/locale/mediacontrols%40cliffniff.github.com.pot) and translate it. Then open a pull request with the translated file. You can use [Gtranslator](https://flathub.org/apps/org.gnome.Gtranslator) or [Poedit](https://flathub.org/apps/net.poedit.Poedit) to translate.

If you are interested in contributing code. There are no specific guidelines for contributing. Just make sure you follow the coding style of the project. To update the translation files run `pnpm run translations` in the extensions directory after your changes are done. This will update the files in the locale folder.

---

## Screenshots

#### Popup menu

[<img src="assets/images/popup.png" width="400">]()

#### General settings

[<img src="assets/images/prefs_general.png" width="400">]()

#### Panel settings

[<img src="assets/images/prefs_panel.png" width="400">]()

#### Position settings

[<img src="assets/images/prefs_positions.png" width="400">]()

#### Shortcut settings

[<img src="assets/images/prefs_shortcuts.png" width="400">]()

#### Other settings

[<img src="assets/images/prefs_other.png" width="400">]()
