# MythosLoader release notes

## 1.2.6

- **Games keep their window size.** A game started in windowed mode no longer stays maximized after it signs
  in: it goes back to the size it opened at (or to its saved position, if you saved one). Full screen and
  borderless games are left as they are.
- **No more "Logged in" notification.** A game signing in is only noted in the activity log. Notifications for
  a launch problem, all launches finished and a crash are unchanged.

## 1.2.5

- **Window layouts.** A new **▦ Windows ▾** button tiles your games on the monitor MythosLoader is on, or
  across all your monitors, at the game's 16:9 shape. Each game opens where it was next time (saved when you
  tile, with **Save window positions**, or when you close it from MythosLoader). A spot on a monitor that is
  gone is ignored. Can be turned off in Settings.
- **Close games from MythosLoader.** **■ Close ▾** closes all games or the ones you ticked, after a Yes/No
  check; right-click a loader for **Close game**. Games close normally, like pressing their X.
- **Crash recovery.** A game that closes with an error shows **Crashed (exit code …)** and a notification.
  **↻ Relaunch closed** starts every game that closed again with one click.
- **Lighter game settings for alts.** In a loader's Launch options: a frame rate limit (30 / 60 / 90 / 120) and
  **Lowest graphics** for that loader's game only. Your other games keep your own settings.
- **New Runewords tab:** every runeword with its runes in order, bases, sockets, level, stats and where it came
  from, searchable by name, rune, base or stat.
- **Favourites:** star recipes and runewords to keep them at the top.
- **A running loader is never started twice.** Launch all skips loaders that are already running, also after
  MythosLoader is reopened.
- Tab icons on every tab and alternating row colours in the loader list.

## 1.2.4

- **Much faster multi-launch.** All your games now load at the same time and sign in one by one, each as
  soon as the one before it has picked up its login. Two accounts are usually in the game in around ten
  seconds; each extra account adds a second or two. Every game still signs in with its own account.
- **No more "Press any key to begin".** MythosLoader presses it for you, on each game's turn only, and never
  once a game has signed in.
- **New Recipes tab** with the game's Horadric Cube icon: every cube recipe in the game, searchable by rune,
  gem, item or mod, with pictures, crafted mods, item level rules and Ladder / difficulty notes.
- Settings: "Gap between launches" is now **Pause between sign-ins** (default 0).

## 1.2.3

- **Fixed: "Data version mismatch detected" on start-up** with intro skip on (1.2.2). The intro-skip mod now
  carries the game's build number, which the game checks for every mod. It is updated by itself after a game
  patch.

## 1.2.2

- **Intro skip fixed.** The old method pressed Space for 15 seconds after the game window appeared. Those
  presses could pile up while the game was loading and land later, on the character screen or in game. Intro
  skip now uses a tiny mod with empty start-up videos (the way lowHD does it): no key presses at all, and the
  title screen shows in a few seconds. Loaders using lowHD need nothing extra. Loaders using another mod get a
  careful fallback that presses Space only while a start-up video is playing.

## 1.2.1

- **Settings is now a tab** in the main window, next to Loaders, instead of a pop-up. Everything fits on
  one page without scrolling. The gear button and the tray menu open it.
- **Discord button** now shows the real Discord logo.

## 1.2.0

- **System tray.** A tray icon with a menu to launch loaders and groups, bring a running game to the
  front, label all games, open Settings and exit. Left-click shows or hides MythosLoader. Minimise to
  tray, close to tray, start minimised, start with Windows and notifications are in Settings.
- **Identify.** A label with the slot number and loader name appears over each game window for a few
  seconds, so you can see which window is which.
- **Focus hotkeys** (off by default): Ctrl+Alt+1…9 bring a game to the front, Ctrl+Alt+0 labels all
  games, Ctrl+Alt+L shows MythosLoader.
- **Groups.** Put loaders in named groups and launch a whole group from the Groups button, the tray or
  the command line (`--group "name"`).
- **Title keeper and live rename.** If the game changes its window title back, MythosLoader restores it;
  changing the title template renames running windows at once.
- **Import from D2RML** (Settings): brings over loaders and settings from a D2RML folder.
- **Updater fixed.** "The update could not be installed: the file is being used by another process" no
  longer blocks an update. If you see that error on an older version: close your games and MythosLoader,
  start MythosLoader again and press Update, or download this version by hand once.
- **Launch options window** is wider, in two columns, and no longer needs scrolling.

## 1.1.4

- **New icon.** The icon in the title bar, the window and the taskbar is now the Ber rune as it appears
  in the game, on a transparent background.

## 1.1.3

- **LOGIN column now says what is true.** A login shows **Saved** from the moment you add it and
  **Confirmed** once a launch has logged in with it. A confirmed login stays confirmed: closing the game
  early no longer puts it back to "Unconfirmed".
- **STATUS column in plain words:** Running, Logged in, Closed, Closed before logging in, Could not log in.
  The "new login not saved yet" and "Closed before a new login was saved" messages are gone — your login
  is saved when you add it, and it is the one used on every launch.
- "Could not log in" replaces "No login before the time ran out". A login that has worked before is not
  marked "Log in again" because of one failed launch.

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
