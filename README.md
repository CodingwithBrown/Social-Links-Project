# DowntownBrown — Social-Media-Page

## Overview

This is a single-page **link-in-bio** website for the content creator **DowntownBrown** (me). It serves as a centralized hub where fans and followers can find all of the creator's social media profiles and platform links in one place — similar to services like Linktree, but fully custom-built as a self-contained HTML file.

---

## What the Page Displays

When opened in a browser, the page presents:

- **Avatar** — A circular badge displaying the initials "DB" as a placeholder. This can be swapped out for a real profile photo.
- **Name** — "DowntownBrown" displayed as a large, bold heading using the *Bebas Neue* display font.
- **Tagline** — A short subtitle reading *"content creator · streamer"*.
- **Social Icon Bar** — A frosted pill-shaped row of clickable icons for quick access to Twitch, Instagram, TikTok, and YouTube.
- **Main Link Buttons** — Three large, labeled buttons linking directly to the creator's YouTube channel, Twitch stream, and Instagram profile.
- **Footer** — A simple copyright line reading *"© 2026 DowntownBrown"*.

---

## Visual Design

The page uses a dark, cinematic aesthetic built entirely with CSS:

- **Color palette** — Deep navy blues (`#1a1a2e`, `#16213e`, `#0f3460`) give it a moody, night-sky feel.
- **Animated background** — A slowly rotating conic gradient (one full spin every 30 seconds) creates a subtle spotlight effect behind all content.
- **Scanline overlay** — A faint horizontal line pattern adds a retro-screen texture.
- **Grain texture** — An SVG noise filter layered on top gives the page a slight film-grain feel.
- **Frosted glass cards** — Buttons and the social icon pill use semi-transparent backgrounds with a blur effect (`backdrop-filter: blur`) to appear as if floating over the animated background.
- **Typography** — *Bebas Neue* is used for the name/title; *DM Mono* (a monospace font) is used for buttons and body text, giving it a developer/streamer aesthetic.

---

## Animations

Every element on the page fades and slides up into view when the page loads (`fadeUp` keyframe animation). Each element is staggered slightly so they appear one after another in a smooth cascade — avatar first, then the title, tagline, social icons, and finally the link buttons.

On hover, the link buttons:
- Lift slightly upward.
- Display a light shimmer sweep effect across the button.
- Show a colored left-border accent matching the platform (red for YouTube, purple for Twitch, pink for Instagram).

---

## Links & Platforms

| Platform  | Destination |
|-----------|-------------|
| YouTube   | DowntownBrown's YouTube channel |
| Twitch    | `twitch.tv/jaywizgoof` |
| Instagram | `instagram.com/jaydencbrown/` |
| TikTok    | Placeholder — username not yet set |

All links open in a new browser tab.

---

## Security

The page includes a small JavaScript security layer for the social icon buttons:

- A **URL allowlist** restricts navigation to only trusted domains: `twitch.tv`, `instagram.com`, `tiktok.com`, and `youtube.com`.
- All URLs must use **HTTPS** — plain HTTP links are silently rejected.
- New tabs are opened with `noopener, noreferrer` to prevent the new page from accessing or manipulating the original page.
- **Keyboard accessibility** is also supported — the social icons respond to both `Enter` and `Space` key presses, not just mouse clicks.

---

## Responsive Design

The layout adapts to different screen sizes:

- **Desktop** — Centered column, max 440px wide, comfortable spacing.
- **Standard phones (≤ 480px)** — Tighter padding, slightly smaller text and icons, full-width buttons.
- **Very small phones (≤ 360px)** — Further reduced font sizes and spacing.
- **Landscape phones** — Vertical padding is reduced and the avatar shrinks so the full page fits in the shorter viewport.
- **Touch devices** — The hover "lift" effect on buttons is disabled to prevent the raised state from getting stuck after a tap.

---

## File Structure

This is a **single self-contained HTML file** — no external JavaScript files, no separate CSS files, and no build tools required. The only external dependencies are two Google Fonts loaded via a `<link>` tag (Bebas Neue and DM Mono). All icons are rendered as inline SVG masks, meaning no image files are needed either.

To deploy, simply upload `index.html` to any web host or static file server.

---

## Customization Notes

- **Avatar photo** — Replace the "DB" initials `<div>` with an `<img>` tag pointing to a real profile photo.
- **TikTok link** — The TikTok icon currently points to a placeholder URL (`YOUR_TIKTOK_USERNAME`) and needs to be updated with the real username.
- **Adding more links** — Copy any existing `<a class="link-button">` block and update the `href`, `data-platform`, and label text. Add the new domain to the `ALLOWED_DOMAINS` array in the JavaScript if needed.
