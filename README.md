#  Streamer

A desktop IPTV player for **Windows, Linux and macOS**. Log in with your Xtream Codes account, browse live TV, movies and series — playback runs in **VLC**, controlled straight from the app.

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
| Linux | `vlc` available in `PATH` |

Get VLC at [videolan.org](https://www.videolan.org/vlc/).

> ⚠️ **The 64-bit version of VLC is required.** On Windows, the 32-bit VLC installs to `C:\Program Files (x86)\...`, where the app will not find it — make sure to download the **64-bit installer** from the VLC site.

## Installation

Download the file for your platform from the [latest release](../../releases/latest):

- **Windows**: run `streamer-x.y.z-setup.exe`
- **Linux (AppImage, recommended)**: `chmod +x streamer-x.y.z.AppImage`, then run it
- **Linux (deb)**: `sudo dpkg -i streamer_x.y.z_amd64.deb`
- **macOS**: open the `.dmg` and drag the app into Applications. The build is unsigned — on first start, right-click the app and choose *Open*.

## Updates

The app checks for new releases every few hours and shows a notification with a link to this page — download and install the new version over the old one. Your login, favorites, queue and watch progress are kept.

## Disclaimer

This app is a player/frontend only. It streams whatever your IPTV provider serves — no content is included, hosted or provided.
