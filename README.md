# Xi Rong Project

A single-page, scroll-driven teaser site for **Xi Rong** — a silver-haired figure
who appears in the city of Hai Chang. As you scroll, the background video scrubs
frame-by-frame while a sequence of "classified file" text panels fade in and out,
revealing what is known, what is abnormal, and what cannot be explained — without
spoiling the story.

> *If no body remains, then what exactly is Xi Rong?*

**Release · 24 June 2026**

---

## ✨ Features

- **Scroll-synced video scrubbing** — scrolling drives the video playhead instead of
  time, with smoothing so fast flicks don't snap.
- **7 reveal panels** — hero → who is he → known info → observed abilities →
  anomaly report → "Biological Body: Not Found" → final question & links.
- **Bilingual type** — [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk)
  for Latin paired with [Kanit](https://fonts.google.com/specimen/Kanit) for Thai.
- **Mobile-friendly** — handles browser chrome (`svh`), safe-area insets, and smooth
  touch scrubbing.
- **Analytics** — Google Analytics 4 with scroll-milestone and link-click events.

---

## 🗂 Project structure

```
zeroProject/
├── index.html        # The entire site — markup, styles, and scroll logic
├── video.mp4         # Background teaser video (scrubbed on scroll)
├── whif-logo.png     # WHIF brand logo shown in the whif.io link
└── README.md
```

---

## 🚀 Run it locally

The video scrubbing needs to be served over **HTTP** — opening `index.html` directly
with `file://` will not allow the video to seek.

```bash
# from the project folder
python -m http.server 8000
```

Then open <http://localhost:8000>.

> **Tip:** if you swap `video.mp4`, the browser may keep the cached copy.
> Hard-refresh with `Ctrl + Shift + R` to see the new one.

---

## 🔧 Customizing

Open `index.html` and look for:

- **`--scroll-length`** (CSS, top of the `<style>` block) — how many viewport-heights
  of scrolling drive the full video. Higher = slower, more deliberate scrub.
- **`data-start` / `data-end`** on each `<section class="panel">` — the scroll
  progress range (`0`–`1`) where that text is visible. Leave a gap between one
  panel's `data-end` and the next panel's `data-start` to add a pause where only
  the video plays.
- **`FADE`** (in the `<script>`) — how quickly each panel fades in and out.
- **`VIDEO_SRC`** (in the `<script>`) — path or URL to the video.
- **`window.GA_ID`** (top of `<head>`) — your GA4 property, or `""` to disable.

---

## 📱 Follow / Links

- 🌐 WHIF — <https://www.whif.io/profile/Bonkku>
- 𝕏 (Twitter) — [@NoHoneyBonk](https://x.com/NoHoneyBonk)
- #️⃣ Hashtag — [#XiRongProject](https://x.com/hashtag/XiRongProject)

---

Made by **@NoHoneyBonk**
