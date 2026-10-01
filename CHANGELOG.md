# MythosLoader release notes

## 1.1.2

- **Fixed a false "Log in again" message.** If the game closed before it saved a new login, the loader
  was marked as needing a new login even though its saved login still worked. It now shows a neutral
  "Closed before a new login was saved", keeps the login, and tries it again on the next launch.
- The LOGIN column shows "Unconfirmed" for a login that has not been confirmed by a completed launch yet.

## 1.1.1

- **Fixed: the second login failing.** A loader could log in the first time and then fail to connect to
  Battle.net on the next launch. MythosLoader now only saves a login the game has really written, and
  keeps watching for it while the game runs and when it closes.
- **If a loader is already affected,** right-click it and choose "Log in again / new token" once.
- A loader's row now shows "Exited" when its game closes.
- The Activity panel shows what the game does to its login slot during a launch (no login data), which
  helps when reporting a problem.
- Keep MythosLoader open while you play: some logins are only saved when the game closes.

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
