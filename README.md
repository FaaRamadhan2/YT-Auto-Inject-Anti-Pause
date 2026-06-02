# YT Auto Inject Anti Pause

**YT Auto Inject Anti Pause** adalah Chrome Extension berbasis Manifest V3 untuk YouTube dan YouTube Music. Extension ini menggabungkan fitur visual inject, focus mode, custom theme, wallpaper, ad cleaner, custom CSS, dan anti-pause safe clicker dalam satu package.

> Status: personal-use extension. Built for `youtube.com`, `www.youtube.com`, and `music.youtube.com`.

## Features

### YouTube Inject

- Theme preset
- Custom color override
- Wallpaper from URL
- Local wallpaper upload
- Wallpaper opacity / blur / dim control
- Custom CSS injector
- Hide comments
- Hide sidebar
- Hide Shorts
- Hide home feed
- Hide end screen
- Cinema width mode
- Progress bar theme color
- Popup/menu readability styling

### Anti Pause Safe

- Auto-detects YouTube continue-watching popup
- Auto-clicks positive continue button
- Multi-language button detection
- Works on YouTube and YouTube Music
- Does **not** override `video.play()`
- Does **not** override `video.pause()`
- Does **not** override `document.hidden`
- Does **not** force autoplay after manual pause

### Ad Cleaner

- Normal mode for common YouTube ad containers
- Aggressive mode for stronger cleanup
- Skip-button click attempt when available
- CSS hide + DOM cleanup strategy

## Supported Sites

```txt
https://youtube.com/*
https://www.youtube.com/*
https://music.youtube.com/*
```

## Installation

1. Download or clone this repository.
2. Open Chrome.
3. Go to:

```txt
chrome://extensions
```

4. Enable **Developer Mode**.
5. Click **Load unpacked**.
6. Select the extension folder.
7. Open YouTube.
8. Click the extension icon.
9. Press **Apply** or **Force Inject**.

## Recommended First Run

```txt
1. Remove older versions of the extension.
2. Load the latest folder with Load unpacked.
3. Close all YouTube tabs.
4. Open YouTube again.
5. Click Force Inject.
```

## Storage Notes

Local wallpaper upload is saved through Chrome extension storage. Large images can hit Chrome storage quota. Recommended formats:

```txt
JPG
PNG
WEBP
```

Recommended size:

```txt
<= 2560px longest side
<= 7MB stored data after compression
```

For very large wallpaper files, use a hosted image URL instead of local storage.

## Custom CSS Example

```css
.ytp-play-progress,
.ytp-swatch-background-color,
#progress {
  background: linear-gradient(90deg, red, orange, yellow, lime, cyan, blue, violet) !important;
  box-shadow: 0 0 14px cyan !important;
}
```

## Project Structure

```txt
manifest.json
content.js
popup.html
popup.css
popup.js
LICENSE
README.md
```

## Permissions

```txt
storage
unlimitedStorage
tabs
scripting
```

Host permissions:

```txt
youtube.com
www.youtube.com
music.youtube.com
```

## Safety Design

This extension avoids risky playback hooks. Anti-pause logic only scans visible dialogs and clicks the positive continue button when the popup text matches a known continue-watching pattern.

## Troubleshooting

### Apply does not work

```txt
1. Reload the YouTube tab.
2. Click Force Inject.
3. If still failed, remove old extension versions.
4. Load unpacked again.
```

### Wallpaper does not save

```txt
Use a smaller JPG/PNG/WEBP file or use a wallpaper URL.
```

### YouTube layout looks broken

```txt
1. Switch theme to YouTube Default.
2. Disable Custom CSS.
3. Click Apply.
4. Reload YouTube.
```

## License

This project is licensed under the **GNU General Public License v3.0**.

See [`LICENSE`](./LICENSE) for the full license text.

## Author

Created by **Faa Ramadhan**.
