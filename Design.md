# Design System Document

## 1. Overview & Creative North Star
**Creative North Star: The Scholastic Monolith**
This design system rejects the cluttered, line-heavy aesthetic typical of academic software. Instead, it adopts the persona of "The Scholastic Monolith"—a space defined by architectural weight, intellectual clarity, and editorial breathing room. By moving away from traditional wireframe boxes, we create a student experience that feels less like a utility and more like a high-end publication.

The system utilizes intentional asymmetry and tonal depth to guide the student’s eye. Hierarchy is not forced through bold lines, but through the "gravity" of typography and the subtle "stratification" of surfaces.

## 2. Colors
The palette is restricted to a sophisticated grayscale to ensure the focus remains on information architecture and structural intent.

| Role | Token | Hex | Application |
| :--- | :--- | :--- | :--- |
| **Primary** | `primary` | #212121 | High-emphasis actions and "Monolith" headers. |
| **Surface** | `surface` | #F5F5F5 | The base canvas of the portal. |
| **Container (Low)** | `surface-container-low` | #F3F3F3 | Subtle sectioning for secondary information. |
| **Container (Lowest)**| `surface-container-lowest` | #FFFFFF | Active "Elevated" content (cards, active inputs). |
| **Outline Variant** | `outline-variant` | #E0E0E0 | Used exclusively for Ghost Borders. |
| **On Surface** | `on-surface` | #212121 | Primary body text and icons. |

### The "No-Line" Rule
Standard 1px solid borders are strictly prohibited for sectioning. Boundaries must be defined through **Background Tonal Shifts**. For example, a student’s "Current Courses" list should sit on a `surface-container-low` background, distinguished from the main `surface` by color alone.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of paper. 
*   **The Desk (`surface`):** The main background.
*   **The Folder (`surface-container`):** Grouped sections.
*   **The Sheet (`surface-container-lowest`):** Individual items like cards or notifications.
By nesting a white card (`lowest`) inside a light gray section (`low`), we create depth without a single line.

### Glassmorphism & Tonal Soul
For floating elements like Top Bars or Modals, use `surface` colors with a 80% opacity and a **24px backdrop-blur**. This "frosted glass" effect prevents the portal from feeling flat or "dead."

## 3. Typography
We utilize **Inter** to bridge the gap between technical precision and academic elegance.

*   **Display (lg/md):** Used for large "Welcome" messages or grade averages. These should have a slight negative letter-spacing (-0.02em) to feel "tight" and authoritative.
*   **Headline (sm):** Used for primary section titles. Always in `#212121`.
*   **Body (md):** The workhorse for all student reading materials. Ensure a line height of at least 1.6 for maximum legibility.
*   **Label (sm):** Used for metadata (e.g., "Submission Date"). These should be in `secondary` tones to recede in the hierarchy.

## 4. Elevation & Depth
In this design system, shadows and lines are secondary to **Tonal Layering**.

*   **The Layering Principle:** Place a `#FFFFFF` card on a `#F5F5F5` background to create a "Natural Lift."
*   **Ambient Shadows:** For floating elements (e.g., a "New Message" popover), use a shadow with a 32px blur at 4% opacity. The shadow color should be `#212121`.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility (e.g., input fields), use `outline-variant` (#E0E0E0) at 20% opacity. It should be felt, not seen.
*   **Intentional Asymmetry:** Avoid perfectly centered grids. Align headers to the far left with a generous 64px–128px margin to create an editorial, "premium" feel.

## 5. Components

### Buttons
*   **Primary:** Solid `#212121` with `#FFFFFF` text. Use `lg` (0.5rem) roundedness. No border.
*   **Secondary:** Ghost style. No background, only a "Ghost Border" (20% `outline-variant`).
*   **Tertiary:** Text-only. Use `title-sm` typography with an underline on hover.

### Cards & Lists
*   **Rule:** Forbid divider lines between list items.
*   **Implementation:** Use 16px of vertical whitespace between items. For lists of grades or assignments, use a alternating tonal shift (Zebra striping) using `surface-container-low` and `surface-container-lowest`.

### Form Fields
*   **Input Fields:** Use `surface-container-lowest` (#FFFFFF) with a Ghost Border. On focus, the border opacity increases to 100% (using `outline`).
*   **Labels:** Use `label-md` positioned strictly 8px above the input. Never place labels inside the field.

### Simple Tables
*   Tables must be "headless" or have a very subtle `surface-container` header background. Remove all vertical lines. Only use a 1px `outline-variant` (10% opacity) for horizontal row separation if the data is extremely dense.

### Navigation (Sidebar & Top Bar)
*   **Sidebar:** Fixed width (280px). Use a subtle gradient from `surface` to `surface-container` to indicate depth.
*   **Top Bar:** 100% width, using the Glassmorphism rule (backdrop-blur) to stay integrated with the scrollable content behind it.

## 6. Do's and Don'ts

### Do:
*   Use massive amounts of white space (minimum 48px between major sections).
*   Align typography to a strict vertical rhythm.
*   Use background color shifts to indicate hover states.

### Don't:
*   **Do not** use 100% black (#000000). Use #212121 to keep the "Editorial" softness.
*   **Do not** use standard "Drop Shadows" with high opacity.
*   **Do not** use borders to separate the Sidebar from the Main Content; use a tonal step-down (e.g., Sidebar is `#FFFFFF`, Content is `#F5F5F5`).
*   **Do not** use icons without accompanying labels; in an academic context, clarity is king.