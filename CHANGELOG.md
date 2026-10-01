# MythosLoader release notes

## 1.1.0

- **Built-in updates.** MythosLoader checks for a new release when it starts and shows an Update button
  in the title bar. One click downloads the new version, verifies it, and restarts into it. Your running
  games are not closed. If you have 1.0.0, download 1.1.0 by hand this one last time.
- **Performance mod per loader.** Press "Download lowHD (once)" in a loader's Launch options, then switch
  the mod on or off per loader from the right-click menu. Loaders without the mod keep full quality and
  your normal graphics settings. lowHD is made by celloboy126.
- **Install any mod from a zip** you downloaded yourself.
- The title bar now shows the real version number.

Known limits are unchanged: not code-signed yet, and limited testing against live game sessions.

## 1.0.0

First release.

- Add a loader by pasting a login token (`US-…`, `EU-…`, `KR-…`) or by logging in on Battle.net's own page
- Saved logins, encrypted for your Windows user, refreshed after every launch
- Launch one loader, the selected ones, or all of them, one after another with live progress
- Game windows named from a template (`D2R: {name}`), with a per-loader override
- Launch options for all loaders and per loader, with a live preview of the command line
- Switch a loader's region without re-adding it
- Intro video skip, globally or per loader
- Right-click menu on every loader for quick access

Known limits: not code-signed yet (Windows SmartScreen will warn), and limited testing against live
game sessions so far. Tray, Identify, hotkeys and groups are planned for later releases.

Help and feedback: https://discord.com/invite/d2rmythos
