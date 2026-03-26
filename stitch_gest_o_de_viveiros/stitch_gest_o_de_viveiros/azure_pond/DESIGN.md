# Design System Document: Precision Aquaculture

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Aquaculturist"**
This design system moves away from the "cluttered industrial dashboard" stereotype. Instead, it embraces an **Editorial-Precision** aesthetic. It treats complex shrimp farming data—water salinity, biomass growth, and AI-driven feed cycles—with the same clarity and elegance found in a high-end scientific journal. 

The system creates a "Hybrid Utility" experience: high-altitude, soft-focus dashboards for executive decision-making, and "Brutalist-Efficient" data grids for granular pond operations. We break the template look by utilizing **Tonal Layering** instead of borders, creating an interface that feels like a singular, integrated glass surface rather than a collection of disjointed boxes.

---

## 2. Colors & Surface Philosophy
We utilize a sophisticated Material Design-inspired palette to move beyond flat #0ea5e9 blue into a spectrum of depth.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders (`#6e7881`) for sectioning or layout containment. Structural boundaries must be defined solely through:
1.  **Background Shifts:** Placing a `surface_container_lowest` (#ffffff) panel on a `surface` (#f8f9fa) background.
2.  **Tonal Transitions:** Using `surface_container_low` (#f3f4f5) to group related operational controls.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of "Fine Paper" or "Frosted Glass." 
*   **Base Layer:** `surface` (#f8f9fa) – The global canvas.
*   **Secondary Layer:** `surface_container_low` (#f3f4f5) – Used for the Sidebar and TopBar backgrounds.
*   **Priority Layer:** `surface_container_lowest` (#ffffff) – Used for active workspace panels and dashboard cards.

### Signature Textures & Glassmorphism
*   **AI Elements:** The Floating AI Assistant must use a **Glassmorphism** effect: `surface_container_lowest` at 70% opacity with a `backdrop-blur: 12px`.
*   **Brand Soul:** Use a subtle linear gradient for primary CTAs: `primary` (#006591) to `primary_container` (#0ea5e9) at a 135° angle. This adds a "liquid" depth appropriate for AgTech.

---

## 3. Typography: The Inter Compact Scale
We use **Inter** with tight tracking (-0.011em to -0.022em) to maintain an authoritative, high-density look.

| Level | Token | Size | Weight | Use Case |
| :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-md` | 2.75rem | 700 | Large KPI metrics (e.g., Total Biomass) |
| **Headline**| `headline-sm`| 1.5rem | 600 | Pond Name or Section Header |
| **Title**   | `title-sm`   | 1.0rem | 500 | Card titles & Sidebar Categories |
| **Body**    | `body-md`    | 0.875rem| 400 | General descriptions |
| **Label**   | `label-sm`   | 0.6875rem| 600 | **The Grid Standard:** Column headers & Data tags |

*Editorial Note:* For operational grids, force `Inter` to 13px (between `label-md` and `body-sm`) to maximize information density without sacrificing legibility.

---

## 4. Elevation & Depth
### The Layering Principle
Do not use shadows for static layout elements. Achieve separation by "nesting." A `surface_container_lowest` card sitting on a `surface_container` background provides a soft, organic lift.

### Ambient Shadows
Shadows are reserved for "Floating" elements (Modals, AI Assistant). 
*   **Token:** `box-shadow: 0 12px 32px -4px rgba(0, 30, 47, 0.06);`
*   The shadow is tinted with `on_primary_fixed` (#001e2f) at very low opacity to mimic natural light filtered through water.

### The "Ghost Border" Fallback
If high-density data grids require separation, use a **Ghost Border**: `outline_variant` (#bec8d2) at **15% opacity**. This provides a visual guide without "cutting" the interface into fragments.

---

## 5. Components

### The Sidebar & TopBar
*   **Sidebar:** `surface_container_low`. No border on the right. Use a `3.5` (0.7rem) vertical padding between nav items. Active state: A subtle `primary_fixed` (#c9e6ff) left-accent bar (4px).
*   **Multi-tenant Selector:** Styled as a "pill" using `rounded-full`. Background: `surface_container_high`. Text: `on_surface_variant`.

### Data Grids (Operations)
*   **Constraint:** Forbid divider lines between rows. Use a subtle hover state: `surface_container_highest` (#e1e3e4).
*   **Density:** Cell padding `2` (0.4rem) top/bottom, `4` (0.9rem) left/right.
*   **Action Buttons:** "Import/Export" use `secondary_container` (#b8dffe) with `on_secondary_container` (#3d637d) text. No fill, just a soft tonal background.

### Floating AI Assistant (Sparkles)
*   **Shape:** `rounded-xl` (0.75rem).
*   **Surface:** Glassmorphic (70% white, 12px blur).
*   **Icon:** `primary` (#006591) sparkles with a soft glow effect (`drop-shadow` using `primary_fixed`).

### Buttons & Inputs
*   **Primary Button:** Gradient (`primary` to `primary_container`). `rounded-md`.
*   **Input Fields:** `surface_container_lowest` with a `Ghost Border` on focus. Labels must be `label-sm` in `on_surface_variant` (#3e4850), positioned 4px above the input.

---

## 6. Do's and Don'ts

### Do
*   **DO** use whitespace (Spacing scale `8` and `12`) to separate dashboard sections rather than lines.
*   **DO** use `tertiary_container` (#de8712) for cautionary AI-derived insights—it stands out from the "Blue" ocean of data.
*   **DO** maintain "compact" line-height (1.2 - 1.3) for all data-heavy grid text.

### Don't
*   **DON'T** use 100% black (#000000) for text. Always use `on_surface` (#191c1d) to keep the "Editorial" softness.
*   **DON'T** use standard "Drop Shadows" on cards. If a card needs to pop, increase its surface lightness to `surface_container_lowest` and use a `Ghost Border`.
*   **DON'T** use rounded-full for everything. Reserve `full` for status chips and the AI bubble; use `md` or `lg` for structural panels to maintain an "Architectural" feel.