# Inkline - Tattoo Artist Prototype

A 10-15 minute vertical slice prototype demonstrating the core "needle feel" and pain tension mechanics of a tattoo artist precision game.

## What This Prototype Proves

1. **Needle Feel**: The path-following mechanic creates tactile tension through tolerance zones that require steady cursor control
2. **Pain as Pressure**: The single Pain meter creates meaningful pacing decisions - push through or wipe/cool
3. **Difficulty Scaling**: Three clients with increasing path complexity, tighter tolerances, and faster pain rates
4. **Client Personality**: Dialogue and barks give each client distinct reactions to pain thresholds and mistakes
5. **Session Arc**: A complete shift from entry to 3 completed tattoos provides a satisfying loop

## How to Run

**Option 1: Direct browser open**
```bash
# Open in default browser
xdg-open index.html          # Linux
open index.html              # macOS
start index.html             # Windows
```

**Option 2: Local server (if needed)**
```bash
python3 -m http.server 8000
# Then open http://localhost:8000 in browser
```

**Option 3: Just double-click `index.html` in your file manager**

The game loads instantly with zero dependencies.

## Controls

| Action | Control |
|--------|---------|
| Move stencil | Click and drag |
| Confirm stencil | Press **SPACE** |
| Activate needle | Hold **mouse button** |
| Trace path | Move cursor along the blue target circle |
| Wipe/Cool | Click **Wipe/Cool** button or press **W** |
| Advance dialogue | Click dialogue box |

## Gameplay Loop

1. **Street Front** - Enter the shop
2. **Waiting Room** - See your next client
3. **Front Desk** - Check in and view difficulty
4. **Prep Station** - Equipment ready
5. **The Chair** - Main tattoo gameplay:
   - **Stencil**: Position the ghost outline, press SPACE to confirm
   - **Linework**: Hold mouse and trace the outline within tolerance
   - **Shading**: Same mechanic with wider tolerance, slower progress
6. **Aftercare** - Complete the tattoo, increment counter
7. Repeat for 3 clients, then **Shift Complete**

## Pain System

- Pain increases continuously while needle is active
- **Mistakes** (cursor outside tolerance while needle on) cause pain spikes + red flash
- **Hesitation** (not moving while needle active) increases pain rate
- **Wipe/Cool**: Reduces pain by 15, has 6-second cooldown
- At **Pain 100**: Client taps out = fail
- Barks trigger at 25%, 50%, 75% pain thresholds

## Difficulty Progression

| Client | Difficulty | Tolerance | Pain Rate | Mistake Penalty |
|--------|------------|-----------|-----------|-----------------|
| Casey  | Easy       | 25px      | 3/sec     | +8              |
| Miguel | Medium     | 20px      | 5/sec     | +12             |
| Lila   | Hard       | 15px      | 7/sec     | +15             |

## Debug Controls (bottom-right)

- **Reset Tattoo**: Restart current tattoo with pain at 0
- **Reset Shift**: Return to title, reset all progress
- **Quick Run**: Skip navigation, jump straight to chair for each client

## Known Limitations

- No audio (placeholder system not implemented)
- Simplified path designs (geometric shapes vs. realistic tattoo art)
- Stencil placement has no fail state (any position accepted)
- No save/load system
- Single session only (browser refresh resets)
- Wipe cooldown timer not displayed numerically
- No touch/mobile support

## Tech Stack

- **Engine**: Vanilla HTML5 Canvas + JavaScript
- **Why Web**: Zero installation, single-file, runs in any browser
- **Lines of code**: ~700 (single self-contained file)

## File Structure

```
inkline/
├── index.html           # Complete runnable game
├── README.md            # This file
├── SLICE_SPEC.md        # Design specification
├── DIALOGUE.yml         # Source dialogue data
├── ASSET_MANIFEST.yml   # Asset requirements
└── ... (other pitch docs)
```

## Acceptance Criteria Met

- [x] Runs in under 2 minutes (instant browser open)
- [x] 3 tattoos completable in 10-15 minutes
- [x] Pain meter matches spec (continuous + spikes + thresholds)
- [x] Tattoos Completed counter works (0/3 → 3/3)
- [x] No extra systems (economy, crafting, etc.)
- [x] 6 locations implemented as screens
- [x] Dialogue from DIALOGUE.yml integrated
- [x] Barks trigger at pain thresholds
- [x] Debug controls for playtesting
