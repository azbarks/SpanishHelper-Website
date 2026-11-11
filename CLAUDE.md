# Spanish My Way Website — Claude Context

Static marketing / support site for the Spanish My Way iOS app (source: `../spanish-helper`).
Published as GitHub repo **azbarks/SpanishHelper-Website** with GitHub Pages (main, root) →
https://azbarks.github.io/SpanishHelper-Website/ — `../app_web/apps.html` links to it, so keep
that repo name and the page filenames. Same structure as the ScoreIt / BookIt / GrillIt sites — plain HTML + one
shared `style.css`, no build step, no JavaScript.

## Pages
- `index.html` — hero (phone mockup of the Today screen), trust bar, feature grid, how-it-works, band
- `help.html` — full guide, sidebar of sections; keep in sync with the app's behavior
- `privacy.html` — App Store privacy-policy URL
- `support.html` — App Store support URL (email azbarks@gmail.com)
- `style.css` — tokens + nav/footer/buttons. Colors from the app icon: deep green `#0E3D27`
  (nav), accent green `#157A48` (the "¿Qué?" bubble), red `#D22B3B` (the "¡Sí!" bubble), warm
  cream ground `#FBF6EE`; Bitter + Source Sans 3. Light + dark. Token names (`--ember`,
  `--flame`) are kept from the GrillIt stylesheet so page styles copy across.
- `images/` — `icon.png` (256), `favicon.png` (64), `apple-touch-icon.png` (180), resized from
  `../spanish-helper/Spanish_Icon.png` (= the app's AppIcon-1024).

## At release (TODO)
- `index.html` `#download`: swap the "Coming soon" badge for the real App Store button
  (commented template is right there), and change the hero tag to "Available now on the App Store".

## Keep accurate
- **Privacy page must match the app.** Spanish My Way makes **no network requests** of its own and
  asks for **no permissions**. The voice is Apple's on-device text-to-speech. The only outside
  link is the Dreaming Spanish YouTube channel (Talk → Watch), which opens YouTube/Safari. Data is
  SwiftData + UserDefaults on device — **not iCloud-synced**, included in the device backup.
  Export Backup (words + progress, line bookmarks, This Week counts, settings, story shelf) goes wherever the user sends it via the share sheet. If the app ever adds sync, a
  network call or a permission, update `privacy.html` and the App Store labels.
- **Help mirrors the app** — see `../spanish-helper/CLAUDE.md` for the behavior. Things it states
  that change if the app changes: default counts (Learn Something New 5 words / 3 phrases,
  Refresher 3, No Schedule page 10 words / 5 phrases, step goals 4 + 4, Listen answer time 4 s
  words / 6 s phrases); the swipe table (right: Pause / Less Often / Still Know It / Bring Back Now;
  left: Daily or More Often + Learned / Study Again + Never Remind); Sort buttons (I Know It, Know
  It Never Remind, Learn It, Not Now, Undo); the Refresher miss question (Study It Again = one
  correct day; Keep It Learned = first in the Refresher daily until right); "No past tense yet"
  (going to counts as present); 236 verbs; 57 stories in 3 levels; story shelf.
- Mexican Spanish only, as in the app: no vosotros, no Spain words.
