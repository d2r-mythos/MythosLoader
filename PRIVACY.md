# MythosLoader privacy policy

*Applies to every way of getting MythosLoader: the Microsoft Store, the standalone download from GitHub, and any
installer published by D2R Mythos. Last updated 2026-10-01.*

## The short version

MythosLoader collects nothing about you. It has no account system of its own, no analytics, no advertising and no
telemetry. Everything it keeps stays on your PC.

## What it stores, and where

| What | Where | Protection |
|---|---|---|
| Your settings | `%LocalAppData%\MythosLoader\settings.json` (or next to the program in portable mode) | No secrets in it |
| Your loaders: names, labels, groups, launch options | `%LocalAppData%\MythosLoader\accounts.json` | — |
| Saved Battle.net logins (login tokens, never passwords) | inside `accounts.json` | Encrypted with Windows DPAPI for your Windows user |

MythosLoader never asks for, sees or stores your Battle.net password. You type it on Battle.net's own page, and
MythosLoader only receives the resulting login token. Uninstalling the program does not delete this folder; delete
`%LocalAppData%\MythosLoader` yourself to remove everything.

## What it sends over the network

- **Battle.net's login page**, when you choose to log in inside the app. That page is Blizzard's, and Blizzard's own
  privacy policy applies to it.
- **GitHub**: the optional lowHD mod, downloaded only when you ask for it. The standalone version also checks for a
  newer release when it starts (you can turn that off) and downloads it when you press Update; the Microsoft Store
  version leaves updates to the Store. GitHub sees your IP address, as with any download.

Nothing is sent to D2R Mythos. There is no server of ours that MythosLoader talks to.

## What it changes on your PC

Before each launch it writes the account's login into the game's own login slot in the registry, which the game
reads. It renames game windows, and with intro skip on it adds a small `MythosIntroSkip` folder to the game's `mods`
folder. Details: [README — Security and privacy](README.md#-security-and-privacy).

## Children

MythosLoader is a tool for players of Diablo II: Resurrected and is not directed at children.

## Contact

Questions about this policy: the [D2R Mythos Discord](https://discord.com/invite/d2rmythos), or a private report as
described in [SECURITY.md](SECURITY.md).
