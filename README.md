# FuelTrack V6 — Smart Food Diary

A free mobile-friendly nutrition PWA for Android and iPhone. V6 builds directly on V5, retains the original localStorage key `fueltrack-v2`, and preserves barcode lookup, custom foods, macros and weight logging.

## New in V6
- Smart Log: describe meals in text, match foods in the built-in offline nutrition library, estimate portions and preview macros.
- Optional browser speech recognition (availability differs by phone/browser; Android keyboard dictation can be used instead). Recognition may use the browser vendor’s online speech service.
- Camera/photo input shows a temporary reference photo; **does not recognise foods automatically**, transmit or save photos.
- Review and change portions and select foods before adding to the existing diary. Unknown foods require manual entry.

Nutrition matches are rule-based approximations, not AI. Verify values. AI photo recognition and conversational coaching require a separate securely hosted backend and are **not included**.

## Update GitHub Pages
1. Back up your data from FuelTrack Settings on your phone.
2. Replace `index.html` and `sw.js` in your `fueltrack` repository with the V6 copies. Other files remain unchanged.
3. Commit both changes, then reload the hosted website. Close and relaunch the home-screen app. Look for V6 at the top.
4. Test Smart Log with `250g chicken breast, 150g rice and 100g broccoli`.

Data is stored on the current device and not synchronised. GitHub Pages only publishes the application code, not your diary data.
