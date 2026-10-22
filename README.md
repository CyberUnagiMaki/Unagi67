# UNAGI 67 · v0.5

Android controller and Windows bridge: Wi-Fi control + Bluetooth HID, without a USB connection. This distribution contains the APK, Windows executable with its runtime, instructions and screenshots.

[Русская инструкция](README_RU.md)

## Download

- [Android APK · v0.5](downloads/Unagi67-v0.5.apk)
- [Windows x64 · v0.5 ZIP](downloads/Unagi67-Windows-v0.5.zip)
- [SHA-256](SHA256SUMS.txt)


## Install and connect

1. Install **Unagi67-v0.5.apk** on Android 9 or newer. This is a debug-signed build; its signing certificate matches the supplied v0.4 APK, so install it as an update to preserve app data.
2. Download and extract the entire Windows ZIP. Run **Unagi67_WiFi_Bridge/Unagi67_WiFi_Bridge.exe** on Windows x64. Keep `_internal` alongside the executable. Python is not required.
3. Connect phone and PC to the same local network. The PC may use Ethernet. Open the Android app and grant its Bluetooth permissions.
4. Keep the existing Bluetooth pairing with the PC, or pair once in Windows Bluetooth settings while the app is running.
5. Enter the phone's Wi-Fi IP and six-digit code in the Windows bridge, then select **CONNECT / WIFI**.
6. Select **CALIBRATE MOUSE**, then click your physical mouse's left button. Choose and configure a preset on the phone before enabling a mode.

## Your presets

Open **STROKE → presets** or **TAP → presets**. Tap a preset to select it, **Create** to add one, **Edit** to change its name/image/value, or **Delete** to remove it after confirmation.

The 19 initial presets are named after the supplied image files: ACE32, AKM, AUG, BERYL M762, FAMAS, G36C, GROZA, JS9, K2, M416, MICRO UZI, MP5K, MP9, P90, QBZ, SCAR-L, THOMPSON, UMP and VECTOR. Their initial sensitivity is 100 and tapping rate is 5 clicks/s; these are starting values, not weapon-specific tuning. Set your own values.

Names and images are shared between modes. Each preset stores its own **STROKE sensitivity (1–500)** and **TAP rate (1–20 clicks/s)**. The two modes may select different presets. Sensitivity controls the assistant's movement amount; it does not change the game's sensitivity setting.

Values changed on a mode screen save automatically. Changes made in the editor require **Save**. Selected presets, names, images and values survive application restarts and phone reboots. Imported pictures are copied into private app storage, so the original gallery file is no longer required. Deleted defaults stay deleted, including when the entire library is empty. Previously saved v0.4 values migrate to separate **Saved N** entries.

Uninstalling the app or clearing its data removes local presets. Install updates over the existing app.

## Emergency STOP

In the Windows bridge, click **STOP KEY: F8**, then press your preferred keyboard key. The assignment is saved in `bridge_config.json` beside the executable. Keep the folder writable and preserve this file when updating Windows builds.

The binding accepts one key, including function keys, letters, digits or Escape. Ctrl, Alt, Shift and Windows alone are excluded; combinations and mouse buttons are not supported. The key is also delivered normally to other applications. It works while the bridge's input listener is running after connection, including when the bridge is in the background. Middle mouse no longer triggers STOP.

STOP disables modes and hides the magnifier. The phone also has an on-screen STOP button. Modes remain off after a lost connection until you enable them again.

## Magnifier and background operation

The magnifier starts at the main monitor's center. Use **CENTER ON GAME MONITOR**, then click the desired monitor to center it there. This targets the monitor center, so fullscreen/borderless gameplay is the intended layout.

The Android connection runs in a foreground service. Normal minimization should keep it running; **DISCONNECT** or Android force-stop ends it. After a phone reboot, open the app again to start the connection; presets are retained. Manufacturer battery restrictions and physical Bluetooth HID behavior still require testing on your phone.

If Wi-Fi fails, check IP, code, shared network and router client isolation. The phone listens on TCP 5005. Use a trusted local network; the connection is not encrypted. No USB debugging or ADB is needed for normal use.

## Screenshots

Actual v0.5 Android emulator screenshots, Russian UI. One default was deleted during persistence testing; a fresh installation includes all 19.

<img src="screenshots/presets.png" width="320" alt="Preset library"> <img src="screenshots/editor.png" width="320" alt="Preset editor">

## Validation

2026-10-22: APK build and Android lint passed (0 errors, 28 warnings). Android instrumentation verified creation, renaming, per-mode values, selection, removal of all defaults, legacy migration and imported images. Persistence was verified after process stop and emulator reboot. Eight Python tests passed, covering key persistence/repeats, native Raw Input dispatch, removal of middle-click STOP, transport reconnects and native magnifier positioning. The packaged EXE started successfully.

Physical-phone Bluetooth HID, game-specific behavior and actual keyboard STOP during gameplay were not tested in this run.
