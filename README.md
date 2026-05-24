# App 016 — Chug Roulette

**Category:** G · Games and Interactive  
**Live:** https://augustineiacopelli.github.io/appaday-016-chug-roulette

## What It Does

Chug Roulette is a spin-the-wheel party drinking game built for the phone in your pocket, inspired by the Beer Mile. Spin the wheel and get a random challenge matched to the segment the pointer lands on — chugs, waterfalls, rule-making, swaps, or a full DNF penalty. Add your group as Runners and the wheel cycles through players automatically, addressing each challenge by name.

## How to Use

1. Tap **+ Add Runner** to add everyone playing. The wheel won't spin until at least one runner is in.
2. Tap **SPIN** and wait for the wheel to land.
3. The challenge card reveals who's up and what they have to do.
4. Tap **📋 Rules** to see house rules and any session rules that have accumulated from RULE spins.
5. Tap **🏁 Log** to review every spin in the session.
6. Tap **End Session & Clear Rules** in the Rules modal when the game is over to wipe session rules.

## Technical Notes

- Vanilla HTML, CSS, and JavaScript — no frameworks, no dependencies beyond Google Fonts.
- Layout uses a flex column with `height: 100%; overflow: hidden` so the app fills the device viewport exactly with nothing falling off screen.
- Wheel canvas is dynamically sized on load and resize to fit available space, capped between 180px and 300px.
- Spin animation uses `requestAnimationFrame` with a quartic ease-out curve for natural deceleration.
- Segment detection uses pointer-relative angle math (`-π/2` offset) so the correct segment pool is always matched to what the pointer lands on.
- RULE spins automatically append the challenge text to the session rules log with player name and round number.
- All inputs use `font-size: 16px` to prevent iOS Safari viewport zoom on focus.
- `viewport-fit=cover` and `env(safe-area-inset-bottom)` handle iPhone notch/home indicator spacing.

## Definition of Complete

- [x] Wheel spins and decelerates naturally
- [x] Segment detection matches pointer to correct challenge pool
- [x] Player names cycle in order with active turn highlighted
- [x] Game locked until at least one runner is added
- [x] Rules modal with permanent house rules and live session rules
- [x] RULE spins automatically logged to session rules
- [x] Race Log modal tracks all spins
- [x] Session rules clearable at end of game
- [x] Viewport fills device with no scroll or overflow
- [x] No iOS zoom on text input
- [x] Mobile-friendly at 375px viewport
- [x] Published to GitHub Pages
