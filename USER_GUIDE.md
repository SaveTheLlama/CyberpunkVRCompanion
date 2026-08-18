# Cyberpunk VR Companion — User Guide

This guide explains the major functions of Cyberpunk VR Companion, what each one is intended for, and when to use it.

---

## Before you begin: tested VR port

Cyberpunk VR Companion does not include or install a Cyberpunk VR port.

Version 1.1.0 was developed and validated primarily with the **iPowerTech CyberpunkVR Port**:

**[iPowerTech/cyberpunk-vr-port](https://github.com/iPowerTech/cyberpunk-vr-port)**

That repository is a fork of the upstream **[dariulone/cyberpunk-vr-port](https://github.com/dariulone/cyberpunk-vr-port)** project.

Before installing the Companion:

1. Follow the VR port project's current README and dependency requirements.
2. Install the VR port and its required dependencies.
3. Verify that Cyberpunk launches correctly in VR.
4. Then install Cyberpunk VR Companion.

Other compatible Cyberpunk VR configurations may work, but the iPowerTech port is the primary environment used to validate Companion v1.1.0.

---

## 1. Automatic Setup

### What it does

Automatic Setup prepares the Companion around the user's existing Cyberpunk VR installation.

On first launch it can detect or configure:

- Cyberpunk 2077 installation location
- GPU and approximate hardware class
- CPU and system memory
- connected HMD/headset
- active OpenXR runtime
- estimated headset refresh target
- Cyber Engine Tweaks
- RED4ext
- Cyberpunk VR port state
- Smart Launch readiness

It also captures the user's current Cyberpunk graphics configuration as:

**Current Settings (Auto-Detected)**

and generates protected local reference profiles:

- **Performance**
- **Balanced**
- **Ray Tracing**
- **Clarity**

### When to use it

Normally, no manual action is required. Review the Automatic Setup status after installation or after making major changes to the VR/mod environment.

A **READY** state means the Companion has found the expected components and is prepared to use its normal features.

If Automatic Setup reports **ACTION NEEDED**, follow the item shown rather than reinstalling everything immediately.

---

## 2. Launch VR / Smart Launch

### What it does

Smart Launch prepares the selected Companion profile and launches Cyberpunk through the configured VR workflow.

Before launching, the Companion checks its launch-readiness components and can attempt to repair missing Smart Launch/bootstrap pieces automatically.

### Normal workflow

1. Choose the profile you want to use.
2. Make sure Cyberpunk 2077 is not already running.
3. Select **Launch VR**.
4. Allow the Companion to prepare the profile and start Cyberpunk.

### If the game does not launch

Run **Health** first.

If needed, run:

`CyberpunkVRCompanion\Tools\Repair Smart Launch.bat`

Then try **Launch VR** again.

The most recent Smart Launch log is stored under:

`CyberpunkVRCompanion\Logs\App\SmartLaunchLast.log`

---

## 3. Graphics Profiles

Profiles let the Companion store and apply different Cyberpunk graphics configurations.

### Current Settings (Auto-Detected)

This is the protected baseline captured from the user's existing Cyberpunk configuration during first-run setup.

Use it as a reference for the settings that were present when the Companion was installed.

### Performance

A locally generated protected reference intended to favor performance and reduce expensive effects.

### Balanced

A locally generated protected reference intended to balance image quality and performance.

### Ray Tracing

A locally generated protected reference intended for users who want ray-traced effects enabled while retaining a controlled VR-oriented configuration.

### Clarity

A locally generated protected reference intended to favor image clarity and reduce effects that can make the VR image look softer or less clean.

### Important: protected profiles

Built-in/reference profiles are protected.

The Companion intentionally avoids editing them directly so users always retain known reference points.

If you want to modify one:

1. Open/view the profile.
2. **Duplicate** it.
3. Edit the new **Custom** profile.
4. Save the Custom profile.
5. Use that Custom profile for launching/tuning.

---

## 4. Native Profile Editor

### What it does

The Profile Editor exposes Cyberpunk settings in a safer, friendlier interface.

Depending on the setting, the editor may use:

- toggles
- labeled sliders
- selectors/drop-downs
- numeric range sliders
- **Advanced Raw** values

### Why Advanced Raw sometimes appears

Cyberpunk settings can change between game versions, and some values do not expose a safe list or numeric range.

When the Companion cannot confidently determine a safe user-friendly control, it leaves the value as **Advanced Raw** instead of guessing.

That behavior is intentional.

### Recommended use

For most users:

- edit duplicated Custom profiles;
- change only settings you understand;
- keep the protected reference profiles intact.

---

## 5. Custom Profiles

Custom profiles are the user's editable configurations.

They are useful for situations such as:

- a personal 90 Hz configuration;
- a high-quality SSW/reprojection configuration;
- a profile tuned for a specific mission/location;
- testing one or two graphics changes without losing a known-good setup.

The Companion tracks profile identity and modification state so saved Custom profiles remain separate from protected originals.

---

## 6. Community Profiles

### What it does

Community Profile tools allow profiles to be exported and imported with useful metadata.

A shared profile can include information such as:

- author
- hardware
- headset
- OpenXR/runtime context
- profile purpose
- other compatibility metadata

### Before using a Community profile

Treat it as a starting point rather than a guarantee.

A profile created for different hardware, headset resolution, runtime, or refresh target may perform very differently on another PC.

Use the Companion's compatibility information to help judge whether the profile is a reasonable match.

### Best practice

Import → inspect → duplicate/customize if necessary → test.

---

## 7. Hardware & Compatibility

### What it does

The Hardware section describes the system the Companion is optimizing around.

Automatic detection can populate information such as:

- GPU
- CPU
- RAM
- headset
- OpenXR runtime
- refresh target / display information where available

Compatibility logic can use profile metadata and hardware information to estimate how closely a profile matches the current system.

### Manual Hardware Profiles

If a user deliberately saves a manual Hardware profile, the Companion preserves that explicit choice rather than continually replacing it with automatic detection.

Use manual values when automatic detection cannot accurately describe a specialized setup.

---

## 8. Assisted Tuning

### What it does

Assisted Tuning helps create a more appropriate Custom profile based on:

- the selected source profile;
- current hardware/profile metadata;
- compatibility information;
- known tuning rules.

### Important behavior

Assisted Tuning does **not** silently overwrite protected profiles.

Its purpose is to create or recommend an editable Custom result while keeping known originals available for recovery/comparison.

### Good workflow

1. Choose the profile closest to your goal.
2. Run Assisted Tuning.
3. Review the proposed/resulting Custom profile.
4. Test it in game.
5. Keep, edit, or discard it based on actual VR performance.

---

## 9. VR / Flatscreen Switcher

### Why this feature exists

Some Cyberpunk 2077 scenes or mission interactions may not function correctly through a VR port.

Examples can include sequences that depend on:

- gaze direction;
- 2D interface interaction;
- scripted camera positioning;
- unusual cinematic behavior;
- mission interactions that do not translate correctly into VR.

The Flatscreen switcher gives users a recovery path without manually removing or reinstalling the VR port.

### Correct recovery workflow

1. **Save your game** before the affected scene or mission step.
2. **Fully exit Cyberpunk 2077.**
3. Open Cyberpunk VR Companion.
4. Switch the game to **Flatscreen** mode.
5. Launch Cyberpunk.
6. Complete the scene, interaction, or mission step that was preventing progress.
7. **Save again.**
8. **Fully exit Cyberpunk.**
9. Switch the Companion back to **VR** mode.
10. Relaunch and continue playing in VR.

### Important

**Do not switch between VR and Flatscreen while Cyberpunk is running.**

The game should be completely closed before changing modes.

---

## 10. Health Check

### What it does

Health Check is the first troubleshooting tool to use when something is not working.

It checks expected Companion and VR/mod components and reports results using statuses such as:

- PASS
- WARN
- FAIL
- INFO

### When to run it

Use Health Check when:

- Cyberpunk will not launch;
- the VR port appears inactive;
- a required component may be missing;
- profiles behave unexpectedly;
- the Companion was moved/upgraded;
- the VR/mod environment was recently changed.

Start here before deleting files or reinstalling components.

---

## 11. Diagnostic Pack

### What it does

Diagnostic Pack creates a support archive containing information useful for diagnosing Companion problems.

It is designed to sanitize environment-specific information and avoid user-content categories that are not needed for support.

### Intended exclusions/sanitation include

- Cyberpunk save files
- screenshots
- Cyberpunk `UserSettings.json`
- crash dumps
- Steam IDs
- IP addresses
- user-directory information where sanitation rules apply

### Before sharing

Even though the tool is designed around privacy-safe diagnostics, users should always review an archive before uploading it publicly.

Use a Diagnostic Pack when Health Check alone does not explain the problem.

---

## 12. Stereo Startup Intro

### What it does

When the HMD/OpenXR path is available, Cyberpunk VR Companion can present its startup branding stereoscopically inside the headset.

If stereo startup cannot initialize, the Companion falls back to the desktop startup presentation rather than blocking the application.

### Available startup preferences

The Companion can expose startup options such as:

- stereo intro enabled/disabled;
- depth level;
- intro duration.

The startup intro is visual only. Disabling it does not disable the VR launch system.

---

## 13. Export / Import

### Export

Use export when you want to:

- back up a profile;
- move a profile to another installation;
- share an appropriate profile with another user.

### Import

Use import to add a compatible profile package to the Companion.

After import, review its metadata and compatibility before treating it as a recommended configuration for your hardware.

---

## 14. Recommended First-Time Workflow

For a new user:

1. Install the VR port and its dependencies using the VR port project's own instructions.
2. Verify that Cyberpunk launches correctly in VR before adding the Companion.
3. Install Cyberpunk VR Companion.
4. Allow Automatic Setup to finish.
5. Confirm the setup status is **READY** or resolve any reported item.
6. Review **Current Settings (Auto-Detected)**.
7. Review the four generated protected reference profiles.
8. Start with **Balanced** unless you already know you want a different goal.
9. Use **Launch VR**.
10. If performance or image quality needs adjustment, duplicate the closest reference into a Custom profile.
11. Use Assisted Tuning or edit the Custom profile.
12. Run Health before performing manual repairs if something stops working.

---

## 15. Uninstall / Full Reset

Cyberpunk VR Companion includes two ways to remove/reset Companion-managed components:

- **Normal uninstall** removes the Companion while preserving the intended user data/state.
- **FULL RESET** clears Companion-managed state so a later installation behaves like a fresh Companion setup.

Neither option removes Cyberpunk 2077, Cyber Engine Tweaks, RED4ext, the VR port, Virtual Desktop, or the user's OpenXR runtime.

Use **FULL RESET** only when you deliberately want a fresh Companion state.

---

## 16. General Safety Rules

- Fully exit Cyberpunk before switching between VR and Flatscreen.
- Keep protected profiles as reference points.
- Duplicate a profile before experimenting heavily.
- Run Health before deleting/reinstalling files.
- Review Diagnostic Packs before posting them publicly.
- Remember that Community profiles may target different hardware/headsets.
- Avoid manually moving VR-port files when the Companion can manage the state for you.

---

## Getting Help

If a problem persists:

1. Run **Health**.
2. Create a **Diagnostic Pack**.
3. Note the Companion version, Cyberpunk version, GPU, headset, OpenXR runtime, and steps needed to reproduce the issue.
4. Submit those details through the project's GitHub support/issue workflow.

Do not upload saves, credentials, private screenshots, or unrelated personal files.
