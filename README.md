# Streamer

A desktop IPTV player for **Windows, Linux and macOS**. Log in with your Xtream Codes account, browse live TV, movies and series — playback runs in **VLC**, controlled straight from the app.

> ⚠️ **Xtream Codes only.** The app works exclusively with providers that offer the **Xtream Codes API** (server URL + username + password). Plain M3U playlist URLs, Stalker portals or other IPTV formats are **not supported**.

> This repository hosts the **releases** of the app. Grab the latest version from the [Releases page](../../releases/latest).

## Features

- **Live TV, movies & series** — browse by category, search across everything, mark favorites, hide channels or whole categories you don't care about
- **Series browser** — seasons and episodes neatly sorted, with watched checkmarks per episode
- **VLC queue** — enqueue single movies, episodes or whole seasons ("binge queue"); already watched episodes are skipped automatically
- **Now-playing bar** — see what's currently playing, pause/skip, and open the queue from anywhere in the app
- **Watch progress & resume** — the app remembers how far you got. Progress bars in every list, and playback resumes right where you stopped
- **Auto-cleanup** — titles you finished (less than 10 seconds left) are marked as watched and removed from the queue automatically
- **Persistent queue** — your queue survives app and VLC restarts
- **Update notifications** — the app checks this repository and tells you when a new version is available

## Requirements

**VLC media player (64-bit)** must be installed:

| Platform | Expected location |
| --- | --- |
| Windows | `C:\Program Files\VideoLAN\VLC\vlc.exe` |
| macOS | `/Applications/VLC.app` |
| Linux | `vlc` available in `PATH` (e.g. `sudo apt install vlc`) |

Get VLC at [videolan.org](https://www.videolan.org/vlc/).

> ⚠️ **The 64-bit version of VLC is required.** On Windows, the 32-bit VLC installs to `C:\Program Files (x86)\...`, where the app will not find it — make sure to download the **64-bit installer** from the VLC site.

You also need an **IPTV subscription with Xtream Codes credentials** (server URL, username, password) — see the note at the top: other formats like plain M3U are not supported. This app does not provide any content.

## Installation

Download the file for your platform from the [latest release](../../releases/latest):

- **Windows**: run `streamer-x.y.z-setup.exe`
- **Linux (AppImage, recommended)**: `chmod +x streamer-x.y.z.AppImage`, then run it
- **Linux (deb)**: `sudo dpkg -i streamer_x.y.z_amd64.deb`
- **macOS**: open the `.dmg` and drag the app into Applications.
  ⚠️ The macOS build is **not signed yet** (proper signing & notarization
  is planned) — macOS will therefore claim the app *"is damaged and can't
  be opened"*. It isn't damaged; see
  [macOS says the app "is damaged"](#macos-says-the-app-is-damaged-and-cant-be-opened)
  for the one-line fix.

## Updates

The app checks for new releases every few hours and shows a notification with a link to this page — download and install the new version over the old one. Your login, favorites, queue and watch progress are kept.

## Troubleshooting

**macOS says the app "is damaged and can't be opened"**

The app is fine — the macOS build is currently **not signed or notarized**
(that requires a paid Apple developer subscription; it's planned for a
future release). macOS flags every unsigned app downloaded from the
internet with this misleading message.

Until then, remove the quarantine flag once after installing:

```bash
xattr -cr /Applications/bab00nsStreamer.app
```
**Nothing shows up in the queue / playback doesn't start / "Open Vlc" does nothing**

The app most likely cannot find or reach VLC. Check in this order:

1. **Is VLC installed at the expected location?** See the table under *Requirements*. The app does not search anywhere else.
2. **Windows: did you install the 32-bit VLC by accident?** It lives in `C:\Program Files (x86)\VideoLAN\VLC` — the app won't find it there. Uninstall it and install the **64-bit** version.
3. **Quick test:** click *Open Vlc* in the app. If no VLC window appears, it's one of the two points above.

**VLC opens, but items never appear in the queue**

An old VLC window from a previous session may still be running with a stale configuration. Close **all** VLC windows, then restart the app and use *Open Vlc* again.

**Still stuck?**

Attach the app log when reporting the issue:

| Platform | Log file |
| --- | --- |
| Windows | `%APPDATA%\streamer\logs\main.log` |
| macOS | `~/Library/Logs/streamer/main.log` |
| Linux | `~/.config/streamer/logs/main.log` |

## Disclaimer

This app is a **player/frontend only** — comparable to a media player like VLC itself. It does not include, host, index, advertise or provide any content, channels or subscriptions. It only plays whatever the IPTV provider behind the credentials **you** enter serves.

- **You are responsible for what you watch.** Depending on your country, streaming content from providers that do not hold the proper licenses may be **illegal** and can be prosecuted. It is your duty to make sure your IPTV provider is legitimate and properly licensed.
- The developers of this app have **no relationship with any IPTV provider**, do not sell or recommend subscriptions, and assume **no liability** for how this software is used.
- Use this software only with content you are legally entitled to access.

