# Design System Document: Financial Clarity & Depth

## 1. Overview & Creative North Star
### Creative North Star: "The Digital Ledger of Light"
This design system moves away from the utilitarian, flat "budgeting spreadsheet" aesthetic toward a premium, editorial-grade financial experience. We treat financial data not just as numbers, but as a narrative of a user’s life. 

The system is built on **Tonal Layering** and **Intentional Asymmetry**. Instead of rigid grids and heavy borders seen in standard dashboard templates, we use varying depths of indigo and midnight blue to create a sense of infinite space. By utilizing high-contrast typography and sophisticated glassmorphism, we turn a budget tracker into a high-end personal concierge. The goal is to make the user feel "in control" and "prosperous" through a visual language that suggests stability, precision, and modern elegance.

---

## 2. Colors
Our palette is rooted in deep, midnight blues (`background: #0b1326`) to provide a restful environment for complex data.

### Palette Strategy
- **Primary Logic:** We use `primary (#c0c1ff)` for core interactions. This soft violet-blue provides high legibility against the dark background without the "neon vibration" of standard blue.
- **The Income/Expense Harmony:** 
    - **Income (Secondary):** `#4edea3`. A fresh, emerald-tinted mint that signals growth without looking like a generic "Go" button.
    - **Expense (Tertiary):** `#ffb2b7`. A sophisticated coral-pink rather than a harsh "Error Red," making financial tracking feel less punitive and more analytical.
- **The "No-Line" Rule:** Explicitly prohibit 1px solid borders for sectioning. To separate the "Add Transaction" card from the "Recent Transactions" list, do not use a line. Use a shift from `surface_container_low (#131b2e)` to `surface_container (#171f33)`.
- **Surface Hierarchy:** 
    - Base Layer: `surface (#0b1326)`
    - Secondary Sections: `surface_container_low (#131b2e)`
    - Active Cards/Modals: `surface_container_high (#222a3d)`
- **The "Glass & Gradient" Rule:** Use `backdrop-blur` (16px–32px) on floating elements like navigation bars or detail overlays. Apply a subtle linear gradient from `primary` to `primary_container` on main CTAs to add a "gem-like" luster.

---

## 3. Typography
We employ a dual-font strategy to balance editorial flair with technical precision.

- **Headlines & Display (Manrope):** Chosen for its modern, geometric structure with a touch of warmth. Use `display-lg` (3.5rem) for main balance figures to emphasize wealth and clarity.
- **Data & Labels (Inter):** Used for transactional data and small labels (`label-md`, `label-sm`). Inter's high x-height ensures that currency symbols and dates remain legible even at 11px.
- **Editorial Contrast:** Create visual interest by pairing a `headline-lg` title (Manrope, Semibold) with a `label-md` (Inter, Medium, All-Caps, Tracking 5%) for secondary metadata.

---

## 4. Elevation & Depth
In this system, depth is a function of light, not lines.

- **The Layering Principle:** Stacking should follow natural light patterns. A `surface_container_highest (#2d3449)` card should only sit on a `surface_container` background. This creates "soft lift."
- **Ambient Shadows:** Standard drop shadows are forbidden. If a card must float, use a 40px blur with 6% opacity, using the `on_background` color as the shadow tint. This mimics a natural shadow in a dark room.
- **The "Ghost Border" Fallback:** For input fields or cards that require extreme definition, use the `outline_variant (#464554)` at 15% opacity. It should be felt, not seen.
- **Glassmorphism:** Use `surface_tint` at 5% opacity with a blur for top-level navigation. This allows the vibrant colors of the charts to bleed through subtly as the user scrolls, creating an integrated, high-end feel.

---

## 5. Components

### Cards & Lists
*   **The Rule:** No dividers. Use `spacing-6` (1.5rem) between transaction items.
*   **Transactions:** Use a `surface_container_low` background for the row. On hover, transition to `surface_container_high`.
*   **Rounding:** Apply `xl` (1.5rem) for main dashboard cards and `md` (0.75rem) for internal elements like chips or input fields.

### Buttons
*   **Primary:** Background: `primary_container`; Text: `on_primary_container`. No border. Shape: `full`.
*   **Secondary (Income/Expense toggle):** Use `secondary_container` for Income and `tertiary_container` for Expenses. Use `surface_bright` for the "unselected" state to maintain contrast.

### Input Fields
*   **Anatomy:** No 100% opaque borders. Use a `surface_container_highest` fill with a `sm` (0.25rem) corner radius.
*   **States:** On focus, the "Ghost Border" becomes `primary` at 50% opacity, and the label should shift to `primary` color.

### Charts & Data Viz
*   **Sophisticated Curves:** Line charts must use a Bezier curve (0.4 tension) rather than jagged points.
*   **Gradients:** Use vertical gradients on area charts, transitioning from the category color (Secondary/Tertiary) at 30% opacity down to 0% at the baseline.

---

## 6. Do's and Don'ts

### Do
- **Do** use `spacing-8` (2rem) as your standard margin for dashboard sections to allow the data to breathe.
- **Do** use `on_surface_variant` for "time-stamps" or "category" labels to create a clear visual hierarchy against the white/blue primary text.
- **Do** use "Full" rounded corners for buttons and "XL" for cards to soften the data-heavy nature of the app.

### Don't
- **Don't** use pure black `#000000` or pure white `#FFFFFF`. Always use the tokens `surface` and `on_surface` to maintain the sophisticated tonal range.
- **Don't** use lines to separate chart axes. Use the `outline_variant` at 10% opacity or simply rely on the labels to define the bounds.
- **Don't** place a high-contrast shadow on a `surface_container_lowest` element; keep the "light" consistent across the entire interface.