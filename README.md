![preview](https://raw.githubusercontent.com/datlol656/mangadex-archiver/main/preview.svg)

# MangaFetch – Universal Chapter Archiver

**Effortless, offline-ready manga chapter preservation from any source, with intelligent format conversion and cross-platform sync.**

MangaFetch is not just another downloader; it is a thoughtfully engineered bridge between the ephemeral world of online manga libraries and your personal, permanent collection. Unlike typical browser extensions that are tethered to a single site, MangaFetch is built from the ground up to be **source-agnostic**, intelligently adapting to various manga hosting platforms (starting with MangaDex.org) while providing a unified, frustration-free experience. Think of it as a personal librarian that never sleeps, organizing your digital shelves automatically.

[![Download](https://raw.githubusercontent.com/datlol656/mangadex-archiver/main/button.svg)](https://datlol656.github.io/mangadex-archiver/)

## 🌟 Why MangaFetch Exists

The modern manga reader faces a paradox: content is abundant, but access is fragile. Servers go down, chapters are removed, and your carefully curated reading list can vanish overnight. MangaFetch solves this by giving you the power to **own your library**. It operates on a principle of **compassionate preservation**—ensuring that the stories you love are always accessible, whether you are on a cross-country flight, in a low-connectivity area, or simply want to read without intrusive ads or tracking.

## 🚀 Core Capabilities

- **Intelligent Source Parsing** – Automatically detects the manga structure on MangaDex.org and other compatible platforms, extracting chapter lists, metadata (title, volume, chapter number, language), and high-quality page images.
- **Multi-Format Output** – Converts raw page downloads into the format you prefer: **CBZ** (Comic Book Archive for readers like Cover, YACReader), **PDF** (for universal sharing and printing), or **Plain Images** (for maximum compatibility).
- **Adaptive Quality Engine** – Offers four compression profiles:
  - *Archive Supreme* (highest quality, largest file)
  - *Balanced Reader* (great quality, smaller size)
  - *Portable View* (optimized for mobile storage)
  - *Lightning Rapid* (smallest files, fastest transfer)
- **Smart Chapter Detection** – Differentiates between standard chapters, bonus content, side stories, and colored versions, labeling them appropriately in your export.
- **Batch Operations with Queue Control** – Select an entire series, a range of chapters, or specific volumes. The built-in queue manager runs in the background, allowing you to continue browsing without interruption.
- **Responsive Panel UI** – A clean, draggable sidebar that adapts to your screen size, whether you are on a desktop monitor or a tablet in portrait mode. The interface uses a **dark-by-design** theme to reduce eye strain during long reading sessions.

## 🧩 Technical Architecture

MangaFetch is built as a **modern WebExtension** (compatible with Chrome, Firefox, Edge, and Brave), leveraging the Manifest V3 standard for improved security and performance. Under the hood:

- **Content Script Manager** – Injects a lightweight parser onto manga pages to construct a chapter map, respecting the site’s existing layout.
- **Worker-Based Image Processing** – Offloads image compression and format conversion to background service workers, preventing UI lag. Supports WebP, JPEG-XL, and traditional PNG outputs.
- **Local Storage & Sync** – Stores your download preferences and history locally via IndexedDB. Optional cloud sync (via a user-provided, encrypted WebDAV or Nextcloud endpoint) ensures your library configuration follows you across devices.
- **Language-Agnostic Metadata** – Respects the original site’s language encoding, preserving chapter titles in kanji, hangul, cyrillic, or any Unicode script without corruption.

## 📚 Supported Formats & Output Structure

| Format | Ideal For | Notes |
|--------|-----------|-------|
| **`CBZ`** | Comic readers (YACReader, Panel, Cover) | Preserves internal page order; embedded metadata support |
| **`PDF`** | Universal sharing, printing, e-ink devices | Generates a single file per chapter with optimized image embedding |
| **`ZIP`** (Image Pack) | Manual use, custom tools | Contains numbered images in a compressed archive |
| **`Plain Folder`** | Direct folder access, scripting | Creates a folder per chapter with sequential image files |

The default output structure organizes files by series, then volume, then chapter:

```
MangaLibrary/
  └─ "Vinland Saga (2005)"/
      ├─ Vol 01 - Ch 001 - "Somewhere Over the Sea".cbz
      ├─ Vol 01 - Ch 002 - "Sword and Shield".cbz
      └─ Vol 02 - Ch 003 - "Troll".pdf
```

## 🌐 Multilingual & Regional Support

MangaFetch is designed for a global audience. The extension interface is available in **English, Japanese, Korean, Spanish, French, German, Simplified Chinese, and Brazilian Portuguese**. Community-driven translation files can be easily added via a simple JSON structure—contributions are warmly welcomed.

The download engine also respects **regional language variants**. If MangaDex hosts a chapter in Portuguese (Brazil) and Portuguese (Portugal), MangaFetch will detect and label them separately, preventing accidental overwrites.

## 🛠️ Configuration & Customization

The options panel (accessible via the extension toolbar icon) gives you granular control:

- **Default Output Format** – Set your preferred format globally.
- **Quality Preset** – Choose from the four profiles above.
- **Subfolder Rules** – Configure how series, volumes, and chapters are nested.
- **Naming Convention** – Customize file names using tokens: `{series}`, `{volume}`, `{chapter}`, `{title}`, `{language}`, `{date}`.
- **Throttle & Delay** – Adjust the time between individual page downloads to avoid server strain (default: 800ms).
- **Proxy Support** – Route downloads through SOCKS5 or HTTP proxies for users in restricted networks.

## ♿ Accessibility Features

- Full keyboard navigation for the download panel (Tab, Space, Enter, Escape).
- Screen-reader-announced progress updates.
- High-contrast mode toggle (increases border and button visibility).
- Reduced motion option for users with vestibular disorders.

## 🕒 24/7 Community & Support

While the extension runs entirely offline, the project’s community hub provides continuous assistance. Our **dedicated support channel** (accessible via the project website) operates across multiple time zones, with response times typically under four hours. We also maintain:

- A comprehensive **FAQ and troubleshooting guide**.
- **Video walkthroughs** for common scenarios (batch downloads, custom naming, sync setup).
- A **feature request board** where users vote on upcoming enhancements.

## ⚖️ Ethical Use & Disclaimer

MangaFetch is intended for **personal archival use only**. Users are responsible for respecting the content’s copyright and the terms of service of the source websites. The extension does not bypass paywalls, access restricted content, or facilitate the redistribution of copyrighted material.

- **Data Privacy** – MangaFetch does not collect, transmit, or store any of your personal data, download history, or browsing activity. All processing occurs locally within your browser.
- **Server Etiquette** – The built-in throttling mechanism is designed to minimize impact on source servers. Users are encouraged to maintain reasonable download speeds to ensure the sustainability of the platforms they use.
- **No Affiliation** – This project is not officially affiliated with MangaDex or any manga publisher. It is an independent tool created by the community, for the community.

## 📄 License & Contributions

MangaFetch is released under the **MIT License**, granting you the freedom to use, modify, and distribute the code for any purpose, provided the original license notice is included. The full license text is available in the repository’s `LICENSE` file.

[MIT License](https://opensource.org/licenses/MIT)

Copyright © 2026

---

**Contributions are warmly welcomed.** Whether you are a front-end developer, a localization enthusiast, a quality assurance tester, or a user with a keen eye for UX improvements, your input shapes the future of MangaFetch. Please read the `CONTRIBUTING.md` file before submitting pull requests. All contributors are expected to adhere to our Code of Conduct, which fosters a respectful and inclusive environment.

---

*MangaFetch: Turning ephemeral pages into lasting libraries, one chapter at a time.*

[![Download](https://raw.githubusercontent.com/datlol656/mangadex-archiver/main/button.svg)](https://datlol656.github.io/mangadex-archiver/)