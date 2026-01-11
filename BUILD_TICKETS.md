
---

## `BUILD_TICKETS.md`

```md
# Inkline — Build Tickets (Ordered)

## T01 — Slice Skeleton
**DoD**
- Shop map exists with 6 locations and simple navigation start→end
- Player can move between areas and reach the tattoo chair
- “Client ready” state gates the chair interaction (no chair = no job)

## T02 — Interactions (3–5 max)
**DoD**
- Stencil Placement: align + confirm on a body zone (simple rotate/position)
- Linework Trace: follow a stencil path with error detection
- Shading/Fill: second pass with wider tolerance but longer exposure
- Wipe/Cool: short interaction that reduces pain slightly
- Finish/Aftercare: commits job completion and advances to next client

## T03 — Pressure System (one meter)
**DoD**
- Pain meter rises during needle-active states
- Pain spikes on trace errors and on long pauses mid-stroke
- Wipe/Cool reduces pain by a fixed amount with a brief cooldown
- Clear fail when pain hits max (client stops session, retry prompt)

## T04 — Progress Metric (one meter)
**DoD**
- Tattoos Completed increments on successful aftercare completion
- Gate next client spawn/availability off progress (0/3, 1/3, 2/3, 3/3)
- End condition triggers at 3/3 and activates A_SLICE_END

## T05 — Playtest Support
**DoD**
- Debug buttons: reset current tattoo / reset full shift
- Minimal HUD: Pain meter + Tattoos Completed + current client label
- Quick-run mode that skips walking and jumps to chair for rapid iteration
