# Design System Specification: Clinical Serenity

## 1. Overview & Creative North Star
The "Clinical Serenity" system transcends the cold, sterile nature of traditional medical interfaces. Our Creative North Star is **"The Digital Sanctuary."** We aim to create an environment that feels authoritative yet calming, moving away from "software" and toward a high-end, editorial wellness experience.

This system rejects the rigid, boxed-in layouts of legacy healthcare portals. Instead, we embrace **Breathable Composition**: using expansive white space, intentional asymmetry, and soft tonal layering to guide the user’s eye. By layering semi-transparent surfaces and utilizing a sophisticated typographic scale, we establish a sense of "quiet competence" that builds deep patient trust.

## 2. Color & Surface Philosophy
The palette is rooted in professional medical blues, but its application is reimagined through the lens of depth and light.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning. Structural boundaries must be defined solely through background color shifts. A `surface-container-low` section sitting on a `surface` background provides all the definition a modern interface needs.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of fine, frosted glass. 
*   **Base:** `surface` (#f7f9fb)
*   **Low-Level Content Area:** `surface-container-low` (#f2f4f6)
*   **Primary Interactive Cards:** `surface-container-lowest` (#ffffff)
*   **Floating Navigation/Modals:** `surface-bright` (#f7f9fb) with Glassmorphism.

### The Glass & Gradient Rule
To avoid a flat, "templated" look, use **Glassmorphism** for floating elements (e.g., chat bubbles or sticky headers). Use semi-transparent surface colors with a `backdrop-blur: 20px` effect.
*   **Signature Textures:** For primary CTAs and hero backgrounds, use a subtle linear gradient: `primary` (#003d9b) to `primary_container` (#0052cc) at a 135° angle. This adds a "jewel-toned" depth that flat hex codes cannot replicate.

## 3. Typography: The Editorial Authority
We utilize a dual-font strategy to balance character with clinical clarity.

*   **Display & Headlines (Manrope):** Use Manrope for all `display` and `headline` tiers. Its geometric yet slightly softened terminals provide a modern, high-end editorial feel that commands attention without feeling aggressive.
*   **Body & Labels (Inter):** Use Inter for all functional text. It is the gold standard for legibility in dense medical data (vitals, dosages, and chat logs).

**Scale Highlights:**
*   **Display-LG (3.5rem):** Reserved for hero health scores or welcoming headers.
*   **Title-MD (1.125rem):** The workhorse for card titles and section headers.
*   **Label-SM (0.6875rem):** Used for micro-data in vitals cards, always in `on_surface_variant` (#434654).

## 4. Elevation & Depth
Hierarchy is achieved through **Tonal Layering** rather than traditional drop shadows.

*   **The Layering Principle:** Place a `surface-container-lowest` (#ffffff) card on a `surface-container-low` (#f2f4f6) background. This creates a natural "lift" that feels integrated into the environment.
*   **Ambient Shadows:** If an element must float (e.g., a critical "Emergency Call" FAB), use an extra-diffused shadow: `box-shadow: 0 12px 32px rgba(0, 61, 155, 0.06);`. Note the blue tint in the shadow—never use pure black or grey.
*   **The "Ghost Border":** If accessibility requires a container boundary, use the `outline_variant` (#c3c6d6) at **15% opacity**. High-contrast borders are strictly forbidden.

## 5. Component Guidelines

### Vitals Cards (The Signature Component)
*   **Structure:** No borders. Use `surface-container-lowest` with a `lg` (1rem) corner radius.
*   **Data Visualization:** Use `tertiary` (#7b2600) for heart rate or "alert" vitals to provide a sophisticated contrast to the primary blues.
*   **Spacing:** Use `24px` internal padding to ensure the data feels "curated" rather than "crammed."

### Chat Bubbles
*   **Patient (Primary):** Use the signature gradient (Primary to Primary-Container). Corner radius: `1rem` except for the bottom-right `0.25rem`.
*   **Provider (Secondary):** Use `secondary_container` (#d9e3f2) with `on_secondary_container` text.
*   **Layout:** Use a wide gutter (64px) on the opposing side of the bubble to create an asymmetrical, modern conversational flow.

### Buttons & Interaction
*   **Primary:** `primary` (#003d9b) background, `on_primary` (#ffffff) text. Use `full` (9999px) rounded corners for a friendly, approachable feel.
*   **Tertiary/Ghost:** No background or border. Use `primary` text. These are for low-emphasis actions like "View History."

### Progress Indicators
*   **Track:** `secondary_container` (#d9e3f2).
*   **Indicator:** `primary` (#003d9b).
*   **Styling:** Height should be `8px` with `full` rounded caps. For high-end "Health Goal" progress, add a subtle glow to the indicator head using a 4px blur of the primary color.

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical margins (e.g., a wider left-hand gutter) to create an editorial feel.
*   **Do** use `surface-container-high` for hovered states of cards to create tactile feedback through color shift.
*   **Do** prioritize typography over icons. Let the words lead the experience.

### Don't:
*   **Don't** use 1px dividers to separate list items. Use `16px` of vertical white space or a subtle background shift to `surface-container-low`.
*   **Don't** use pure black (#000000) for text. Use `on_surface` (#191c1e) to maintain a soft, high-end contrast.
*   **Don't** use "default" blue. Always refer to the specific `primary` (#003d9b) or `primary_container` (#0052cc) tokens to maintain the brand's professional depth.