# UI & Styling Specification

## 1. Responsive Design Layouts
Optimized for mobile touchscreens first, scaling elegantly up to desktop viewports.

### Minimal Hero & Header
* No massive or bulky hero blocks. 
* Implement a simple, cozy header featuring a styled serif text logo ("The Good Web.") and an instant utility search input.
* **Header Collapse on Mobile**: In desktop view, a wide search text field must sit visible in the header. In mobile layout view, the text field collapses into a simple magnifying glass icon button that opens a clean search drawer/overlay when tapped.
* Directly beneath the header, add a clean, friendly, one-line sentence that instantly outlines the value proposition: "A quiet corner of the internet gathering useful websites that don't require your money or a credit card."

### Grid & Mobile Padding Layout
* **Bootstrap Card Grid**: You must implement a strict, responsive 3-column Bootstrap layout structure using card decks. Use the exact classes: `row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4`.
* **Mobile Padding Fix**: To stop elements from sticking directly to the edge of mobile screens, apply consistent horizontal padding container wrappers (`px-3` or `container`) to both the category headers and the navigation chip sections. Category items must never touch the absolute left or right viewport edges on mobile devices.

### Desktop Layout
* **Navigation Shelf**: A grid of pill-shaped navigation chips under the header acting as fast anchor jumps down to specific categories.
* **Link Matrix**: Renders in a responsive 3-column layout. Individual items sit inside elevated border cards that lift visually on pointer hover.

### Mobile Layout
* **Navigation Chips**: Wraps seamlessly into a multi-row "Grid of Chips" to prevent horizontal scrolling navigation fatigue.
* **Link Matrix**: Collapses completely into a unified, single vertical stack of cards spanning screen width.
* **Tappable Targets**: Action buttons for visiting a tool scale up to wide, thumb-friendly tap bounds.

## 2. Dynamic Features

### Real-Time Content Filter Search Mechanics
* **Instant Dynamic Replacement**: When a user types a query into the search input box, do not scroll the page or highlight individual blocks. The JavaScript engine must instantly hide all irrelevant categories and non-matching link cards entirely from view.
* **Filtered Canvas State**: Only the card grid items containing text strings or tags that match the search input will remain visible on the screen, neatly replacing the homepage content canvas in real-time.
* **Reset States**: Tapping an "All Categories" chip button or clearing out the text inside the search bar must instantly reset the filter state, making all category blocks and cards fully visible again.

### Theme Engine & Curated Vectors
* Do NOT use default system emojis (like ☀️ or 🌙) for the theme switcher, as they conflict with the curated look.
* Integrate clean, professional SVG vector inline icons (such as Bootstrap Icons or Lucide Icons) for the theme mode presentation.
* The button toggles seamlessly, manages state tokens, targets operating system defaults on initial load, and saves state to `localStorage`.

### Card Content Component Architecture & Signup Badges
Every individual website listing must be wrapped inside a standard Bootstrap card element (`class="card h-100 shadow-sm"`). The internal hierarchy of the card must follow this precise order from top to bottom:
1. **Card Header/Title Row**: A small vector icon container followed immediately by the tool's name in a bold heading (`class="card-title d-flex align-items-center gap-2"`).
2. **Card Body**: A clean, short paragraph tracking the site description (`class="card-text text-muted small"`).
3. **Card Footer Action Row**: A unified layout row placed cleanly at the base of the card (`class="card-footer d-flex justify-content-between align-items-center bg-transparent border-0 mt-auto"`):
   * **Left Side**: A low-profile anchor button styled to "Visit Site".
   * **Right Side**: If `requires_signup` is true, render a small, minimalist pill-shaped indicator badge reading "Requires Signup". The background of this badge must use a subtle, low-contrast tone that matches the chosen light or dark theme mode perfectly. If false, emit no markup.

### Disclosure Section
* Located at the base of the page as a distinct, beautifully designed section right before the final footer.
* Styled visually to resemble a clean notebook entry or open letter acknowledging our aggregation and validation of assets inspired by public community lists like FMHY and GitHub Awesome repositories.

## 3. Typography
* **Headings & Branding (h1, h2, h3)**: 'Lora' (Serif Google Font) for an editorial, custom library aesthetic.
* **Descriptions & Badges**: 'Plus Jakarta Sans' (Sans-serif Google Font) for sharp interface text.

## 4. Dual-Theme Color Engine (Bootstrap 5 Modes)
All styling declarations must exist within `src/css/style.css`. Use strict CSS custom variables mapped to Bootstrap's `data-bs-theme` properties. Pure white (`#ffffff`) or pure black (`#000000`) bases are prohibited.

### Light Mode (`data-bs-theme="light"`)
* Background: `#fbf9f4` (Cozy warm off-white)
* Main Text: `#2b2d42` (Dark charcoal)
* Muted Text: `#6c757d` (Soft grey)
* Card Background: `#ffffff` (Crisp white)
* Structural Borders: `#eae6df` (Warm sand divider)
* Active Accents: `#d96b43` (Terracotta orange)
* Signup Pill Background: `#f0ede6` (Subtle sand tint)

### Cozy Dark Mode (`data-bs-theme="dark"`)
* Background: `#1a1816` (Dark cocoa charcoal)
* Main Text: `#f4ebd9` (Reading paper cream)
* Muted Text: `#a89f91` (Warm sand)
* Card Background: `#24211e` (Sepia tint grey)
* Structural Borders: `#332f2a` (Deep earth divider)
* Active Accents: `#e08253` (Vibrant terracotta amber)
* Signup Pill Background: `#2d2925` (Subtle deep brown tint)
