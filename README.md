# Lua Apparel: Chrome extension prototype

Two versions, switched with "Version" in the bar at the bottom (the address's states are kept):

- **Minimal · Nov 26** (`/`, `index.html`): no side panel. A small window 344 px wide, 8 px from the top and right of the page (Figma, section "7. Chrome extension · Simple", component "Extension: Window"). Hover a photo for "Add to Lua" in its centre over a scrim; a click or Alt + L selects it (small Lua mark in the corner, hover shows "Remove" with an X). The window shows the count with "Add N images" and "Unselect all"; "Find all outfits on this page" (Alt + A) selects every photo loaded so far. The Toast sits under the window, as wide as it. Settings and Sign out are in the ··· menu. No dark mode. Shortcuts are set in IBM Plex Mono.
- **Side panel · Nov 25** (`/side-panel.html`): the first version, described below.

A clickable prototype of the Lua Chrome extension: a sample profile page on the left and the extension's side panel on the right.
Source of truth: Figma, section "7. Chrome extension" (screens 7.0 to 7.8) in the Lua Apparel file.

Static site, no build step. Each version is one HTML file.

## What the prototype does

- The left side is a sample profile page (a fictional person, generated images) with 24 photos to scroll.
- The right side is the extension as a Chrome side panel.
- Hover a photo: it darkens and shows "Add to Lua". A click, or Alt + L while pointing at it, puts the photo on a ticked list in the panel; a second click takes it off.
- "Find outfits on this page" lists every photo from the top of the page down to the bottom edge of the window (what has loaded so far).
- "Add N images" shows the photos loading in the panel (Figma 7.5), then marks them on the page with the small Lua mark in the corner and shows a Toast.
- A photo on the list carries the same mark. Hovering the photo turns the mark into an X; clicking it removes the photo from the list, or from Lua if it was already added (Figma 7.11).
- The grid has 2 px gaps and only its four outer corners are rounded.
- Motion uses the Serenity motion tokens (feedback 100 ms, enter 150 and 250 ms, exit 200 ms, stagger 50 ms): hover and press feedback, the button popping in on a photo, list items entering one after another, the Toast and the panel sliding, and none of it under reduced motion.

States that are hard to reach by clicking open through the address:

- The prototype starts signed out (Figma 7.7 Sign in); `?signedin` skips it
- `?fail` makes the first Add fail (Figma 7.7)
- `?empty` makes the search find nothing (Figma 7.8)

With the panel closed, a 24 px Lua mark in the top right corner opens it again (Figma 7.10).

## Dark mode and the bar at the bottom

- The extension has a Dark version (Figma "7.N.a Extension dark"); only the panel changes, the page being browsed stays as it is.
- The bar at the bottom is a prototype tool, not part of the extension: Light / Dark, and the states that are hard to reach by clicking (Sign in, Add fails, No outfits). `?theme=dark` opens the dark panel directly.
- The "more" button beside the heading opens a menu with the account (avatar), Settings and Sign out (Figma 7.12).
- Settings (Figma 7.13) replaces the panel content: Button on photos (switch, hides the hover button; Alt + L still works), Shortcut, Theme (Auto, Light, Dark; the same state as the bar) and an outlined button that opens the Lua Apparel settings in a new tab.
- As in Chrome, the page's top right corner is rounded next to the open panel and the panel's colour shows behind it; there is no line between the page and the panel.
- Icons in the panel menu and settings (more, settings, sign-out, arrow-left, external-link) are the Serenity 2 stroke icons, exported from the library (24 px grid, 1.5 stroke, drawn at 16). The menu has a Serenity Separator after the account row: 1 px Stroke/Default with 4 px above and below.
- Minimal version, Nov 26: the window's description text is 16/24 (Body/Large); the ready view has one two-line description. Every view has a close button at the top right (More sits to its left); it turns the extension off, leaving a 24 px Lua button in the corner that turns it back on (Figma 7.14).
