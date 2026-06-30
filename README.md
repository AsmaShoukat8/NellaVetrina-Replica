# Nella Vetrina — Homepage Clone

A pixel-focused front-end recreation of the [Nella Vetrina](https://nellavetrina.com) homepage, built with HTML5, Bootstrap 5, custom CSS, and vanilla JavaScript. Built as a front-end practice project to sharpen layout, animation, and interaction skills — not affiliated with the original brand.


📸 **Screenshot / GIF:** 

---

## Page Sections

- **Navbar** — sticky top nav with contact info, logo, search/account icons, and the mega-dropdown category menu
- **Hero Section** — full-screen auto-playing image slider with overlay title, tagline, and "Ask an Expert" CTA
- **Category Grid** — 2x2 showcase grid linking into Furniture, Kitchen, Bathroom, and Lighting
- **Video Section** — full-width autoplay background video (Vimeo embed)
- **Explore All Products Gallery** — asymmetric image grid (Bootstrap column spans) covering Lighting, Furniture, Seating, Office, Wall Units, Wardrobe, Bathroom, Kitchen, and Turnkey categories, each with a hover zoom effect
- **Our Story Section** — full-bleed background image with centered text overlay and an animated accent line
- **Press Section** — logo strip on desktop, swipeable Bootstrap carousel on mobile
- **Instagram Feed** — 3-column responsive grid with hover overlays (likes, comments, caption) and a custom lightbox/modal for image + video posts
- **Footer** — About, Contact, Privacy, and Newsletter columns, plus social icons and copyright

## Features

- **Mega-dropdown navigation** — desktop hover-reveal panels for Furniture, Bathroom, Lighting, and Outdoor categories, each with its own multi-column layout and a "show more" collapse toggle
- **Separate mobile navigation pattern** — rather than just squashing the desktop menu, mobile gets dedicated slide-in side panels (`translateX` transitions) with back-navigation, driven by a small reusable `clickme()` / `clickmetoo()` JS pair
- **Auto-playing hero image carousel** — built from scratch with CSS `@keyframes`, no carousel library
- **Instagram-style feed + custom lightbox** — image and video posts, keyboard navigation (←/→/Esc), dynamic content rendered from a JS data array instead of hardcoded markup
- **Fully responsive layout** — Bootstrap 5 grid combined with custom breakpoints for navbar, hero text sizing (`clamp()`), video section height, and the Instagram grid
- **Custom typography** — self-hosted `@font-face` (NeutraTextAlt, regular + bold) applied globally
- **Hover micro-interactions** — image zoom-on-hover, dropdown link color transitions, footer heading scale effect

## Tech Stack

`HTML5` · `CSS3` · `Bootstrap 5` · `Vanilla JavaScript` · `Font Awesome 6`

## Challenges & What I Learned

- **Desktop vs. mobile nav as genuinely different UX, not just a resized version** — desktop uses CSS `:hover` reveal on mega-dropdowns; mobile swaps to JS-driven slide-in panels via `transform: translateX()`. Keeping both in sync (same content, two different interaction models) was the main structural challenge.
- **Debugging a silent `<a href="">` bug** — two of the four nav triggers used an empty `href=""` instead of `href="#"`. Clicking the chevron inside them fired the JS correctly, but the click event then bubbled up to the parent `<a>`, which triggered a full page reload before the transform change was visible — making it look like the JS "did nothing." Fixed by correcting the `href` and reinforced the lesson to guard against event bubbling with `preventDefault()`.
- **Reusable JS over copy-pasted handlers** — instead of writing a separate function per dropdown, `clickme(boxnum)` / `clickmetoo(boxnum)` take an ID suffix and target `nb${boxnum}` dynamically, so adding a new mobile panel only needs one new `<div id="nbX">` and a CSS rule, not new JS.

## Setup

No build step required — it's a static site.



## Notes

This is a learning/portfolio project replicating the visual design and interaction patterns of nellavetrina.com for educational purposes. All trademarks and brand assets belong to their respective owners.
