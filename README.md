# Trip-Itinerary (TripPacer)

Offline-capable, pure-CSS mobile itinerary helper and getaway library designed for regional Pacific Northwest travel departing from Belltown, Seattle (2929 1st Ave).

## Available Itineraries

* **Historic Fairhaven (Bellingham, WA)** — `BellinghamDayTrip.html`
  * **Transit:** Monorail $\rightarrow$ Link Light Rail $\rightarrow$ Amtrak Cascades Northbound (Train 516 / 519)
  * **Highlights:** Taylor Dock boardwalk stroll over Bellingham Bay, lunch at Keenan's at the Pier, 19th-century brick village shopping.

* **Historic Centralia, WA** — `CentraliaDayTrip.html`
  * **Transit:** Monorail $\rightarrow$ Link Light Rail $\rightarrow$ Amtrak Cascades Southbound (Train 505 / 504)
  * **Highlights:** Historic 1912 Union Depot, lunch & craft beer at McMenamins Olympic Club, Tower Avenue antique district.

* **Mount Vernon & Skagit Valley** — `MountVernonDayTrip.html`
  * **Transit:** Monorail $\rightarrow$ Link Light Rail $\rightarrow$ Amtrak Cascades Northbound (Train 516 / 519)
  * **Highlights:** Skagit Riverwalk Trail, wood-fired lunch at Skagit River Brewery, historic 1st Street and Lincoln Theatre.

---

## Technical Architecture

* **Multi-Trip Library Hub (`index.html`):** Acts as the home launcher menu, allowing one-tap access to any trip without reinstalling or reconfiguring home screen shortcuts.
* **Pure CSS State Machine:** Drives step progression via hidden radio inputs (`<input type="radio">`) paired with CSS `:checked` siblings—eliminating all JavaScript.
* **Sandbox & Webview Immune:** Zero `<script>` tags ensures full compatibility across iOS Safari, Edge, email sandboxes, and content blockers.
* **100% Offline Capable:** Once loaded or added to the iPhone Home Screen, layout, pacing, and steps remain completely cached and responsive even through rail dead zones.
* **PWA & Viewport Optimized:** Utilizes `100dvh`, strict touch targets, and generous `safe-area-inset-bottom` padding to elevate controls safely above native iOS swipe-gesture lines.

---

## Adding a New Trip in the Future

1. **Create the Trip File:**
   * Click **Add file** $\rightarrow$ **Create new file** in GitHub (e.g., `BainbridgeDayTrip.html`).
   * Paste the 14-step pure-CSS template code and commit.

2. **Link It in the Launcher (`index.html`):**
   * Edit `index.html` and append a card link block to `<main class="trip-list">`:
     ```html
     <a href="YourNewTrip.html" class="trip-card">
       <div class="trip-info">
         <h2>Destination Name</h2>
         <div class="trip-meta">Transit Mode • Key Highlights • Dining</div>
       </div>
       <div class="trip-arrow">➔</div>
     </a>
     ```
   * Commit changes. The iPhone
