# TripPacer Library

A mobile-first, zero-dependency travel itinerary runner optimized for regional Pacific Northwest day trips, overnight getaways, and local doorstep walking excursions originating from downtown Seattle.

Built specifically for hands-free and mobile field use on iOS Safari and modern mobile browsers.

---

## Architecture & Features

- **Zero-Dependency Engine:** Pure client-side HTML, CSS, and lightweight vanilla JavaScript. No node modules, build tools, external CDNs, or server runtimes.
- **Dynamic Step Sizing:** Itineraries dynamically calculate their own total steps (`Step 1 of N`). Outings adapt naturally to however many stops are required—from quick 6-step neighborhood walks to 18-step regional multi-modal rail journeys—with zero artificial filler.
- **Automated Navigation Controls:** 
  - Dynamic **Back** and **Next** progression.
  - Automatic conversion to a blue **Finish ➔** button on the final step.
  - Native **Up Next** chronological preview cards.
- **Tab State Persistence:** Bottom **⌂ Menu** and **Finish** buttons route back to specific URL category anchors (`#day`, `#overnight`, `#local`), guaranteeing iOS Safari preserves the active filter tab when returning to the library.
- **Mobile-First Layout:** Designed to accommodate iOS safe areas (Dynamic Island / home bar) with fixed touch targets and high-contrast night styling.

---

## Repository Structure

- `index.html` — The main portal and categorized library runner. Contains the tabbed segmented filter (`Day Trips`, `Overnights`, `Local Walks`).
- `[TripName].html` — Self-contained itinerary files powered by the internal template engine.

---

## How to Add a New Itinerary

Follow this standard 2-step workflow to add a new trip to the library:

### 1. Create the New Trip File
1. In the repository root, create a new file (e.g., `FridayHarbor.html`).
2. Copy and paste the standard **TripPacer Dynamic Template** into the file.
3. Update the `TRIP_CONFIG` block at the top of the `<script>` tag:
   - `title`: Display title in the header (e.g., `"Friday Harbor Day Trip"`).
   - `returnHash`: Target category tab (`"#day"`, `"#overnight"`, or `"#local"`).
   - `steps`: An array of step objects containing `time`, `tag`, `title`, and an array of `bullets`.
4. Save and commit the file.

### 2. Add the Card to `index.html`
Open `index.html` and add a new card link under the appropriate section:
- `#list-day` for Day Trips
- `#list-overnight` for Overnight Getaways
- `#list-local` for Local Walks & Excursions

```html
<a href="YourFileName.html" class="trip-card">
  <div class="trip-info">
    <h2>Destination — Subtitle or Route</h2>
    <div class="trip-time-window">⏱ Departure – Return • ~Total Duration</div>
    <div class="trip-meta">Transit Mode • Primary Highlights • Dining</div>
  </div>
  <div class="trip-arrow">➔</div>
</a>
