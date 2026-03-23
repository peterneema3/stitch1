# Design System Document: The Sun-Drenched Editorial

## 1. Overview & Creative North Star
**Creative North Star: "The Morning Conservatory"**
This design system moves away from the cold, industrial weight of "charcoal and iron" toward an aesthetic that feels organic, light-filled, and intentionally composed. We are designing for the urban professional who seeks warmth without sacrificing precision. 

To break the "template" look, we abandon rigid, boxed-in layouts in favor of **Intentional Asymmetry**. Elements should breathe; headlines may overlap soft image containers, and white space is treated as a premium material rather than empty air. The goal is a digital experience that feels like reading a high-end physical lookbook in a sun-lit café—sophisticated, tactile, and warm.

---

## 2. Colors: Tonal Depth & Warmth
Our palette is anchored in terracotta (`primary: #994127`) and cream (`surface: #fdf8f5`), moving away from harsh blacks to rich, wood-toned neutrals.

### The "No-Line" Rule
**Explicit Instruction:** Sectioning via 1px solid borders is strictly prohibited. Use background color shifts to define boundaries. 
*   **Example:** A hero section using `surface` should transition into a content block using `surface-container-low (#f8f3f0)` to create a natural break without a "line."

### Surface Hierarchy & Nesting
Treat the UI as physical layers of fine paper.
*   **Base:** `surface` (#fdf8f5)
*   **Layer 1 (Subtle Inset):** `surface-container-low` (#f8f3f0)
*   **Layer 2 (Elevated Card):** `surface-container-lowest` (#ffffff)
*   **Layer 3 (Active/Highlight):** `surface-container-high` (#ece7e4)

### Signature Textures & Glassmorphism
*   **The Glass Rule:** For floating navigation or modal overlays, use semi-transparent `surface` colors with a `backdrop-blur` of 12px–20px. This allows the terracotta and wood tones to bleed through, softening the interface.
*   **Gradients:** Use subtle linear gradients for primary CTAs, transitioning from `primary` (#994127) to `primary-container` (#b8583d) at a 135-degree angle. This adds a "soul" to the button that flat color cannot replicate.

---

## 3. Typography: The Editorial Voice
The tension between the serif Newsreader and the geometric Manrope creates an authoritative yet approachable voice.

*   **Display & Headlines (Newsreader):** Use `display-lg` (3.5rem) and `headline-md` (1.75rem) to establish a literary, premium feel. Headlines should use "Optical Sizing" where possible to maintain elegant thins in large formats.
*   **Body & Utility (Manrope):** Use `body-lg` (1rem) for long-form reading. Manrope’s clean structure provides the "professional" counterbalance to the warmth of the Newsreader serifs.
*   **Hierarchy Note:** Always lead with Newsreader for storytelling and Manrope for data or actionable tasks.

---

## 4. Elevation & Depth: Tonal Layering
We do not use shadows to create "pop"; we use them to create "atmosphere."

*   **The Layering Principle:** Depth is achieved by stacking. Place a `surface-container-lowest` (#ffffff) card on a `surface-container-low` (#f8f3f0) background. The slight shift in brightness creates a sophisticated "lift."
*   **Ambient Shadows:** If a floating element is required, use a shadow with a 32px blur, 0px spread, and 6% opacity. Use a tinted shadow color derived from `on-surface` (#1c1b1a) to avoid a "dirty" grey look.
*   **The Ghost Border:** If a boundary is required for accessibility, use `outline-variant` (#dcc1ba) at **20% opacity**. It should be felt, not seen.

---

## 5. Components

### Buttons
*   **Primary:** A gradient of `primary` to `primary-container`. Corner radius: `md` (0.375rem). Type: `title-sm` (Manrope).
*   **Secondary:** Ghost style. No background. `outline` (#89726c) at 20% opacity for the border.
*   **Tertiary:** Text-only using `primary` color. High-emphasis hover state using a subtle `surface-container-highest` background.

### Cards & Lists
*   **The No-Divider Rule:** Forbid 1px dividers between list items. Use `spacing-5` (1.7rem) of vertical space or alternating subtle background tints (`surface` vs `surface-container-low`).
*   **Cards:** Use `surface-container-lowest` (#ffffff) with a `lg` (0.5rem) corner radius. No border.

### Input Fields
*   **Style:** Minimalist. Use `surface-container-highest` (#e6e2df) as a subtle background fill rather than a high-contrast outline. 
*   **Focus State:** Transition the background to `surface` and add a 1px `primary` (#994127) "Ghost Border" at 40% opacity.

### Signature Component: The "Conservation Gallery"
A layout pattern for featured content: An asymmetrical grid where images use `rounded-xl` (0.75rem) corners, and `Newsreader` headlines overlap the image container by `spacing-4` (1.4rem) to create a layered, editorial look.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use `Newsreader` in italics for secondary headlines to add a "designer's touch."
*   **Do** allow for generous white space. If in doubt, increase the margin to the next increment on the Spacing Scale (e.g., move from `8` to `10`).
*   **Do** use `tertiary` (#7b542b) for accent elements like icons or small labels to ground the terracotta in wood tones.

### Don’t
*   **Don’t** use pure black (#000000) for anything. Always use `on-surface` (#1c1b1a).
*   **Don’t** use "Drop Shadows" on buttons. Use tonal shifts on hover instead.
*   **Don’t** use the `full` (9999px) roundedness for anything other than small tags or chips; it feels too "tech-startup" for this sophisticated editorial system. Use `md` or `lg` for a more architectural feel.