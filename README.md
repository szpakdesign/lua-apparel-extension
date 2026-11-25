# Lua Apparel: Chrome extension prototype

A clickable prototype of the Lua Chrome extension: a sample profile page on the left and the extension's side panel on the right.
Source of truth: Figma, section "7. Chrome extension" (screens 7.0 to 7.8) in the Lua Apparel file.

Static site, no build step. `index.html` is the whole prototype.

## What the prototype does

- The left side is a sample profile page (a fictional person, generated images) with 24 photos to scroll.
- The right side is the extension as a Chrome side panel.
- Hover a photo: it darkens and shows "Add to Lua". A click, or Alt + L while pointing at it, puts the photo on a ticked list in the panel; a second click takes it off.
- "Find outfits on this page" lists every photo from the top of the page down to the bottom edge of the window (what has loaded so far).
- "Add N images" marks the photos as "Added to Lua" on the page and shows a Toast in the panel.

States that are hard to reach by clicking open through the address:

- `?signin` starts signed out (Figma 7.6)
- `?fail` makes the first Add fail (Figma 7.7)
- `?empty` makes the search find nothing (Figma 7.8)

Not in Figma: the "Open Lua" button that brings the panel back after closing it.
