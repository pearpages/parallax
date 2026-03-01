# Parallax Playground

A small static webpage that demonstrates a simple parallax scrolling effect using only HTML and CSS.

The page is intentionally lightweight: random text blocks + full-screen image sections to showcase depth while scrolling.

## Project Structure

- `index.html`: Page markup and content sections
- `styles.css`: Visual styling, layout, and parallax behavior

## How It Works

### 1. Layout in `index.html`

The page alternates between:

- Image sections (`.hero`, `.strip`, with `layer-*` classes)
- Text sections (`.text-panel`)

This creates long vertical scroll space so the parallax effect is easy to see.

### 2. Parallax Effect in `styles.css`

The core effect comes from this rule on image sections:

- `background-attachment: fixed`

For `.hero` and `.strip`, the background image stays fixed relative to the viewport while content scrolls, producing the parallax illusion.

Supporting rules:

- `background-size: cover` keeps each image filling its section
- `background-position: center` keeps framing consistent
- `min-height: 100vh` makes each parallax section full-screen

### 3. Layer Images

Each parallax section gets a different background image via:

- `.layer-1`
- `.layer-2`
- `.layer-3`

Swap these URLs to change the visual style.

### 4. Readability Overlay

Each parallax section includes an `.overlay` element with a dark gradient. This improves text contrast on top of photos.

### 5. Mobile Behavior

On smaller screens (`max-width: 900px`), the CSS changes to:

- `background-attachment: scroll`

This is a compatibility/performance fallback, since fixed backgrounds can behave inconsistently on some mobile browsers.

## Run Locally

npm static server (if you install one)

```bash
npm install --save-dev serve
npx serve .
```

## Customize Quickly

- Replace random copy in `index.html`
- Change image URLs in `.layer-*` classes
- Add/remove `.text-panel` and `.strip` sections for different scroll rhythm
- Adjust colors via CSS variables in `:root`

## Notes

This is a demo/static showcase, not a production app. It has no build step and no JavaScript.
