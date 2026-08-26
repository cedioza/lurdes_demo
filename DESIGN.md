# Lurdes Marques Cabeleireiros — Design System

## Direction

**Pink-and-ink salon lookbook.** The landing uses the reference site's recognizable pink, white, and black family with an editorial rhythm: real work leads, thin rules organize, and the consultation menu creates a considered pause before contact.

## Palette

- `--pink` / `#de5d83`: reference accent, hero image field, contact field, service rail, and primary actions.
- `--pink-deep` / `#a9365b`: contrast-safe pink for labels, links, indicators, and small text on light surfaces.
- `--ink` / `#1b1b1b`: primary dark surface and text.
- `--ink-soft` / `#3a3a3a`: secondary dark text.
- `--paper` / `#fafafa` and `--paper-soft` / `#f5f5f5`: quiet page surfaces.
- `--white` / `#ffffff`: elevated service panel, inverse type, and active controls.
- `--muted` / `#666666` and `--line-light` / `#eeeeee`: readable secondary copy and separators.

Semantic aliases in `global.css` preserve the existing component grammar while resolving to this reference palette; no cobalt, lime, or coral values remain.

## Typography

- Display: Barlow Condensed, used for the oversized editorial voice, category tabs, and service headings.
- Body: DM Sans, used for navigation, descriptions, lists, and controls.
- Display copy stays short and high-contrast; body copy is constrained to readable measures.

## Composition

- The hero is an asymmetric ink/pink split with a large real portfolio image, offset thumbnail, vertical location note, and immediate WhatsApp action.
- Thin rules, grid traces, section markers, and masonry image spans keep the lookbook structure without competing with the hair work.
- Services are an interactive consultation explorer: a visible tab rail for Cabello, Tratamientos, and Manos & pies controls one white detail panel at a time. Native buttons expose `role="tab"`, `aria-selected`, `aria-controls`, and keyboard arrow/Home/End navigation. CSS keeps the first panel visible when JavaScript is unavailable.
- The brands row remains attached to the service menu as its professional finish.
- The portfolio is the proof surface: real local images, category filters, restrained crop/focus on hover, and a native dialog lightbox.
- Mobile collapses into a single-column story and service explorer with a persistent bottom WhatsApp action.

## Motion thesis

The page behaves like a lookbook being opened. The hero image reveals through a bounded clip-path and scale shift. Changing a service category crossfades/slides the consultation panel and staggers its real item list, so the interface explains what changed instead of merely decorating the page. Portfolio images use a restrained crop/focus adjustment. Section reveals are progressive enhancement: content is visible without JavaScript and only receives bounded opacity, blur, clip-path, and transform motion when the observer is available. Reduced motion removes spatial travel and keeps content and state legible.

Motion uses CSS transforms, opacity, clip-path, and short delays only; the list stagger is capped at ten items and the expensive effects stay limited to isolated image/panel regions.

## Components and states

- Pink primary actions, dark ink navigation, and text links provide clear conversion hierarchy.
- Mobile navigation is `aria-hidden` + `inert` when closed, supports Escape, and restores focus to the menu trigger.
- Service tabs use native buttons, visible active indicator, focus-visible styling, and a single active `tabpanel`.
- Portfolio filters expose `aria-pressed` and hide non-matching items.
- Reveal motion is progressive enhancement; content remains visible if JavaScript or IntersectionObserver is unavailable.
- Reduced-motion users receive no entrance, spatial, or crop animation.

## Content and assets

Portfolio assets were sourced from the official reference site and converted to local WebP files under `public/images`. Every shipping raster carries an `impeccable:prompt` provenance sidecar. Licensing/brand permission must be confirmed with the salon before production launch.

## Accessibility

Semantic landmarks, skip link, visible focus rings, descriptive Spanish alt text, keyboard-operable service tabs, minimum 44px control targets, readable contrast on the main actions, and mobile-first contact affordances are part of the system.
