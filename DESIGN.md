# KabirBrewCafe — Design System

## Theme

Dark mode. Scene: "A warm, dim-lit brew-house in Jin Bazar where wood-fire oven glow and coffee steam meet the evening street bustle — the amber pendant light over the table IS the atmosphere."

## Color Strategy

Committed — one saturated amber-gold carries 30-60% of the visual weight.

## Palette (OKLCH)

```css
--bg:         oklch(0.10 0.005 60);    /* deep warm near-black */
--surface:    oklch(0.14 0.008 55);    /* card/section bg */
--primary:    oklch(0.68 0.17 78);     /* amber-gold — brand anchor, glows on dark */
--ink:        oklch(0.88 0.01 80);     /* warm off-white body text */
--accent:     oklch(0.50 0.19 35);     /* deep tomato- rust for CTAs, badges */
--muted:      oklch(0.60 0.012 70);    /* secondary helper text */
```

Contrast:
- ink vs bg: 13.2:1 (AAA)
- muted vs bg: 6.0:1 (AA)
- accent on primary: distinct hues and L steps (L diff > 0.15)
- CTA white text on accent (L=0.50): 4.8:1 (AA)

## Typography

| Role | Family | Weight | Size (clamp) | Line Height | Letter Spacing |
|---|---|---|---|---|---|
| H1 | Playfair Display | 700 | clamp(2.5rem,5vw,4rem) | 1.05 | -0.02em |
| H2 | Playfair Display | 700 | clamp(1.8rem,3.5vw,2.75rem) | 1.1 | -0.01em |
| H3 | Playfair Display | 400 | clamp(1.25rem,2vw,1.6rem) | 1.15 | 0 |
| Body | DM Sans | 400 | 1rem / 1.125rem | 1.65 | 0 |
| Body Large | DM Sans | 400 | clamp(1.05rem,1.3vw,1.125rem) | 1.7 | 0 |
| Caption | DM Sans | 500 | 0.75rem | 1.4 | 0.15em uppercase |
| Small | DM Sans | 400 | 0.8125rem | 1.5 | 0 |

Display heading max: 4rem (64px). H1 letter-spacing floor: -0.02em.

## Spacing & Grid

- Base unit: 8px
- Section padding: 96px (desktop), 64px (tablet), 48px (mobile)
- Content max-width: 1200px
- Container padding: 24px (desktop), 20px (tablet), 16px (mobile)
- Grid gaps: 24px (cards), 48px (sections), 64px (major breaks)

## Signature Motif

Steam curl — an SVG organic curve resembling rising coffee/pizza steam. Used:
1. Animated in hero as ambient motion
2. Brass-colored section divider between all content sections
3. Subtle background watermark on testimonial cards
4. Always same SVG path, scaled per context — never varied shape

## Component Tokens

### Buttons
- Primary: bg=accent, text=white, border-radius=100px, px-7 py-3.5, hover scale(1.02)
- Secondary: bg=transparent, text=ink, border=1px primary/30, border-radius=100px
- Pill shape consistent across all interactive elements

### Cards
- border-radius: 0px (all sharp corners — intentional non-rounded)
- bg=surface, border=1px primary/10
- hover: border primary/30, translateY(-2px)

### Dividers
- Brass divider bar: 48px wide, 2px tall, bg=primary
- Steam SVG divider: centered, 80×32px, opacity 0.3

### Navigation
- Floating centered pill, max 800px wide
- bg=bg/85, backdrop-blur(16px), border=1px primary/20
- border-radius=100px
- Mobile: full-screen overlay drawer with blurred bg

## Motion

- Easing: cubic-bezier(0.16, 1, 0.3, 1) — exponential ease-out
- Scroll reveal: translateY(32px) + opacity 0→1, 800ms
- Nav link hover: underline slide-in from left, 300ms
- CTA hover: background darken + scale(1.02), 200ms
- Hover on cards: translateY(-2px) + border lighten, 300ms
- prefers-reduced-motion: collapse all to instant
