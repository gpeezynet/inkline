# Inkline — Slice Spec (Vertical Slice Contract)

## Slice Goal
Complete three walk-in tattoos in a single shift, proving the tattooing interaction loop and the pain-pressure system end-to-end.

## Start / End
- Start: You unlock the shop, step into the booth, and the first client is ready in the chair.
- End: The third tattoo is finished, aftercare is applied, and the “Shift Complete” prompt triggers at the counter.

## Objectives (Player-facing)
- Complete Tattoo #1 (easy): stencil → linework → quick shade → aftercare.
- Complete Tattoo #2 (medium): slightly tighter linework, higher pain sensitivity.
- Complete Tattoo #3 (hard): longest trace path + higher mistake penalty.
- Finish all three before any client’s pain meter maxes out.

## Pressure System (one)
**Client Pain Meter**
- Pain rises while the needle is active (linework/shading).
- Pain spikes when you deviate off-stencil or pause too long mid-stroke.
- Pain can be reduced slightly by using the wipe/cool interaction (limited relief, not a full reset).
- If pain maxes: client taps out → tattoo fails → slice fails.

## Progress Metric (one)
**Tattoos Completed (0/3 → 3/3)**

## Fail States
- Client Pain Meter maxes out on any tattoo (client stops the session).
- Player abandons the chair mid-tattoo (walks away / cancels) → counts as fail for the slice.

## In / Out of Scope
### In
- One shop interior with 6 linked areas (front, desk, prep, two booths, aftercare/exit).
- Three tattoo “jobs,” each using the same 3–5 interaction types:
  - Stencil placement (align/confirm)
  - Linework trace (precision follow)
  - Shading/fill pass (broader follow)
  - Wipe/cool (pain relief)
  - Finish/aftercare (commit completion)
- Minimal HUD: Pain meter + Tattoos Completed.

### Out
- Economy, vendors, skill trees, crafting systems
- Open world streaming
- Multiplayer
