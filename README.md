> **This repo now just mirrors compiled installers for the auto-updater.**
> Source code, issues, discussions, and downloads all live at
> **[github.com/Haris357/Layer](https://github.com/Haris357/Layer)** — head
> there instead.

<div align="center">

# Layer

**A quiet layer of widgets on your desktop.**

Drop notes, clocks, weather, media controls, a shelf, and more straight onto your wallpaper — pinned to the desktop, out of your way until you want them.

[**⬇️ Download for Windows**](https://github.com/Haris357/Layer/releases/latest/download/Layer-Setup.exe) · [**🌐 Website**](https://layer-desktop.web.app) · [**🖼️ Space Gallery**](https://layer-desktop.web.app/spaces) · [**📦 All releases**](https://github.com/Haris357/Layer/releases)

</div>

---

This is the **public release channel** for Layer — signed Windows installers and the auto‑update manifest are published here on every release.

## What is Layer?

Layer turns your desktop into a calm, customizable canvas. Add widgets, arrange them however you like, switch between **Spaces** (multiple layouts), and let it sit quietly behind your apps. It never steals focus — it's pinned to the desktop.

**Widgets:** Notes · Sticky notes · Shelf · Greeting · To‑do · Pomodoro · Clock · World clock · Calendar · Countdown · Search · App launcher · Clipboard history · Web embed · Now Playing · Notifications · Unit converter · Links · Image · Video · Gallery · Weather · System stats · Disk Info

**Also:** a built‑in **screensaver** (Ambient / Minimal / Quote), **Spaces** with a hot‑corner and peek gesture, **Freewrite** mode, ambient focus sounds, wallpaper‑reactive theming, and full **multi‑monitor** support.

## Install

1. [**Download `Layer-Setup.exe`**](https://github.com/Haris357/Layer-releases/releases/latest/download/Layer-Setup.exe) (always the latest build).
2. Run it — Layer installs and launches, and can start with Windows (toggle in **Settings**).
3. Right‑click the **tray icon** for the menu, or hover the top pill to add widgets.

**Updates are automatic.** Layer checks for new versions, downloads them quietly in the background, and lets you **Relaunch** when you're ready — or grab the latest installer here anytime.

**Requirements:** Windows 10/11 (64‑bit).

---

## Is it safe?

Short answer: yes. Here's the honest detail, since running any `.exe` deserves caution.

- **VirusTotal flags (2 of ~70 engines):** a couple of heuristic/ML "behaviour" engines (e.g. Trapmine, SecureAge) flag Layer. These are well known for false‑positives on small, unsigned indie apps. They aren't matching a malware signature — they react to two things Layer legitimately does: a **global hotkey** (so `Ctrl+Shift+N` quick‑capture works anywhere, which is a keyboard hook) and a **transparent full‑screen desktop overlay** (which is literally what Layer is). **Microsoft Defender and the other ~68 engines pass it clean.**
- **Built on WebView2:** Layer uses [Tauri](https://tauri.app) — a tiny Rust core plus a web UI rendered by **Microsoft's WebView2** (the same engine behind Edge, shipped and updated by Microsoft). It does not bundle a browser or anything hidden.
- **Runs as a normal app:** no drivers, no services, no system‑level changes. It only writes to your own `%AppData%\Layer` folder and **uninstalls cleanly**.
- **Network:** only the public APIs for the features you use — weather (open‑meteo), currency rates (frankfurter), the Space gallery, and GitHub for updates. **No telemetry, no tracking.**

---

## Changelog

### v1.10.0 — 🎯 Quick Capture now works over any app, plus Hide All and monitor profiles
- 🐛 **Quick Capture (Ctrl+Shift+N) now pops up over whatever you're using** — it was rendering behind other windows instead of on top, so it only ever seemed to work with nothing else open. Fixed.
- 🙈 **New: Hide everything, instantly** — `Ctrl+Shift+H` hides the whole canvas in one press (handy in public or before a screen share); press again to bring it back. Remappable in Settings → Shortcuts.
- 🖥️ **New: Layer remembers your setup** — switch between your office multi-monitor rig and your laptop, and Layer automatically switches to whichever Space you last used with that exact monitor setup. Fully automatic, nothing to configure.
- 📏 **New: Quick size presets** — right-click any widget for Small/Medium/Large sizing, scaled sensibly for that widget type.
- ✨ Reduced a visual flicker when adding new widgets.
- 🧹 Removed cloud sync and "export canvas as image." Everything now stays local — one less thing to configure, and one less service Layer depends on.


### v1.9.0 — 🗓️ Week start, shortcut fixes & a context-menu fix
- 🗓️ **Choose your week start** — the Calendar can now start the week on **Monday or Sunday**. Set it in the Calendar widget's settings gear; the month grid, week view and headers all follow.
- ⌨️ **Rebinding shortcuts actually works** — while you're setting a new shortcut, Layer now frees up its keys so any combo (even Ctrl+Shift+S/N/E) is captured correctly. The Shortcuts screen also explains how it works.
- 🖱️ **Context menu closes properly** — the right-click widget menu now closes when you click anywhere on the desktop, not just on another widget.


### v1.8.0 — ⌨️ Remap or disable any keyboard shortcut
- ⌨️ **Rebind every shortcut** — the edit-mode toggle, Quick capture, Cycle spaces and Preview screensaver can all be set to whatever key combo you like, in **Settings → Shortcuts**.
- 🚫 **Turn shortcuts off** — disable any of the secondary shortcuts so they no longer clash with other apps (e.g. Ctrl+Shift+S vs "Save As"). A disabled shortcut fully frees its keys system-wide.
- 🧠 **Your bindings stick** — custom shortcuts now persist correctly across restarts.


### v1.7.2 — 🩹 Fix top-bar flicker
- ✨ **No more flicker** — the top bar no longer strobes/blinks while the widget menu is expanded (it was most visible in dark mode). The open/close animation is unchanged.


### v1.7.1 — 🌍 Fuller translations & localized dates
- 🗓️ **Localized dates everywhere** — the Clock, World Clock and Calendar now show day and month names in your selected language.
- 🖱️ **Translated right-click menu** — the widget context menu (Duplicate, Bring to front, Color, Theme…) is now fully translated.
- 💬 **Everything else translated too** — toasts, notifications, the command palette, dialogs, cloud-sync messages and the screensaver now follow your language. If something was still showing in English, it shouldn't be anymore.


### v1.7.0 — 🌍 Layer speaks your language
- 🌍 **9 languages** — Layer's whole interface is now translated into English, Español, Français, Deutsch, Português (BR), Italiano, Русский, 简体中文 and 日本語. Pick yours in **Settings → General → Language**; it switches instantly.
- 💬 **Consistent tooltips everywhere** — every interactive button across all widgets now shows the same clean hover tooltip, so nothing is a mystery.
- 🧹 **Send-to-back / bring-to-front fixed** — widget layering now always behaves correctly; a widget can never get "stuck" behind the desktop again (and any layout already affected heals itself).
- 🩹 **Cleaner uninstall** — uninstalling Layer now also removes its screensaver, so it never lingers after the app is gone.


### v1.4.2 — Multi‑monitor, new widgets & stability
- 🖥️ **Multi‑monitor, sorted** — the pill & menu bar always sit on your primary screen (never the gap between mismatched monitors), **Settings is draggable**, all modals/palettes open on a real screen, and the desktop **auto‑extends to a monitor you plug in** (no restart).
- 🗄️ **Shelf** widget — drag any file/image/video onto it to stash it (hidden folder) with thumbnails; open, reveal, or remove anytime.
- 👋 **Greeting** widget — an ever‑changing greeting with your name (100+ lines, time‑of‑day aware) in Classic / Serif / Gradient styles.
- 💽 **Disk Info** widget — pick any drive for capacity, type (SSD/HDD), filesystem, and **live read / write / active** like Task Manager.
- 🎚️ **Now Playing rebuilt** — reliable, self‑healing media engine that can never freeze.
- 🧊 **Stability** — app‑wide freeze hardening; **quitting from the tray is instant**; Stats' combined drives now labelled **Storage**.

### v1.4.1 — A smoother update experience
- Updates **download quietly in the background** with live progress on the toast.
- When ready, **you choose when to restart** — Relaunch or Later. No more surprise "not responding" restarts.

### v1.4.0 — Spaces, Freewrite & calmer focus
- ✨ **Spaces** — multiple widget layouts; switch with `Ctrl+Shift+E` or the top‑left hot corner. **Peek** at your desktop with `Ctrl+Shift+` `` ` ``.
- 🖊️ **Freewrite** in Notes — timed, no‑backspace writing with a live word count.
- 🎧 **Ambient sounds** in Pomodoro (rain/ocean/forest/fireplace), gentle UI sounds, and rock‑solid background timers.
- 🌤️ **Wallpaper‑accent theming**, ambient/weather background effects, and **Use my location** in Weather.
- 🖥️ **Screensaver** styles (Ambient/Minimal/Quote) with live weather + now‑playing, per‑monitor.
- 📋 **Smart Clipboard** formatting (links, paths, code, JSON, colors…), new **Web embed** widget, redesigned **Calendar** week view.
- 💅 Silky‑smooth typing, custom tooltips, tabbed Settings with a Shortcuts section, per‑widget opacity.

### v1.3.2 — Interactive toasts
- One‑tap **update**, **undo** deletes, handy follow‑up actions, and calendar/focus reminders — all from the toast.
- Toasts no longer clip behind the taskbar; smoother animation.

### v1.3.1 — Screensaver fix
- The screensaver now fills the **entire screen** on high‑DPI / scaled displays.

### v1.3.0 — Screensaver & smarter location
- ✨ Layer can run as your **Windows screensaver** — clock, date, weather, now‑playing over an ambient backdrop. Toggle in Settings; preview with `Ctrl+Shift+S`.
- 📍 Weather gains **Use my location** with accurate system‑based location.

### v1.2.0 — Notifications, calendar & more widgets
- 🆕 **Pomodoro**, **Sticky notes**, **Inbox** + `Ctrl+Shift+N` quick‑capture, **Clipboard history**.
- 🔔 **Notifications** centre, 📅 full **Calendar** (month/week/day, recurring events), and 🖥️ **multi‑monitor** canvas.
- 🪟 **Desktop‑pinned** — Layer stays attached to the desktop and never steals focus.

### v1.1.0
- Template sharing: ZIP export/import + publish to the Space Gallery.

### v1.0.0
- First public release of Layer. 🎉

---

<div align="center">

Made with care. · [layer‑desktop.web.app](https://layer-desktop.web.app)

</div>
