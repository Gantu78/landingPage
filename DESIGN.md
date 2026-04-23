# Design System Strategy: The Architectural Precision

## 1. Overview & Creative North Star: "The Urban Concierge"

This design system moves away from the cluttered, utility-first aesthetics of traditional transit apps, moving instead toward **The Urban Concierge**. Our North Star is a fusion of high-end editorial layouts and architectural precision. We treat the city's negative space (parking) as a premium asset. 

To break the "template" look, we utilize **Intentional Asymmetry**. Instead of a centered, rigid grid, we use wide-set margins and overlapping "floating" containers that break the container bounds. This creates a sense of movement and professional fluidity. The contrast between the heavy `display-lg` Manrope headings and the airy `body-md` Inter creates an authoritative yet approachable hierarchy.

---

## 2. Colors: Tonal Depth & The "No-Line" Rule

The palette is anchored in **Royal Blue (`primary`)**, balanced by a sophisticated range of greyscale surfaces.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. Boundaries must be established through background color shifts. 
*   *Example:* A `surface-container-low` (#f3f4f5) content block should sit directly on a `surface` (#f8f9fa) background. The shift in tone is the boundary.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of stacked material.
*   **Base:** `surface` (#f8f9fa)
*   **Nesting Level 1:** Use `surface-container-low` for large content areas.
*   **Nesting Level 2 (The Interactive Layer):** Use `surface-container-lowest` (#ffffff) for cards or interactive elements to make them "pop" against the lower-tier backgrounds.

### The "Glass & Gradient" Rule
To avoid a flat, "SaaS-lite" appearance, floating elements (like navigation bars or hovering price markers) must utilize **Glassmorphism**:
*   **Fill:** `surface` at 70% opacity.
*   **Effect:** Backdrop blur (20px–40px).
*   **Signature Texture:** Main CTAs should not be flat. Apply a subtle linear gradient from `primary` (#003ec7) to `primary-container` (#0052ff) at a 135° angle to give buttons a "lit from within" professional polish.

---

## 3. Typography: Editorial Authority

We use a dual-typeface system to balance character with readability.

*   **Display & Headlines (Manrope):** This is our "Architectural" voice. Use `display-lg` for hero statements with tight letter-spacing (-0.02em). It should feel heavy, stable, and premium.
*   **Body & Labels (Inter):** Our "Functional" voice. Inter provides high legibility for data-dense parking information.
*   **Hierarchy Note:** Always pair a `headline-sm` in Manrope with a `label-md` in Inter (all-caps, 0.05em tracking) for metadata to create a sophisticated, "Swiss-style" information density.

---

## 4. Elevation & Depth: Tonal Layering

Traditional shadows are often "muddy." We achieve depth through light and tone.

*   **The Layering Principle:** Instead of a shadow, place a `surface-container-highest` card on a `surface` background. The delta in luminance creates a natural edge.
*   **Ambient Shadows:** For high-priority floating elements (e.g., a "Book Now" floating bar), use a multi-layered shadow:
    *   *Shadow 1:* `offset-y: 4px, blur: 20px, color: on-surface @ 4%`
    *   *Shadow 2:* `offset-y: 12px, blur: 40px, color: on-surface @ 8%`
*   **The "Ghost Border" Fallback:** If a border is required for accessibility (e.g., input fields), use `outline-variant` (#c3c5d9) at **20% opacity**. Never use 100% opaque lines.

---

## 5. Components: Precision Primitives

### Buttons
*   **Primary:** Gradient (`primary` to `primary-container`), `xl` (0.75rem) roundedness. No border. Text: `title-sm` (white).
*   **Secondary:** `surface-container-highest` background with `primary` text. This creates a "soft" interactive state.
*   **Tertiary:** No background. `primary` text with a 2px underline that only appears on hover.

### Cards & Lists
*   **Rule:** Forbid divider lines. Use 24px or 32px of vertical white space (from the Spacing Scale) to separate list items.
*   **The "Parking Asset" Card:** Use `surface-container-lowest` with a `lg` (0.5rem) corner radius. The image should have a slight `surface-dim` inner glow to feel embedded.

### Input Fields
*   **Style:** `surface-container-low` background, no border. On focus, transition the background to `surface-container-lowest` and add a 2px `primary` bottom-only stroke. This mimics high-end luxury automotive interfaces.

### Signature Component: The "Availability Heatmap"
For a parking marketplace, we need a custom chip variant.
*   **Status Chips:** Use `secondary_fixed` (#e2e2e2) for "Available" and `tertiary` (#952200) for "Limited." Use a small 4px dot next to the text rather than a full background fill to maintain a minimalist aesthetic.

---

## 6. Do’s and Don’ts

### Do
*   **DO** use whitespace as a structural element. If a design feels crowded, increase padding rather than adding a line.
*   **DO** use `display-lg` typography for numbers (prices, distances) to emphasize the marketplace's transparency.
*   **DO** use "Full" roundedness (pill shape) only for small tags and labels; use `xl` (0.75rem) for main containers to maintain a "sleek" architectural feel.

### Don’t
*   **DON’T** use pure Black (#000000) for text. Use `on-surface` (#191c1d) to ensure the high contrast doesn't cause eye strain.
*   **DON’T** use standard Material Design drop shadows. If it looks like a "default" shadow, it’s too heavy.
*   **DON’T** use icons with varying stroke weights. All icons must be 1.5px or 2px to match the "Sleek" brand pillar.