# AFTERSHIFT implementation plan

## Phase 1 — Offline vertical slice
- Generate the test arena and verify the Unity project compiles.
- Test player movement, jump, dash, camera, projectiles, target health, and echo playback.
- Fix all console errors and ensure the game can restart cleanly.

## Phase 2 — Mobile controls and polish
- Add an on-screen movement stick and touch buttons for jump, dash, fire, and echo.
- Add readable HUD scaling for phone and desktop aspect ratios.
- Replace primitive geometry with original low-cost art and effects.
- Add audio, impact feedback, and a clear tutorial.

## Phase 3 — Cross-platform test builds
- Build Web and Android targets separately.
- Test browser compatibility, frame rate, input, memory, and Android device performance.
- Do not advertise either build as playable until smoke tests pass.

## Phase 4 — Multiplayer spike
- Test Unity Netcode for GameObjects and a compatible transport with two clients.
- Verify browser-to-browser and browser-to-Android connectivity before choosing the final architecture.
- Decide between relay and dedicated server after validating costs and deployment needs.
- Keep the existing GameHub frontend and server untouched until this phase is successful.

## Current status
This repository is a starter scaffold. The Unity editor has not yet compiled or run the project, and multiplayer/mobile touch controls are not implemented.
