# Inkline — Playtest Script (10–15 min)

## Setup
Start at L01 with Tattoos Completed at 0/3 and Pain meter at 0.
Ensure three clients can be completed in sequence and the chair interaction is enabled when a client is ready.

## Step-by-step Run
1. Enter the shop (L01→L02→L03), confirm Client #1 is ready, and sit them in the chair (L05).
2. Place stencil, perform linework trace, do one shading pass, use wipe/cool once, then finish aftercare.
3. Confirm Tattoos Completed updates to 1/3 and Client #2 becomes available.
4. Complete Client #2 and confirm pain spikes occur on mistakes; verify you can recover using wipe/cool.
5. Complete Client #3 and confirm the slice ends only after aftercare + Tattoos Completed reaches 3/3 at L06.

## Expected Outcomes
- Player can complete 3 tattoos in 10–15 minutes with readable tension from the Pain meter.
- The same interaction loop repeats cleanly with slightly increased difficulty each client.
- Failure is clear and immediate when Pain maxes (client stops session).

## Bug Buckets
- Blocker (can’t finish slice)
- Major (loop breaks / meter incorrect / progress not updating)
- Minor (UI/text/audio feedback)
