# Trip-Itinerary (TripPacer)

Offline-capable, pure-CSS mobile itinerary helper designed for train, ferry, and regional Pacific Northwest getaways.

## Current Active Itinerary
* **Route:** Belltown, Seattle (2929 1st Ave) to Historic Fairhaven (Bellingham, WA)
* **Mode:** Monorail, Link Light Rail, Amtrak Cascades (Business Class)
* **Highlight:** Taylor Dock boardwalk stroll & lunch at Keenan's at the Pier

## Technical Architecture
* **Pure CSS State Machine:** Uses hidden radio buttons (`<input type="radio">`) and CSS `:checked` selectors to advance steps.
* **Zero JavaScript:** Built without `<script>` tags to bypass mobile webview/email sandbox restrictions and prevent script crashes.
* **100% Offline Capable:** Once loaded or added to the iPhone Home Screen, all layout, timing, and transitions run locally with zero cellular or Wi-Fi dependency.

## Workflow to Update Trips
1. Update `index.html` with the new itinerary code generated in chat.
2. Commit changes to the `main` branch.
3. Open the GitHub Pages link on iPhone to refresh the offline cache.
