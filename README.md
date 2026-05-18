# Hugo Web Novel Reader Template

A fast, highly customizable, and PWA-enabled web novel reading interface built with Hugo. This template is designed specifically for serial fiction, offering readers a premium, app-like experience directly in their browser.

## Features

* **Progressive Web App (PWA):** Readers can install the site to their home screen and read cached chapters offline.
* **Customizable Reader:** Multiple themes (Light, Sepia, Dark, AMOLED, etc.), adjustable font sizes, line heights, and typeface selections.
* **Text-to-Speech (TTS):** Built-in audio player that reads paragraphs aloud with adjustable speed and pitch.
* **Highlighting & Notes:** Readers can highlight text in different colors, add personal notes, and view all their highlights in a centralized modal.
* **Smart Navigation:** Keyboard shortcuts (Left/Right arrows), sticky navigation, and automatic progress tracking.
* **Sino-Scale Converter:** A built-in tool for translating traditional cultivation measurements (Li, Zhang, Shichen) to metric.

## Quick Start Setup

### 1. Repository Configuration
2. 
1. Click the green **Use this template** button at the top of the GitHub repository to create your own copy.
2. Open `hugo.yaml` and update the core site variables:
   * `baseURL: "https://yourusername.github.io/your-repo-name/"`
   * `languageCode: "en-us"`
   * `title: "Your Novel Title"`

### 2. Homepage Metadata & Links
 
Open `content/_index.md` and update the front matter block at the top. This powers your home page description, author/translator credits, and outbound links (like Discord or a Wiki).

### 3. Cover Art & Icons

To personalize your site and ensure the PWA looks correct when installed, replace the default image assets:

* **Book Cover:** Place your main cover image at `static/img/cover.webp`. If you prefer a different format or file name, update the `images:` array in `content/_index.md` to match your new path.
* **Browser Favicons:** Replace `favicon.ico` and `favicon-96x96.png` in the `static/icons/` directory. Replace `favicon.svg` in the `assets/icons/` directory.
* **Apple Icon:** Replace `apple-touch-icon.png` in the `static/icons/` directory so iOS users see your logo.
* **PWA Manifest Icons:** Replace `web-app-manifest-192x192.png` and `web-app-manifest-512x512.png` in the `static/icons/` directory. These are required for the "Add to Home Screen" prompt to display your custom app icon on Android devices.

## How to Add Chapters

**Important:** This template uses a custom script to generate metadata. You **do not** need YAML front matter in your chapter files. 

Drop your markdown files into `content/chapters/`. The files can be named anything (e.g., `01.md`, `chapter-2.md`), but the **first line of the file must be an H1 tag formatted exactly like this**:

```md
# Chapter 1: The Beginning of the End

The rest of your chapter content goes here...
```

The build script will automatically parse the chapter number and title from that heading to generate the Table of Contents, next/previous links, and RSS feed.

## Deployment

This repository includes a pre-configured GitHub Actions workflow (.github/workflows/hugo.yml).

Go to your repository Settings > Pages.

Set the Source to GitHub Actions.

Whenever you push a new chapter to the main branch, GitHub will automatically build the site, generate the chapter metadata, and deploy the update.
