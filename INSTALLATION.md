# Installation

## Before installing the Companion

Cyberpunk VR Companion does not install or redistribute a Cyberpunk VR port.

Cyberpunk VR Companion v1.1.0 was developed and validated primarily with:

**[iPowerTech/cyberpunk-vr-port](https://github.com/iPowerTech/cyberpunk-vr-port)**

This is a fork of the upstream **[dariulone/cyberpunk-vr-port](https://github.com/dariulone/cyberpunk-vr-port)** project.

Follow the VR port project's **current** README, dependency list, and installation instructions. Install the VR port and its required dependencies first, then verify that Cyberpunk launches correctly in VR before installing the Companion.

The VR port is a separate third-party project and is not bundled with Cyberpunk VR Companion.

## Recommended public install

1. Download `CyberpunkVRCompanionSetup.exe`.
2. Close Cyberpunk 2077.
3. Run the installer.
4. Approve UAC if prompted.
5. Let setup detect the game and finish installation.
6. Launch the Companion from the desktop or Start Menu shortcut.

## Automatic setup

Setup finds Cyberpunk, installs/upgrades the Companion, creates the native launcher/shortcuts, installs the Smart Launch bridge, runs preflight and launch-readiness checks, then hands off to first launch.

First launch detects GPU/HMD/OpenXR, captures the user's current graphics baseline, generates protected reference profiles, and checks required VR/mod components.

## Upgrading

Run the latest setup EXE over the existing installation.

## Uninstall / Full Reset

Cyberpunk VR Companion includes two removal paths:

- **Normal uninstall** — removes the Companion while preserving the intended user data/state.
- **FULL RESET** — removes Companion-managed state so the next installation behaves like a completely fresh Companion setup.

The Companion removal tools do **not** remove Cyberpunk 2077, Cyber Engine Tweaks, RED4ext, the VR port, Virtual Desktop, or the user's OpenXR runtime.

Use **FULL RESET** only when you deliberately want to clear the Companion's managed state for troubleshooting, testing, or a fresh reinstall.

## Using the VR / Flatscreen switcher

The Flatscreen mode is primarily a compatibility/recovery feature. Some scripted scenes, gaze-based interactions, UI-heavy sequences, or mission steps may not behave correctly with the VR port active.

When a section cannot be completed in VR:

1. Save before the affected section.
2. Fully close Cyberpunk 2077.
3. Open Cyberpunk VR Companion and switch to **Flatscreen**.
4. Launch the game and complete the blocked section.
5. Save and fully close Cyberpunk again.
6. Switch the Companion back to **VR**.
7. Relaunch and continue in VR.

Always change modes while the game is closed. The Companion handles the VR-port state for you so users do not need to manually move or reinstall VR files.
