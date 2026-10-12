# AFTERSHIFT — GameHub Unity Prototype

A full-3D Unity starter project for a cross-platform arena game. This repository is intentionally separate from the existing React GameHub and Node.js server, so the live website and existing games remain untouched.

## Prototype scope

- Third-person movement with keyboard/mouse (mobile touch controls are a follow-up task)
- A generated sci-fi test arena
- Energy projectile combat and health
- Echo mechanic: the player's recorded movement is replayed as a translucent ghost after a delay
- HUD for health, echo status, and controls
- Editor bootstrap script that generates the first playable scene
- Web and Android build guidance

This is a **prototype foundation**, not a finished online multiplayer game. Networked matches, matchmaking, anti-cheat, production art/audio, and real-device performance tests are future milestones.

## Recommended editor

Use a current **Unity 6 LTS** editor with:
- Universal Render Pipeline (URP)
- Android Build Support (Android SDK & NDK Tools and OpenJDK)
- Web Build Support

The project uses Unity's built-in input APIs for a simple first prototype. In **Project Settings → Player → Active Input Handling**, choose **Both** or **Input Manager (Old)** if prompted.

## Open the project

1. Extract the project folder.
2. Open Unity Hub.
3. Choose **Add → Add project from disk** and select this folder.
4. Let Unity resolve packages and compile scripts.
5. On first import, use **Tools → AFTERSHIFT → Generate Prototype Scene**.
6. Press Play.

The scene generator is an Editor utility at `Assets/Editor/AftershiftBootstrap.cs`. It creates a simple arena, lights, a player, a follow camera, targets, and a HUD so you can test the mechanics without importing paid assets.

## Controls

### Desktop
- WASD: move
- Mouse: aim camera
- Space: jump
- Left Shift: dash
- Left mouse button: fire energy bolt
- E: trigger/replay echo preview

### Android (current scaffold)

The project can be configured and built for Android, but the on-screen touch-control layer is **not implemented yet**. It is an explicit next task before calling the mobile prototype playable.

## Cross-platform multiplayer plan

1. Get the offline prototype playable.
2. Build Web and Android test builds and measure performance.
3. Prototype Unity Netcode for GameObjects + Unity Transport on both targets.
4. Test browser ↔ Android connection compatibility with a minimal two-client scene.
5. Choose a dedicated-server/relay deployment based on test results and cost.
6. Add a GameHub launch entry only after the prototype passes smoke tests.

The existing GameHub server is Socket.IO-based and currently handles board-game room state. Do not bolt high-frequency 3D movement directly onto that code before validating a transport.

## Known prototype limitations

- Echoes are visual recordings of player positions, not authoritative damage copies.
- Target dummies are local practice targets.
- No real multiplayer is included yet.
- Placeholder materials and primitive geometry are intentional.
- Do not ship this as a finished product without security, device, browser, and networking tests.
