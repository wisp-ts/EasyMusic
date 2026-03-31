# 🎧 EasyMusic

A sleek, browser-based music player powered by the YouTube Data API.
Search, queue, and play music with a modern UI — no downloads, no installs.

## 🚀 Features

- 🔍 Search music using YouTube
- 📈 Trending songs by region
- ❤️ Favorites system
- 📂 Custom playlists
- 🎶 Queue system (like Spotify)
- 🔁 Shuffle + Repeat modes
- 🔊 Volume + seek controls
- 💾 Local storage (auto-save everything)
- ⚡ Fast, single-file app (no backend)

## 🖥️ Demo / Usage

Just open the HTML file:

```sh
open index.html
```

Or host it anywhere (GitHub Pages recommended).

## 🔑 Setup (IMPORTANT)

You need a **YouTube Data API v3** key.

**Steps:**

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Enable **YouTube Data API v3**
3. Create an API key
4. Paste it into your config:

```js
window.EASYMUSIC_CONFIG = {
  apiKey: "YOUR_API_KEY_HERE"
};
```

## 🧠 How It Works

- Uses YouTube API for:
  - Search results
  - Trending music
  - Video metadata (duration, etc.)
- Uses YouTube IFrame Player for playback
- Stores all user data in `localStorage`
- No backend required

## 📁 Project Structure

```
EasyMusic/
├── index.html   # Main app (ALL-IN-ONE)
├── README.md    # This file
```

This project is intentionally built as a single-file app for portability.

## 🔥 Bookmarklet (Open in about:blank)

You can launch EasyMusic in a clean `about:blank` tab for a stealth / minimal look.

### 👉 Method 1 (Best — hosted version)

Create a bookmark and paste this as the URL:

```js
javascript:(function(){
  const url="https://easy-music-weld.vercel.app/";
  const win=window.open('about:blank','_blank');
  fetch(url)
    .then(r=>r.text())
    .then(html=>{
      win.document.open();
      win.document.write(html);
      win.document.close();
    });
})();
```

### 👉 Method 2 (Local / inline version)

```js
javascript:(function(){
  const win=window.open('about:blank','_blank');
  const html=`paste index.html here`;
  win.document.open();
  win.document.write(html);
  win.document.close();
})();
```

## ⚙️ Settings

Built-in settings system includes:

- Region selection
- Search filters (duration, safety)
- Default sorting
- Compact mode
- Autoplay toggle
- Cache control

## 💾 Data Storage

All data is saved locally:

- Favorites
- Playlists
- Queue
- Settings

No account needed.
