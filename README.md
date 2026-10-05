# Berry Vibes Studio × CCD — V4 GitHub Website

A multi-page HTML/CSS/JavaScript CCD website with an optional Node backend. This version keeps the existing food, recipe, movement, fasting, restaurant, grocery, calendar, period, settings, authentication, and social features and adds a cinematic home header, richer social media, and saved recipe modifications.

## V4 highlights

- **Large animated homepage image header** inspired by modern cinematic/parallax website headers.
  - Full-width large visual header at the very beginning of `index.html`.
  - Auto-advancing slides, PREV/NEXT controls, progress dots, slide counter, swipe/pointer gestures, and subtle pointer parallax.
  - On the homepage the private navigation floats directly over the hero with no white navigation box.
- **Social media photo + video posting** on `social.html`.
  - Up to four media files per post.
  - JPG/PNG/WEBP/GIF images and MP4/WEBM/MOV videos.
  - Posts may be media-only; a text caption is optional.
  - Local GitHub Pages mode stores social media blobs in IndexedDB when available so the post metadata does not have to contain a huge video string.
  - The Node backend now accepts image/video uploads up to 20 MB each and serves uploaded video MIME types correctly.
- **More active social experience**.
  - Community Stories / Active Now strip.
  - Multiple seeded community profiles and an active sample feed.
  - Trending topics and live community pulse cards.
  - Like, comment, share, delete-own-post, feed filters, follow/unfollow, private follow requests, approve/deny, refresh, and public/private profiles.
  - Full profile viewer includes bio, location, post/follower/following counts, media gallery, recent posts, and full-size image/video viewer.
  - Social profile photo can be edited separately.
- **Recipe modification / remix workflow on Food Log**.
  - Exact field label: **“THE ONLY THING I CHANGED FROM THE RECIPE I CREATED WAS....”**
  - Select an original CCD food/recipe, describe your changes, optionally rename the version, and save it.
  - Saved modified versions have LOAD, EDIT, and DELETE actions.
  - Logged food entries can preserve the modification note and modified recipe name.

## Existing major features kept

- 220 recovered CCD / food entries and reactive Breakfast / Lunch / Snack / SOTD / Dinner filters.
- Food + drink logging, photos, recipe-card uploads, serving scaling, automatic nutrition.
- Recipe vault + builder lab + grocery custom ingredients.
- Start → finish exercise logging with automatic duration and estimated movement burn.
- Fasting logs, SOTD, restaurant vault, Food Comparison Battle, horizontal macro charts and horizontal food pyramid.
- Editable planning calendar with log editing/deletion, plans, and day water controls.
- Interactive period tracker.
- Grocery page with custom ingredients, cart, wishlist, saved items, quality choices, recommendations, purchase history and daily recipe recommendations.
- Settings page and editable profile (`5'2` feet/inches format).
- Sign in / sign up / password recovery pages with the private menu hidden until authentication.

## Social storage modes

### GitHub Pages / browser account mode
The site can run entirely on static GitHub Pages. Accounts/social state are local to that browser. Social media is stored in IndexedDB when available; this is a browser-local community demo and does not sync between devices/users.

### Node backend mode
Deploy the included `server.js` (for example with the included `render.yaml`) and set `API_BASE` in `config.js`. Backend mode provides server accounts, upload persistence and cross-account social synchronization. Uploaded social videos/images are stored under `uploads/` on that server. For long-term production use, replace local-disk uploads/JSON storage with durable object storage and a real database.

## GitHub Pages
Upload all root files and folders to your repository. Set GitHub **Settings → Pages → Deploy from a branch → main → /(root)**.

The Node backend does not run on GitHub Pages itself; it must be deployed separately if cross-user server sync is wanted.
