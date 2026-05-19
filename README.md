# Palette Selector

> The full source code lives in a private repository. This repo exists to share the project's scope, design decisions, and screenshots with recruiters and hiring managers. Access to the private repo can be granted on request.

## Tech stack

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-5.0-092E20?style=for-the-badge&logo=django&logoColor=white)
![Pillow](https://img.shields.io/badge/Pillow-image%20processing-11557C?style=for-the-badge)
![Playwright](https://img.shields.io/badge/Playwright-headless%20chromium-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-database-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-vanilla-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

## Screenshots

<!-- Replace with real captures: see screenshots/README.md for the suggested shot list. -->

| Image extraction | Website extraction |
| --- | --- |
| ![Image generator](screenshots/image-generator.png) | ![Website generator](screenshots/website-generator.png) |

| Random palette (26 named moods) | Contrast checker |
| --- | --- |
| ![Random generator](screenshots/random-generator.png) | ![Contrast checker](screenshots/contrast-checker.png) |

## Features

- **Four generators**
  - **Image** — upload any image; dominant colors are extracted via Pillow's median-cut quantization.
  - **Website** — paste a URL; the live page is rendered in headless Chromium (Playwright), screenshotted, then fed through the image pipeline so the palette reflects what users actually see, including applied CSS and dark-mode rules.
  - **Random** — 26 named "moods" (pastel, neon, ocean, sunset, cyberpunk, matcha, midnight, …) defined as HSL hue/saturation/lightness windows for predictable aesthetics.
  - **Custom** — a JS canvas for hand-picking colors.
- **Lock-and-regenerate** — pin any colors in the palette and regenerate the rest around them, preserving positions.
- **Accessibility**
  - WCAG contrast checker built into the palette.
  - Colorblind simulation overlay (protanopia / deuteranopia / tritanopia).
- **Color tools** — blend between two palette colors; sort by hue, lightness, frequency, or RGB channel.
- **Accounts** — sign up, save palettes as favorites, light/dark/system theme with both server-side preference (for signed-in users) and cookie fallback (for guests).
- **Defensive** — the website extractor rejects non-`http(s)` URLs and hostnames that resolve to private, loopback, link-local, or multicast addresses (SSRF guard).

Built by **Fotiana** — get in touch if you'd like a walkthrough or access to the private source repo.
