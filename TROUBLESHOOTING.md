# Troubleshooting

## A mission/scene cannot be completed in VR

Some Cyberpunk scenes or interactions do not translate perfectly through a VR port. Symptoms can include gaze-dependent actions not registering, UI elements being inaccessible, scripted camera behavior breaking, or a mission step refusing to progress.

Use the Companion's **Flatscreen** switcher as a temporary recovery mode:

1. Save your game.
2. Fully exit Cyberpunk.
3. Switch to **Flatscreen** in the Companion.
4. Relaunch and complete the blocked section.
5. Save and exit again.
6. Switch back to **VR** and continue.

Do not toggle modes while the game is running.

## Launch VR flashes a window but Cyberpunk does not start

1. Run **Health**.
2. Run `CyberpunkVRCompanion\Tools\Repair Smart Launch.bat`.
3. Try **Launch VR** again.
4. If it still fails, review `CyberpunkVRCompanion\Logs\App\SmartLaunchLast.log` and create a Diagnostic Pack.

The public build also performs launch-readiness self-repair during setup, app startup, and immediately before launching a profile.

## Stereo intro does not appear

The stereo intro is used only when the HMD/OpenXR path initializes successfully. If it cannot initialize, the application uses the desktop startup presentation instead of blocking launch.

Check that the headset is awake/connected, the intended OpenXR runtime is active, and PCVR streaming software is connected if your setup requires it.

## Only Current Settings is visible

Allow Automatic Setup to finish. The public build should generate local protected reference profiles after capturing the baseline.

## Controls show Advanced Raw

This is intentional when the Companion cannot safely infer a bounded control. The app prefers an honest raw value over guessing setting semantics.

## Diagnostic support

Use **Diagnostics → Create Diagnostic Pack** and review the archive before posting it publicly.
