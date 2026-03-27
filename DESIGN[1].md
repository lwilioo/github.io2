# Design System: Modern Pathfinder

## 1. Overview & Creative North Star
The Creative North Star for this system is **"The Tactile Cartographer."** 

We are moving away from the "app-like" sterility of modern SaaS and toward a high-end editorial experience that feels like a premium field guide. This design system rejects the "boxed-in" layout of traditional web design in favor of **Organic Asymmetry**. 

By utilizing intentional overlapping, "floating" map-based textures, and a hierarchy driven by tonal depth rather than lines, we create a digital space that feels as vast and rugged as the trails themselves. We treat the screen not as a grid of pixels, but as a parchment map laid out on a wooden workbench.

---

## 2. Colors & Surface Philosophy

### The Tonal Palette
The palette is rooted in the natural world: Deep Forest Greens for authority, Earthy Browns for stability, and Parchment for the canvas.

*   **Primary (Forest):** `#17340e` (Base) | `#2d4b22` (Container)
*   **Secondary (Earth):** `#79573f` (Base) | `#ffd1b3` (Container)
*   **Surface (Parchment):** `#fcf9f0` (Base) | `#f1eee5` (Container Low)

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. To define a new content area, use a background shift. A `surface-container-low` section sitting on a `surface` background provides all the separation a user needs without the visual "clutter" of a stroke.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the surface-container tiers to create depth:
1.  **Level 0 (The Map):** `surface` (#fcf9f0) — The base background.
2.  **Level 1 (The Compass):** `surface-container-low` (#f6f3ea) — Large content blocks.
3.  **Level 2 (The Logbook):** `surface-container-highest` (#e5e2da) — Interactive cards and high-priority callouts.

### Signature Textures & Glass
*   **Topographic Overlays:** Apply a subtle SVG topographic texture at 5% opacity over `primary_container` or `surface_variant` areas.
*   **The Glass Rule:** For navigation bars or floating utility panels, use a semi-transparent `surface` color with a `backdrop-blur` of 12px. This creates a "frosted lens" effect that feels premium and integrated.

---

## 3. Typography: The Adventurer’s Typeface

Our typography is a dialogue between the technical and the human.

*   **The Explorer (Space Grotesk):** Used for all `display` and `headline` roles. Its wide, geometric stance feels like coordinates on a map—bold, adventurous, and precise.
    *   *Usage:* Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for hero sections to create an editorial, "title-page" feel.
*   **The Field Notes (Work Sans):** Used for `body`, `title`, and `label` roles. A clean, legible sans-serif that ensures clarity even when read on a sun-glared mobile screen mid-hike.
    *   *Usage:* Keep `body-lg` (1rem) as the standard for readability, using the `on_surface_variant` (#43483f) color to reduce harsh contrast against the parchment background.

---

## 4. Elevation & Depth: Tonal Layering

We do not use drop shadows to represent "elevation" in the traditional sense; we use **Ambient Light and Layering**.

*   **The Layering Principle:** Depth is achieved by stacking. A `surface_container_lowest` (#ffffff) card placed on a `surface_dim` (#dddad1) background creates a natural visual lift.
*   **Ambient Shadows:** If a component must float (e.g., a "Join Trip" FAB), use an ultra-diffused shadow. 
    *   *Spec:* `0px 20px 40px rgba(45, 75, 34, 0.08)` — Notice the shadow uses a tint of our Forest Green (`primary`) rather than black, mimicking natural light filtering through a canopy.
*   **The Ghost Border:** If a border is required for accessibility (e.g., in a high-contrast mode or complex form), use `outline_variant` (#c3c8bc) at **20% opacity**.

---

## 5. Components

### Buttons
*   **Primary:** Forest Green (`primary`) background with Parchment (`on_primary`) text. **Minimal 4px radius.**
*   **Secondary:** Earthy Brown (`secondary`) background. Use for secondary actions like "View Map."
*   **Ghost CTA:** No background, `Space Grotesk` uppercase, with a small arrow icon.

### Cards (The "Field Card")
*   **Forbid Dividers:** Do not use horizontal lines to separate card content. Use Spacing Scale `4` (1rem) or `6` (1.5rem) to create clear groupings.
*   **Visual Style:** `surface_container_lowest` background, 8px radius, with a subtle topographic texture in the corner.

### Inputs & Forms
*   **Field Style:** Use a "bottom-line only" approach or a very soft `surface_container_high` background. 
*   **Focus State:** Shift the background to `primary_fixed_dim` (#add19b) and transition the label color to `primary`.

### Specialized Components: "The Wayfinder"
*   **Path Tracking Progress:** A custom vertical stepper using a "dotted line" reminiscent of a trail on a map, with the active step marked by a Forest Green coordinate dot.
*   **Wood-Accent Badges:** Small chips using `secondary_container` (#ffd1b3) with a subtle grain texture to highlight trip difficulty (e.g., "Hard," "Expert").

---

## 6. Do’s and Don’ts

### Do
*   **Do use asymmetrical margins.** Allow some elements to "bleed" off the edge of the grid to create a sense of scale.
*   **Do use "Parchment" as your white space.** High-contrast pure white (#ffffff) should be reserved only for the most elevated interactive elements.
*   **Do stack surfaces.** Layering a light container on a slightly darker background is our primary way of showing hierarchy.

### Don't
*   **Don't use 1px solid borders.** They break the "Modern Pathfinder" immersion and make the site feel like a generic template.
*   **Don't use high-contrast shadows.** Avoid the "Material Design 2" look. Shadows should be felt, not seen.
*   **Don't over-round corners.** Keep to the 4px-8px range. We are building for "Rugged Utility," not "Soft Tech."