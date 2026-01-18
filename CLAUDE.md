# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Vamos Paisa is a static single-page website for a local tour guide service in Medellín, Colombia. No build system—just open `index.html` in a browser.

## Architecture

**Bilingual Support (ENG/ESP)**
- All translatable text uses `data-en` and `data-es` attributes
- JavaScript in `script.js` swaps `innerHTML` based on selected language
- Language preference persists via localStorage (`vamos-paisa-lang`)
- Toggle buttons in navbar switch between languages

Example pattern:
```html
<p data-en="English text" data-es="Spanish text">English text</p>
```

**File Structure**
- `index.html` - Single page with all sections (hero, about, tours, experience, testimonial, contact, footer)
- `css/styles.css` - All styles including responsive breakpoints (1024px tablet, 768px mobile, 480px small mobile)
- `js/script.js` - Language toggle, navbar scroll effect, intersection observer animations
- `pics/` - Tour images (PNG format)
- `mde.md` - Reference content about Medellín (not rendered on site)

**CSS Variables** (defined in `:root`)
- `--terracotta`, `--golden`, `--coffee`, `--cream` - Brand colors
- Responsive sizing uses `clamp()` throughout

**Key UI Components**
- `.lang-toggle` - Language switcher in navbar
- `.tour-card` - Tour listing cards with hover overlays
- `.gallery-item` - Experience section image grid
- Scroll animations triggered by Intersection Observer (`.visible` class)
