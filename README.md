# PRMPT - Fashion Archive Landing Page

A full-screen, scroll-driven fashion landing page for the brand "prmpt" built with React 19, TypeScript, Vite, Tailwind CSS v4, and Motion/Framer Motion.

## Features

- **Hero Phase**: Full-viewport video background with overlaid UI (logo, navigation, product info, custom cursor)
- **Gallery Phase**: Scattered grid of product images with dynamic scaling based on viewport position
- **Desktop Video Interaction**: Cursor-based video scrubbing with dead zone
- **Mobile Auto-Play**: Alternating video playback for touch devices
- **Smooth Scroll Animations**: RAF-driven scroll effects without using scroll events
- **Responsive Design**: Mobile (< 640px), Tablet (640-1024px), Desktop (≥ 1024px)

## Tech Stack

- **React 19** + **TypeScript**
- **Vite 6** with `@vitejs/plugin-react`
- **Tailwind CSS v4** via `@tailwindcss/vite`
- **Motion (Framer Motion) 12** for entry animations
- **Font**: Inter Tight (weight 500) from Google Fonts

## Installation

```bash
npm install
```

## Development

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

## Build

```bash
npm run build
```

## Project Structure

```
src/
  ├── components/
  │   ├── CustomCursor.tsx      # Desktop custom cursor
  │   ├── Logo.tsx               # Animated logo
  │   ├── Caption.tsx            # Introductory caption
  │   ├── Header.tsx             # Top navigation
  │   ├── ProductInfo.tsx        # Product details with symbol
  │   ├── ViewButton.tsx         # CTA button
  │   ├── VideoContainer.tsx     # Video player with interactions
  │   ├── Gallery.tsx            # Scrollable gallery grid
  │   ├── GalleryCard.tsx        # Individual gallery card
  │   ├── Overlay.tsx            # White overlay
  │   └── Footer.tsx             # Footer links
  ├── App.tsx                    # Root component
  ├── main.tsx                   # Entry point
  └── index.css                  # Global styles

vite.config.ts                   # Vite configuration
tailwind.config.ts               # Tailwind configuration
tsconfig.json                    # TypeScript configuration
package.json                     # Dependencies
```

## Design Principles

- All text overlays use `mix-blend-mode: exclusion` for visibility on both light and dark backgrounds
- `pointer-events-none` on all overlaid UI elements to prevent interference with interactions
- Gallery cards scale in/out based on their vertical position using requestAnimationFrame
- Videos hidden once scroll passes first viewport height
- Staggered entry animations for UI elements (0s, 0.15s, 0.3s, 0.45s delays)

## Browser Support

Works on all modern browsers that support:
- CSS Grid
- CSS Custom Properties
- requestAnimationFrame
- ES2020+ JavaScript features
