# AGENTS.md — WinWin Fan Hub

## Project Overview
A Celebrity Fan Hub SPA for 董思成 (WinWin / Dong Sicheng), with hover-dropdown navigation, hash-based routing, bento grid for works, infinite scroll gallery, and full-screen gallery viewer. Built as a static HTML/CSS site with vanilla JavaScript, following "Sky Blue Luxury Editorial" design with visible photo hero background.

## Tech Stack
- **Template**: native-static (coze init)
- **Languages**: HTML5, CSS3, Vanilla JavaScript (ES6+)
- **Fonts**: Playfair Display + Inter + Noto Serif SC (via Google Fonts .cn domain)
- **Routing**: Hash-based SPA (#/category/tv-series, #/gallery/guzhuang, #/about/profile, #/about/guestbook, #/categories, #/gallery)
- **Server**: Python `http.server` on port from ${DEPLOY_RUN_PORT}

## Project Structure
```
/workspace/projects/
├── index.html          # Main SPA — all pages rendered via JS
├── data.js             # All content data (CONTENT, ABOUT_DATA, CATEGORY_CARDS, GALLERY_CARDS, AIRED_WORKS, UPCOMING_WORKS, ALL_GALLERY_IMAGES, SOCIAL_LINKS)
├── styles/
│   └── main.css        # All styles (CSS custom properties, responsive, animations)
├── images/
│   ├── 豆包.mp4        # Hero greeting video (max-width 320px, pop-in animation)
│   └── hero-bg.jpg     # Hero background photo (visible with gradient overlay)
├── DESIGN.md           # Design specifications
├── AGENTS.md           # This file
└── .coze               # Build/run configuration
```

## Build & Run
- **Dev**: `python -m http.server ${DEPLOY_RUN_PORT} --bind 0.0.0.0`
- **No build step required** — pure static files

## SPA Architecture
- **Router**: `window.location.hash` based routing with `hashchange` event listener
- **Render functions**: `renderHome()`, `renderCategoriesPage()`, `renderCategoryPage(key)`, `renderGallerySummary()`, `renderGalleryPage(key)`, `renderAboutPage()`, `renderGuestbookPage()`
- **Data**: Separated into `data.js` — `CONTENT` object, `ABOUT_DATA`, `CATEGORY_CARDS`, `GALLERY_CARDS`, `AIRED_WORKS`, `UPCOMING_WORKS`, `ALL_GALLERY_IMAGES`, `SOCIAL_LINKS`
- **Navigation**: `navigateTo(type, key)` function sets hash; hover-based dropdown menus

## Navigation Structure
- **HOME** — direct link, hash = `''`
- **CATEGORIES** (hover dropdown → #/categories summary page):
  - TV Series (`#/category/tv-series`) — 5-col grid
  - Variety Shows (`#/category/variety-shows`)
  - Stage Focus (`#/category/stage-focus`)
  - Interview (`#/category/interview`)
  - Fan-made (`#/category/fan-made`)
- **GALLERY** (hover dropdown → #/gallery summary page):
  - Period Costume 古装 (`#/gallery/guzhuang`)
  - Casual Wear 私服 (`#/gallery/sifu`)
  - Red Carpet 活动红毯 (`#/gallery/hongtan`)
  - HD Wallpapers 高清壁纸 (`#/gallery/bizhi`)
- **ABOUT** (hover dropdown → Profile by default):
  - Profile (`#/about/profile`) — photo, info, career timeline, filmography
  - Guestbook (`#/about/guestbook`) — client-side message board

## Key Design Tokens (from DESIGN.md)
- Background: `#9CE5F4` (sky blue)
- Hero: Real background photo (visible) + light gradient overlay
- Cards: `#FFFFFF` (white)
- Dark sections: `#061124` (deep navy for gallery viewer/footer)
- Brand accent: `#3A8BCC` (蔚蓝色)
- Heading font: Playfair Display + Noto Serif SC
- Body font: Inter + Noto Serif SC
- Content grid: 5-column layout for ALL categories
- Gallery grid: 4-column layout with full-screen viewer

## Core Features
1. **Visible Photo Hero**: Background photo visible with gradient overlay, desktop text-left/video-right layout
2. **Video Pop-in Animation**: Video character pops in on page load with cubic-bezier animation
3. **Video White Background Removal**: `mix-blend-mode: multiply` to make white bg transparent
4. **Video Play Once & Disappear**: Video fades out after playing, class `video-ended`
5. **Mouse-follow Character**: Hero video follows mouse movement with translate + 3D rotate
6. **Flower Cursor**: Custom small flower cursor on desktop (SVG-based, smooth follow)
7. **Bento Grid**: Aired works (3-col with large card) + Upcoming works (3-col), click navigates to category
8. **Gallery Infinite Scroll**: Horizontal auto-scrolling carousel, pause on hover, bilingual labels
9. **Full-screen Gallery Viewer**: Left/right arrows, keyboard nav, touch swipe, thumbnail bar, side category nav, download button, bilingual captions
10. **Hover Dropdowns**: Desktop hover-based, bilingual items (English title + Chinese subtitle)
11. **Fuzzy Search**: Global search overlay, fuzzy-matches across all data
12. **Guestbook**: Client-side message board on About/Guestbook page
13. **Unified Footer**: Social icons, bilingual disclaimer, copyright, guestbook link

## Common Modifications
- **Add a new category item**: Add entry to `CONTENT['category-key'].items` array in data.js; update AIRED_WORKS/UPCOMING_WORKS if applicable
- **Add a new gallery image**: Add entry to `CONTENT['gallery-key'].images` array in data.js; ALL_GALLERY_IMAGES auto-generates
- **Add a new category/gallery**: Create entry in `CONTENT` object + add card in `CATEGORY_CARDS` or `GALLERY_CARDS` in data.js
- **Change accent color**: Update `--accent` in `:root` of main.css
- **Update About page info**: Edit `ABOUT_DATA` object in data.js
- **Change hero video**: Replace `images/豆包.mp4` file
- **Change hero background**: Replace `images/hero-bg.jpg` file
- **New images**: Place in `images/` folder, reference with `./images/filename.jpg`

## Footer Disclaimer
The footer contains a bilingual (Chinese + English) disclaimer stating this is a non-profit fan-made website, not affiliated with SM Entertainment.
