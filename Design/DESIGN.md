# Design System Strategy: Prezence Studio

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Monolith Editorial."** 

This system rejects the "web-standard" clutter of soft rounded corners and busy grids. Instead, it draws inspiration from high-end architectural journals and avant-garde street fashion. For **Prezence Studio**, the identity is defined by a "Razor Sharp" precision—using absolute zero-radius edges (`0px`) and a high-contrast, monochromatic palette. We break the template look by using aggressive typographic scales and intentional asymmetry, where large display text often bleeds or anchors to the extreme edges of the container, creating a sense of "loud" minimalism.

## 2. Colors: The Matte Obsidian Palette
The palette is rooted in deep obsidian tones, emphasizing texture and tonal depth over flat color.

*   **Core Tones:**
    *   `background`: #131313 (The anchor; a deep, matte obsidian).
    *   `primary`: #ffffff (The "Razor" light; used for high-impact typography and primary CTAs).
    *   `tertiary`: #ffdea7 (The "Signature Ochre"; used sparingly for accent labels or high-level branding elements).
*   **The "No-Line" Rule:** Sectioning must never be achieved with 1px borders. Use `surface-container-low` (#1b1b1b) or `surface-container-high` (#2a2a2a) to create distinct blocks of content. Boundaries are felt through tonal shifts, not drawn lines.
*   **Surface Hierarchy:** Layering should follow a physical logic. Place `surface-container-lowest` (#0e0e0e) elements inside `surface` (#131313) areas to create a "recessed" look, or `surface-container-highest` (#353535) to suggest a raised "matte slab."
*   **Signature Textures:** Utilize a subtle gradient transition from `surface-container-high` (#2a2a2a) to `surface-container-lowest` (#0e0e0e) across large sections to provide a sense of atmospheric depth.

## 3. Typography: Loud & Neutral
The typographic pairing is a study in contrast: the aggressive, condensed energy of **Bebas Neue** against the invisible, clinical precision of **Inter**.

*   **Display & Headlines (Bebas Neue):** Used exclusively in **ALL CAPS**. These should be sized aggressively (`display-lg`: 3.5rem) with tight letter spacing. This is the "Loud" part of the personality—it should feel like a headline in a luxury magazine.
*   **Body & Labels (Inter):** The "Modern Minimal" counter-weight. Used for all functional text, descriptions, and UI labels. Inter provides the necessary legibility to balance the intensity of Bebas Neue.
*   **Hierarchy Note:** Use `tertiary` (#ffdea7) for small metadata or "label-sm" categories to create a sophisticated focal point amidst the monochrome.

## 4. Elevation & Depth
In a system with zero border-radii, depth must be sophisticated to avoid looking "flat" or "dated."

*   **The Layering Principle:** Stacking tiers is mandatory. A `surface-container-low` card sitting on a `surface` background creates a natural, sharp-edged lift.
*   **Ambient Shadows:** If an element must float, use a "Dark Glow" rather than a drop shadow. Use a 24px-48px blur with 5% opacity, using a color derived from `on-surface` (#e2e2e2) to simulate light catching the edge of a matte surface.
*   **The "Ghost Border" Fallback:** For high-density UI where separation is critical, use the `outline-variant` (#474747) at 15% opacity. It should be barely perceptible—a "whisper" of an edge.
*   **Glassmorphism:** For floating navigation or overlays, use `surface-container-high` at 70% opacity with a `20px` backdrop blur. This keeps the "monolith" feeling while allowing the background content to bleed through.

## 5. Components

*   **Buttons (The Razor Edge):**
    *   **Primary:** `primary` (#ffffff) background with `on-primary` (#1a1c1c) text in Bebas Neue (All Caps). 0px border-radius.
    *   **Secondary:** `outline` (#919191) 1px Ghost Border with `primary` text.
*   **Cards:** No borders. No shadows. Use background color shifts (e.g., `surface-container-lowest`) and generous internal padding (32px+).
*   **Input Fields:** Bottom-border only using `outline-variant`. Labels in `label-md` (Inter, All Caps, 0.05em letter spacing).
*   **Chips:** Rectangular, `surface-container-highest` background, Inter `label-sm` text. These should look like precision-cut labels.
*   **Lists:** Forbid divider lines. Use `16px` or `24px` of vertical white space to separate items. Hover states should trigger a subtle shift to `surface-bright` (#393939).
*   **Editorial Badge:** A custom component using `tertiary` (#ffdea7) text in Bebas Neue for category tags, as seen in the "DISPLAY" badge.

## 6. Do’s and Don’ts

### Do:
*   **DO** use extreme typographic scale. If a headline is big, make it *huge*.
*   **DO** embrace the "Starkness." Large areas of `background` (#131313) are a feature, not a bug.
*   **DO** align everything to a strict, sharp grid. With 0px corners, misalignment is immediately obvious.
*   **DO** use the "Signature Ochre" (`tertiary`) as a surgical strike—use it for one tiny element to draw the eye.

### Don't:
*   **DON’T** use border-radius. Ever. Even 2px breaks the "Razor Sharp" mandate.
*   **DON’T** use standard grey shadows. They look "muddy" on matte obsidian surfaces.
*   **DON’T** use icons unless absolutely necessary. Rely on strong typography first.
*   **DON’T** use 100% white for body text. Use `on-surface-variant` (#c6c6c6) to reduce eye strain against the black background, reserving pure `primary` (#ffffff) for headlines.