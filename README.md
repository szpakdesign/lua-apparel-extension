# Lua Apparel: Chrome extension prototype

A clickable prototype of the Lua Chrome extension: a sample profile page on the left and the extension's side panel on the right.
Source of truth: Figma, section "7. Chrome extension" (screens 7.0 to 7.8) in the Lua Apparel file.

Static site, no build step. `index.html` is the whole prototype.

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

- `?signin` starts signed out (Figma 7.6)
- `?fail` makes the first Add fail (Figma 7.7)
- `?empty` makes the search find nothing (Figma 7.8)

With the panel closed, a 24 px Lua mark in the top right corner opens it again (Figma 7.10).

## Dark mode and the bar at the bottom

- The extension has a Dark version (Figma "7.N.a Extension dark"); only the panel changes, the page being browsed stays as it is.
- The bar at the bottom is a prototype tool, not part of the extension: Light / Dark, and the states that are hard to reach by clicking (Sign in, Add fails, No outfits). `?theme=dark` opens the dark panel directly.
