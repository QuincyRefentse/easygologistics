# Design System Document

## 1. Overview & Creative North Star: "The Kinetic Architect"

In the logistics sector, "trust" is often misinterpreted as "static." This design system rejects that notion. Our Creative North Star, **The Kinetic Architect**, balances the heavy-duty reliability of freight with the fluid precision of modern technology. 

Moving beyond standard enterprise templates, this system utilizes **intentional asymmetry** and **tonal layering** to create a sense of forward motion. We replace rigid, boxed-in layouts with an editorial approach: generous white space, overlapping elements that mimic the stacking of cargo, and a high-contrast typographic scale that speaks with authority. This is a digital experience that feels as meticulously engineered as a global supply chain.

---

## 2. Colors: Depth over Definition

The palette is anchored by the deep navy and forest green of the brand, but its sophistication lies in how these tones are layered.

### The "No-Line" Rule
To maintain a premium, modern feel, **1px solid borders are prohibited for sectioning.** Structural boundaries must be defined solely through:
*   **Background Shifts:** Transitioning from `surface` (#fbf8fe) to `surface-container-low` (#f6f2f8).
*   **Tonal Transitions:** Using subtle shifts in the Material container tiers to signify a change in content focus.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked physical layers.
*   **Base:** `surface` (#fbf8fe)
*   **Sectioning:** `surface-container-low` (#f6f2f8)
*   **Interactive Cards:** `surface-container-lowest` (#ffffff) to create a subtle "lift" against the background.
*   **Emphasis Elements:** `primary-container` (#002d72) for deep-set, authoritative modules.

### The "Glass & Gradient" Rule
To escape the "flat" enterprise look, use **Glassmorphism** for floating navigation and status overlays. Apply `surface` colors at 80% opacity with a `20px` backdrop-blur. 
*   **Signature Texture:** Main CTAs should utilize a subtle linear gradient from `primary` (#001a48) to `on-primary-container` (#7a97e2) at a 135-degree angle. This adds "visual soul" and a metallic, professional sheen.

---

## 3. Typography: Editorial Authority

We use a dual-font strategy to balance character with legibility.

*   **Display & Headlines (Plus Jakarta Sans):** A modern sans-serif with geometric foundations. Used for `display-lg` through `headline-sm`. The wide apertures convey transparency and modernization.
*   **Body & Labels (Inter):** A highly legible, workhorse typeface. Used for all functional text (`body-md`, `label-sm`).
*   **The Hierarchy Goal:** Headlines should be significantly larger than body text (e.g., `display-md` at 2.75rem vs `body-lg` at 1rem) to create an editorial rhythm that guides the eye through complex logistics data.

---

## 4. Elevation & Depth: Tonal Layering

Traditional drop shadows are too "web 2.0." We achieve depth through atmospheric physics.

*   **The Layering Principle:** Instead of shadows, place a `surface-container-lowest` (#ffffff) card on a `surface-container` (#f0edf2) background. The contrast in luminance creates a natural, soft lift.
*   **Ambient Shadows:** If an element must "float" (like a mobile nav or a modal), use an ultra-diffused shadow:
    *   *Blur:* 40px
    *   *Spread:* -10px
    *   *Color:* `on-surface` (#1b1b1f) at 6% opacity. This mimics natural ambient occlusion.
*   **The "Ghost Border" Fallback:** If accessibility requires a stroke, use `outline-variant` (#c4c6d2) at **15% opacity**. Never use 100% opaque borders.

---

## 5. Components

### Service Cards
*   **Layout:** Asymmetric. Iconry/Imagery should bleed off the right edge of the card.
*   **Style:** No borders. Background: `surface-container-lowest`. 
*   **Interaction:** On hover, the card shifts from `surface-container-lowest` to `surface-bright`, accompanied by the Ambient Shadow.

### Hero Sections
*   **Composition:** Layered. A high-resolution image of logistics in motion should be masked with a `primary` (#001a48) gradient overlay. 
*   **Typography:** Overlap the headline (`display-lg`) across the image and a solid `surface` container to break the grid.

### Contact Forms & Inputs
*   **Fields:** Use `surface-container-high` (#eae7ed) as the fill color. No borders.
*   **States:** On focus, transition the background to `surface-container-lowest` and add a `2px` bottom-bar in `secondary` (#2b685b).
*   **Error State:** Use `error` (#ba1a1a) text with a `surface-container-highest` background to ensure the user feels "alerted" but not "attacked."

### Additional Components: The "Transit Tracker"
*   **Component:** A horizontal stepper representing shipment progress. 
*   **Style:** Use a `primary-fixed` (#dae2ff) track with a `tertiary` (#420002) indicator for the "current location" to utilize the vibrant red accent as a pinpoint of high-priority information.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use the `spacing-16` (4rem) token for section padding to allow the layout to breathe.
*   **Do** use `tertiary` (#420002) sparingly as an "Action Red"—only for critical CTAs or alerts.
*   **Do** align text to a strict baseline, but allow images and containers to break the vertical grid for a custom feel.

### Don’t
*   **Don't** use black (#000000) for text. Always use `on-surface` (#1b1b1f) for better readability and a more premium feel.
*   **Don't** use the `DEFAULT` (0.25rem) corner radius for large sections. Large containers should use `xl` (0.75rem) to soften the enterprise "hardness."
*   **Don't** use divider lines in lists. Use `spacing-4` (1rem) of vertical gap and subtle background alternating (`surface` vs `surface-container-low`).