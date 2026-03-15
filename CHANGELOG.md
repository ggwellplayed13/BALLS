# Changelog

All notable changes to this project are documented here.

## [Unreleased]

### Fixed — Category A: Emoji Rendering

- Replaced all emojis in rendered text with ASCII alternatives (Pillow cannot render color/Unicode emojis with standard fonts — they appear as rectangles)
- `☠` in elimination feed → `X`
- `⚡ NEW CHALLENGE! ⚡` → `>> NEW CHALLENGE! <<`
- Challenge banner format now uses `[ name ]` brackets instead of emoji wrapping
- `🔴 BRAINROT BATTLE ROYALE 🔴` → `> BRAINROT BATTLE ROYALE <<`
- Timer `⏱ {t}s` → `T: {t}s`
- Challenge sidebar prefixes: `✅` → `[X]`, `▶️` → `>>>`, `⏳` → `...`
- Engagement hooks: removed trailing emojis from all hook strings
- Subscribe button: `👆 SUBSCRIBE 👆` → `> SUBSCRIBE <<`
- Milestone alerts: `🔥 TOP 10! 🔥` → `** TOP 10! **`, `⚡ FINAL 5! ⚡` → `** FINAL 5! **`, `💀 1v1 FINAL! 💀` → `** 1v1 FINAL! **`
- Countdown overlay: `💀 100 BRAINROT BALLS • 1 SURVIVES 💀` → `100 BRAINROT BALLS - 1 SURVIVES`, `🎲 7 RANDOM CHALLENGES THIS ROUND 🎲` → `7 RANDOM CHALLENGES THIS ROUND`
- Winner screen: `🏆 WINNER! 🏆` → `★ WINNER! ★`, winner name wrapped in `[ ]` brackets, `💪 LAST BALL STANDING! 💪` → `** LAST BALL STANDING! **`
- Engagement hooks: trailing emojis removed from all comment prompts
- All `emoji` fields in challenge `_register` calls replaced with ASCII tags (`[FIRE]`, `[ZAP]`, `[WALL]`, `[BOOM]`, etc.)
- Character `emoji` fields replaced with ASCII tags (e.g., `[SHARK]`, `[CROC]`, `[TOILET]`, etc.)

### Fixed — Category B: Image Download System

- Replaced primary image source: now uses `ui-avatars.com` API which generates colored text avatars with character name and their hue-derived background color
- Fallback chain: `ui-avatars.com` → `robohash.org?set=set1` (robots) → generated fallback icon
- Changed robohash set from `set=set4` (cats) to `set=set1` (robots) for better visual quality

### Fixed — Category C: Ball Rendering

- Added `draw = ImageDraw.Draw(img)` refresh after every `img.paste()` call to ensure subsequent draw operations work correctly
- Ball outline and name label are now always drawn on top of the character image
- Resampling changed from `Image.NEAREST` to `Image.LANCZOS` everywhere for smoother images

### Fixed — Category D: Winner Screen Image Size

- Winner character image now resized to `big_r * 2` (diameter = 120px) instead of `big_r` (radius = 60px)
- Paste position updated to `cx_w - big_r` (correct center) instead of `cx_w - big_r // 2`

### Fixed — Category E: Performance / Determinism

- Render-time random effects (lava flicker, lava bubbles) now use a frame-seeded `random.Random(frame * 31337)` for deterministic, flicker-free output
- Screen shake offsets use a frame-seeded RNG (`random.Random(frame * 99991)`)

### Added — Category I: Image Quality

- `icon_size` increased from 64 to 96 pixels for sharper character images on balls
- `icon_size` parameter in `download_character_images` default updated to 96
- All image resizing uses `Image.LANCZOS` for highest quality

### Added — Category H: CI/CD & Documentation

- Added `.github/workflows/lint.yml` — GitHub Actions workflow that runs pyflakes syntax check on `CODE`
- Added `README.md` — Project description, Colab usage instructions, configuration options, and character list
- Added `CHANGELOG.md` — This file
