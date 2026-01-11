# Inkline — Act 1 Level Graph

## Locations (6-10)
- L01_StreetFront_SignAndDoor
- L02_WaitingRoom_FlashWall
- L03_FrontDesk_CheckIn
- L04_PrepStation_SterileSetup
- L05_BoothA_TheChair
- L06_AftercareCounter_ShiftEnd

## Anchor Registry (minimum)
- A_SPAWN_START
- A_CLIENT_01_READY
- A_CLIENT_02_READY
- A_CLIENT_03_READY
- A_EXIT_L01_TO_L02
- A_EXIT_L02_TO_L03
- A_EXIT_L03_TO_L04
- A_EXIT_L04_TO_L05
- A_EXIT_L05_TO_L06
- A_SLICE_END

## Topology (Mermaid)
```mermaid
graph TD
  L01-->L02
  L02-->L03
  L03-->L04
  L04-->L05
  L05-->L06
