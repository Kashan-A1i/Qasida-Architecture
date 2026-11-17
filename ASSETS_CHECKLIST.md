# Showcase Visual Assets Checklist

To make the public `README.md` visually complete, capture the following **1 short screen recording GIF** and **4 targeted screenshots** from your running local or production instance of **Qasida**, and place them inside the `_showcase/assets/` directory using the exact filenames below.

> **Privacy Reminder Before Capturing:**
> - Ensure your browser URL bar is either cropped out or only shows `localhost:8000` or your public domain.
> - Do not capture any Django Admin screens that display real user email addresses or internal credentials.

---

## 1. End-to-End Walkthrough GIF (`assets/demo.gif`)

- **Target Filename:** `./assets/demo.gif`
- **Recommended Resolution:** `1280x720` (or `1080x675`), 15–20 seconds, ~12–15 FPS.
- **Exact Flow to Record:**
  1. Start on the **Home (`/`)** page showing the full list of Ginans and language pills (`All`, `Urdu`, `Persian`, `Arabic`, `Gujarati`, etc.).
  2. Type a multi-word query into the rounded search bar (e.g., a poet name + language) to demonstrate the **500ms debounced HTMX live filtering** without a page reload.
  3. Click into a Ginan card to show the instant **HTMX swap** into the **Ginan Reader (`/ginan/<id>/`)**.
  4. Click the **Roman / Arabic** toggle pills at the top of the lyrics box to switch between centered Roman script and RTL Arabic/Persian/Urdu script, then scroll slightly to reveal the embedded **Listen on YouTube** player.

---

## 2. Static Screenshots (`assets/*.png`)

### Screenshot 1: Home Search & Language Category Pills
- **Target Filename:** `./assets/01-home-search-filter.png`
- **Route:** `/` (Home)
- **What to Show:**
  - The sticky top navigation bar with the **Qasida** logo, navigation links (`Home`, `Trending`, `About`, `Upload a Ginan`), and profile avatar.
  - The sticky search input bar (`"Search ginans, poets or language..."`) with horizontal language filter pills (`All` highlighted in dark gray, alongside language category buttons) and the swipeable Ginan cards below.

### Screenshot 2: Dual-Script Lyrics Reader & YouTube Embed
- **Target Filename:** `./assets/02-dual-script-reader.png`
- **Route:** `/ginan/<id>/` (Pick a Ginan that has **both** `lyrics_roman` and `lyrics_arabic` populated, plus a `youtube_video_id`).
- **What to Show:**
  - The Ginan title, clickable cyan Poet link (`Poet: ...`), the **Roman / Arabic** pill toggle buttons, the clean white lyrics card (either showing the RTL nastaliq/Arabic script or a side-by-side composite), and the rounded **Listen on YouTube** player underneath.

### Screenshot 3: Multi-Page AI Lyrics Scanner Modal in Action
- **Target Filename:** `./assets/03-ai-lyrics-scanner.png`
- **Route:** `/upload/` (Click the **"Scan Lyrics"** camera button to open `#scan-modal`).
- **What to Show:**
  - Select 2–3 sample page photos of poetry so the **"Selected Pages (3)"** preview grid is visible inside the modal with `Page 1`, `Page 2`, `Page 3` badges and the cyan **"Extract Lyrics (3 pages)"** button ready to click.
  - *(Optional alternative)*: Capture the upload form immediately **after** extraction completes, showing the amber **AI Disclaimer banner** (`"AI-extracted lyrics may contain errors..."`) and the populated lyrics textarea.

### Screenshot 4: Poet Profile or Contributor Profile & Moderation View
- **Target Filename:** `./assets/04-contributor-profile.png`
- **Route:** `/poet/<id>/` **or** `/profile/`
- **What to Show:**
  - Either the **Poet Profile (`/poet/<id>/`)** showing the poet header card, total Ginans count badge, and list of works by that poet; **or** the **Contributor Profile (`/profile/`)** showing `@Username`, `"Ginan Contributor"`, and the `"My Uploads"` section.

---

## Quick Verification After Adding Files

Once you drop the files into `_showcase/assets/`, your folder should look like this:

```text
_showcase/
├── README.md
├── ARCHITECTURE.md
├── ASSETS_CHECKLIST.md
├── SETUP_PUBLIC_REPO.md
└── assets/
    ├── .gitkeep
    ├── logo.png            (already included)
    ├── demo.gif
    ├── 01-home-search-filter.png
    ├── 02-dual-script-reader.png
    ├── 03-ai-lyrics-scanner.png
    └── 04-contributor-profile.png
```
