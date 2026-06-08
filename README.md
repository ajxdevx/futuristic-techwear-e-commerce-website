# Futuristic Techwear E-Commerce Website

A cinematic, animation-driven techwear storefront built with **Next.js 16**, **GSAP**, **Three.js**, and **Lenis**. NRMLSS is a fully interactive front-end experience — modular product catalog, smooth page transitions, WebGL dot-matrix effects, and a client-side shopping cart — designed to feel like browsing garments from a near-future archive.

![Next.js](https://img.shields.io/badge/Next.js-16-black?style=flat-square&logo=next.js)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=white)
![GSAP](https://img.shields.io/badge/GSAP-3.14-88CE02?style=flat-square)
![Three.js](https://img.shields.io/badge/Three.js-0.158-white?style=flat-square&logo=three.js&logoColor=black)

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Pages & Routes](#pages--routes)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Available Scripts](#available-scripts)
- [Key Components](#key-components)
- [State Management](#state-management)
- [Animations & Interactions](#animations--interactions)
- [Product Catalog](#product-catalog)
- [Customization](#customization)
- [Deployment](#deployment)
- [License](#license)

---

## Overview

NRMLSS presents a minimalist techwear brand through a dark, signal-heavy visual language. The site combines editorial storytelling with e-commerce functionality: users can browse 30+ conceptual garment units, filter by tag and color, add items to a persistent cart, and explore brand narrative pages with scroll-driven animations and shader-based backgrounds.

The experience is optimized for immersion — a branded preloader on first visit, flickering monospace copy, peel-reveal image transitions, and buttery smooth scrolling via Lenis.

---

## Features

### E-Commerce
- **30 techwear products** with name, price, color, size options, tags, and descriptions
- **Wardrobe archive** with animated filter by tag (`Deform`, `Sheerform`, `Functionary`) and color
- **Featured products** randomly selected on the home page
- **Shopping cart** powered by Zustand — add, remove, quantity tracking, and subtotal
- **Product detail views** with add-to-cart integration

### Visual & Motion Design
- **GSAP-powered animations** — ScrollTrigger, SplitText, timeline sequences
- **WebGL dot-matrix shader** hero background (Three.js)
- **Page transition router** with animated route changes
- **Preloader** with first-visit detection and branded intro sequence
- **Marquee banners**, peel-reveal sections, and parallax CTA blocks
- **3D Orb gallery** on the Lookbook page
- **Smooth scroll** via Lenis with mobile/desktop tuned settings

### Navigation & Layout
- Full-screen **animated menu** with text scramble effects
- Responsive layout with mobile-aware scroll and menu behavior
- Custom typography: **Koulen**, **Host Grotesk**, **DM Mono**

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | [Next.js 16](https://nextjs.org/) (App Router) |
| UI | [React 19](https://react.dev/) |
| Styling | CSS Modules + global CSS |
| Animation | [GSAP 3](https://gsap.com/) + `@gsap/react` |
| 3D / Shaders | [Three.js](https://threejs.org/) |
| Smooth Scroll | [Lenis](https://lenis.darkroom.engineering/) |
| State | [Zustand](https://zustand.docs.pmnd.rs/) |
| Icons | [React Icons](https://react-icons.github.io/react-icons/) |
| Transitions | [next-transition-router](https://www.npmjs.com/package/next-transition-router) |

---

## Pages & Routes

| Route | Page | Description |
|-------|------|-------------|
| `/` | **Index** | Hero with dot-matrix shader, featured products, marquee, peel-reveal, CTA |
| `/wardrobe` | **Wardrobe** | Full product archive with tag/color filters and animated grid |
| `/genesis` | **Genesis** | Brand origin story with scroll-scrubbed preview gallery |
| `/lookbook` | **Lookbook** | Interactive 3D orb image gallery |
| `/touchpoint` | **Touchpoint** | Contact page with hero and contact form |
| `/unit` | **Shell (A)** | Editorial product/feature page |

---

## Project Structure

```
nrmlss/
├── public/                  # Static assets (images, SVGs)
│   ├── home/                # Hero imagery
│   ├── products/            # Product thumbnails
│   ├── lookbook/            # Orb gallery images
│   ├── genesis/             # Brand story assets
│   └── ...
├── src/
│   ├── app/                 # Next.js App Router pages
│   │   ├── page.js          # Home / Index
│   │   ├── layout.js        # Root layout, fonts, providers
│   │   ├── globals.css      # Global styles & CSS variables
│   │   ├── wardrobe/        # Product archive + products.js data
│   │   ├── genesis/         # Brand story page
│   │   ├── lookbook/        # 3D orb gallery
│   │   ├── touchpoint/      # Contact page
│   │   └── unit/            # Editorial shell page
│   ├── components/
│   │   ├── Menu/            # Full-screen nav overlay
│   │   ├── Footer/          # Site footer
│   │   ├── Product/         # Product card component
│   │   ├── ShoppingCart/    # Slide-out cart panel
│   │   ├── Preloader/       # First-visit intro animation
│   │   ├── DotMatrix/       # WebGL shader background
│   │   ├── Copy/            # Animated text (flicker, scroll reveal)
│   │   ├── MarqueeBanner/   # Infinite scroll banner
│   │   ├── PeelReveal/      # Image peel transition section
│   │   ├── CTA/             # Call-to-action block
│   │   ├── Orb/             # Three.js orb for lookbook
│   │   ├── ContactForm/     # Contact form UI
│   │   └── ...
│   ├── providers/
│   │   └── TransitionProvider.jsx  # Page transition wrapper
│   ├── store/
│   │   └── cartStore.js     # Zustand cart state
│   └── client-layout.js     # Lenis smooth scroll wrapper
├── next.config.mjs
├── jsconfig.json
└── package.json
```

---

## Getting Started

### Prerequisites

- **Node.js** 18.17 or later
- **npm**, **yarn**, **pnpm**, or **bun**

### Installation

```bash
# Clone the repository
git clone https://github.com/ajxdevx/futuristic-techwear-e-commerce-website.git
cd futuristic-techwear-e-commerce-website

# Install dependencies
npm install

# Start the development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Production Build

```bash
npm run build
npm start
```

---

## Available Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server with hot reload |
| `npm run build` | Create optimized production build |
| `npm start` | Serve the production build |

---

## Key Components

### `DotMatrix`
WebGL shader background using Three.js. Renders an animated dot grid with configurable color, dot size, spacing, opacity, and intro delay. Used on the home hero.

### `Preloader`
Branded loading sequence shown on the user's first visit. Coordinates timing with downstream hero animations via the `isInitialLoad` export.

### `Copy`
Reusable animated text wrapper supporting flicker effects and scroll-triggered reveals via GSAP.

### `Product`
Displays a garment unit with image, metadata (tag, color, price), and optional add-to-cart button.

### `ShoppingCart`
Slide-out cart panel showing items, quantities, subtotal, and remove actions. Reads/writes to the Zustand store.

### `Menu`
Full-screen navigation overlay with GSAP SplitText scramble animations, scroll-hide behavior, and route links.

### `Orb`
Three.js sphere with orbiting product images for the Lookbook experience.

---

## State Management

Cart state lives in `src/store/cartStore.js` using Zustand:

```js
import { useCartStore, useCartCount, useCartSubtotal } from "@/store/cartStore";

// Add item
useCartStore.getState().addToCart(product);

// Remove item
useCartStore.getState().removeFromCart(productName);

// Derived selectors
const count = useCartCount();
const subtotal = useCartSubtotal();
```

---

## Animations & Interactions

- **ScrollTrigger** — parallax hero headers, genesis gallery scrub, text reveals
- **SplitText** — menu link character scramble on open/close
- **Page transitions** — `next-transition-router` wraps route changes
- **Lenis** — smooth vertical scroll with separate mobile/desktop easing profiles
- **Product filters** — staggered fade/scale on wardrobe filter changes

---

## Product Catalog

Products are defined in `src/app/wardrobe/products.js`. Each entry follows this shape:

```js
{
  name: "Unit 01",
  price: "180",
  color: "Black",           // Black | White | Grey | Stone | Ice
  tag: "Deform",            // Deform | Sheerform | Functionary
  sizes: ["S", "M", "L", "XL"],
  description: "..."
}
```

Product images are served from `public/products/` and mapped by index in the `Product` component.

---

## Customization

| What to change | Where |
|----------------|-------|
| Site title & meta | `src/app/layout.js` → `metadata` |
| Products | `src/app/wardrobe/products.js` |
| Global colors & fonts | `src/app/globals.css` |
| Menu links | `src/components/Menu/Menu.jsx` |
| Hero copy | `src/app/page.js` |
| Cart behavior | `src/store/cartStore.js` |

---

## Deployment

### Vercel (recommended)

1. Push the repo to GitHub
2. Import the project at [vercel.com/new](https://vercel.com/new)
3. Vercel auto-detects Next.js — no extra config needed

### Other platforms

Run `npm run build` and serve the `.next` output with any Node.js host that supports Next.js 16.

---

## License

This project is provided as-is for portfolio and educational use. All brand imagery and copy are part of the NRMLSS concept storefront.

---

**NRMLSS** — *Silhouettes for the Next Era.*
