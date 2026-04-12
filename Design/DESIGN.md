# Design System Strategy: Architectural Silence

## 1. Overview & Creative North Star
**Creative North Star: The Shadow Gallery**
Prezence Studio is not a template; it is a digital physical space. To achieve a premium "High-End Editorial" feel, we move away from standard grid layouts and embrace **Architectural Silence**. This means using negative space as a functional element, not just a gap between content. By utilizing intentional asymmetry and high-contrast typographic scales, we create an experience that feels curated, like a high-fashion lookbook or a contemporary art gallery.

The system breaks the "web-standard" mold by focusing on **Tonal Depth**. Instead of using lines to separate ideas, we use light and shadow—specifically through the manipulation of dark-on-dark layering—to guide the eye.

---

## 2. Colors & Surface Logic
The palette is a sophisticated study in near-blacks and metallic warmth. We use the Material Design naming convention to ensure technical clarity while maintaining editorial soul.

### The Foundation
*   **Surface (`#0A0A0A`):** The primary void. All layouts begin here.
*   **Primary (`#C9A84C`):** Muted gold. This is our "surgical strike" color—used only for critical calls to action and brand-defining moments.
*   **Surface Container (`#1C1C1C`):** The secondary depth layer. Use this for cards and elevated sections.

### The Rules of Engagement
*   **The "No-Line" Rule:** Prohibit the use of 1px solid borders for sectioning. Structural boundaries must be defined solely through background color shifts. A section should transition from `surface` to `surface_container_low` to define a break, never a stroke.
*   **Surface Hierarchy & Nesting:** Treat the UI as physical layers. An element of higher importance should "float" or "sink" relative to its environment. Use `surface_container_lowest` for background-level utility and `surface_container_highest` for interactive card elements.
*   **Signature Textures:** While the palette is minimal, use a subtle `primary` to `primary_container` gradient transition *only* on high-level CTAs to provide a "metallic sheen" that mimics gold leaf rather than a digital gradient.

---

## 3. Typography
Our typography scale is designed to feel authoritative yet breathable.

*   **Display & Headlines (Space Grotesk):** This is our "Voice." Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for hero statements. The technical, geometric nature of Space Grotesk provides the "Studio" feel.
*   **Body & UI (Inter):** This is our "Intelligence." Inter provides high legibility at `body-md` (0.875rem). Use a generous line-height (1.6) to maintain the editorial "airy" feel.
*   **The Contrast Rule:** Pair a `display-lg` headline with a `label-sm` secondary text. The extreme difference in scale creates a custom, high-end hierarchy that standard templates avoid.

---

## 4. Elevation & Depth
In a dark mode system, traditional shadows are often invisible. We achieve depth through **Tonal Layering**.

*   **The Layering Principle:** Place a `surface_container_low` card on top of a `surface` background to create a "soft lift." The hierarchy is felt through the subtle shift in grey, not a harsh shadow.
*   **Ambient Shadows:** For floating modals, use an extra-diffused shadow: `box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5)`. The shadow should feel like ambient occlusion in a room, not a drop shadow on a page.
*   **The "Ghost Border" Fallback:** If accessibility requires a container edge, use the `outline_variant` (`#2A2A2A`) at **20% opacity**. It should be felt more than seen.
*   **Glassmorphism:** For navigation bars or floating action menus, use `surface` at 70% opacity with a `blur(12px)` effect. This "frosted glass" look allows the gold accents of the page to bleed through as the user scrolls, maintaining a sense of place.

---

## 5. Components

### Buttons
*   **Primary:** Solid `primary` (`#C9A84C`) background with `on_primary` (`#3D2E00`) text. Corner radius: `md` (6px). No borders.
*   **Secondary:** Ghost style. `outline` (`#99907E`) 1px border with `on_surface` text.
*   **Interaction:** On hover, the Primary button should scale slightly (1.02) and increase its inner glow; avoid color changes that "break" the gold brand identity.

### Cards & Lists
*   **The "No-Divider" Rule:** Never use horizontal lines to separate list items. Use vertical white space from the spacing scale or a hover-state background shift (`surface_container_high`).
*   **Visual Continuity:** Cards should use `surface_container` (`#1C1C1C`) with a `sm` (0.125rem) ghost border of `outline_variant`.

### Input Fields
*   **State:** Default state is a bottom-border only (the "Editorial Input"). Focus state evolves into a full container using `surface_container_high` with a 1px `primary` accent on the left-most edge only.

---

## 6. Do’s and Don’ts

### Do:
*   **Embrace Asymmetry:** Offset your text columns. Let a headline hang 20% into the left margin.
*   **Use Mono-spaced Accents:** Use `label-sm` in a mono-spaced font for technical data or dates to reinforce the "Development Studio" aspect.
*   **Maximize Whitespace:** If you think there is enough space, add 24px more. Space is the luxury.

### Don’t:
*   **Don’t use 100% White for Body Text:** Use `on_surface_variant` (`#D0C5B2`) or `secondary` (`#C7C6C6`) for long-form reading to prevent eye strain. Save Pure White for headlines.
*   **Don’t Round Everything:** Keep corners at `md` (6px) or `lg` (8px). Avoid "pill" shapes for buttons (except for small chips) to maintain the architectural, sharp-edged aesthetic.
*   **Don’t over-use Gold:** If more than 5% of the screen is gold, the "premium" effect is lost. Gold is the jewelry, not the outfit.