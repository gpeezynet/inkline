# Inkline - Tattoo Artist Prototype

A 10-15 minute vertical slice prototype demonstrating the core "needle feel" and pain tension mechanics of a tattoo artist precision game.

## What Changed in v2

### Gameplay Overhaul
- **Real linework tracing**: Trace along the full stencil path segment-by-segment (no more chasing a moving circle)
- **Proper shading phase**: Fill inside the shape region with wider tolerance - different feel from linework
- **Distinct tattoo designs**: Heart (Casey), Star (Miguel), Rose (Lila) - each with unique paths

### Juice & Feedback
- **Screen shake** on mistakes
- **Ink smear effect** appears where you went off-path
- **Audio cues** via Web Audio API (mistake buzz, wipe swoosh, completion chime, phase-complete ding)
- **Wipe cooldown ring** with visual countdown timer
- **Needle indicator** pulses and buzzes when active
- **Pain bar pulses** when critical (75%+)
- **Skin reddens** as pain increases

### Polish
- **Redesigned title screen** with gradient logo and stats
- **Client cards** in waiting room showing avatar and difficulty badge
- **Aftercare preview** shows your completed tattoo
- **Shift complete gallery** displays all 3 tattoos with mistake count
- **Improved typography** and color scheme throughout

### Robustness
- **Auto-pause** when tab loses focus (Visibility API)
- **ESC to pause/resume** during gameplay
- **Window resize** handling
- **Proper delta-time** game loop (no more frame-rate dependent behavior)
- **Mistake cooldown** prevents pain spam
- **Mouse leave** properly deactivates needle

---

## 30-Second Demo Script

1. Click **Start Shift** on title screen
2. See Casey's client card → click through to **The Chair**
3. **Stencil phase**: Drag the heart outline, press SPACE
4. **Linework phase**: Hold mouse button, trace along the purple dashed path
   - Stay inside the blue tolerance band
   - Go outside = screen shake + ink smear + pain spike
5. **Shading phase**: Hold mouse inside the heart region until filled
6. Press **W** to wipe/cool and reduce pain (-18)
7. Complete → Aftercare screen shows your tattoo
8. Repeat for Miguel (star) and Lila (rose)
9. **Shift Complete** shows all 3 tattoos + total mistakes

---

## How to Run

```bash
# Any of these work:
xdg-open index.html          # Linux
open index.html              # macOS
start index.html             # Windows
# Or double-click index.html
```

Zero dependencies. Loads instantly.

## Controls

| Action | Control |
|--------|---------|
| Move stencil | Click and drag |
| Confirm stencil | **SPACE** |
| Activate needle | Hold **mouse button** |
| Trace linework | Move along the stencil path |
| Fill shading | Move inside the shape region |
| Wipe/Cool | **W** or click button |
| Pause/Resume | **ESC** |
| Advance dialogue | Click dialogue box |

## Gameplay Loop

1. **Title** → Start Shift
2. **Waiting Room** → See client card with difficulty
3. **Front Desk** → Check-in dialogue
4. **Prep Station** → Equipment ready
5. **The Chair** → Main gameplay:
   - **Stencil**: Drag to position, SPACE to confirm
   - **Linework**: Trace the path in order, stay in tolerance band
   - **Shading**: Fill inside the shape region
6. **Aftercare** → See completed tattoo, dialogue
7. Repeat for 3 clients → **Shift Complete**

## Pain System

| Mechanic | Effect |
|----------|--------|
| Needle active | +painRate/sec (varies by client) |
| Hesitation | +hesitationPenalty/sec after threshold |
| Mistake (off-path) | +mistakePenalty (instant spike) |
| Wipe/Cool | -18 pain, 6s cooldown |
| Pain ≥ 100 | Client taps out = fail |

Barks trigger at 25%, 50%, 75% pain thresholds.

## Difficulty Progression

| Client | Design | Line Tolerance | Shade Tolerance | Pain Rate | Mistake |
|--------|--------|----------------|-----------------|-----------|---------|
| Casey  | Heart  | 28px           | 45px            | 2.5/sec   | +6      |
| Miguel | Star   | 22px           | 38px            | 4/sec     | +10     |
| Lila   | Rose   | 16px           | 30px            | 6/sec     | +14     |

## Debug Controls

- **Reset Tattoo**: Restart current tattoo
- **Reset Shift**: Back to title, clear all progress
- **Quick: ON/OFF**: Skip navigation, jump straight to chair

## Tech Stack

- **Engine**: Vanilla HTML5 Canvas + JavaScript
- **Audio**: Web Audio API (procedural sounds, no files)
- **Size**: ~2100 lines, single self-contained file
- **Dependencies**: None

## What's NOT in v2 (Scope Discipline)

- No inventory/shop/economy
- No skill trees or progression
- No extra clients beyond 3
- No extra locations beyond 6
- No save/load
- No touch/mobile support

## Acceptance Criteria

- [x] Single pressure system: Pain meter (0-100)
- [x] Single progress metric: Tattoos Completed (0/3 → 3/3)
- [x] Same 3 clients with escalating difficulty
- [x] 6-location flow preserved
- [x] Quick Run + Reset Tattoo/Shift debug controls
- [x] Runs by opening index.html (no build tools)
- [x] Linework = trace polyline path in order
- [x] Shading = fill region with wider tolerance
- [x] Juice: shake, smear, sounds, cooldown visual
- [x] Robust: pause on tab-out, resize-safe, no stuck inputs
- [x] Polished: title screen, rewarding completion screens
