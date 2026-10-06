# Setup and troubleshooting

[Home](../README.md) · [Русский](SETUP.ru.md)

## Install and connect

1. Download the APK and Windows ZIP from the main page. Install the APK on an Android 9+ phone that supports the Bluetooth HID Device profile. This version is a debug build. Updating an existing installation requires the same signing key; keep a record of your presets before considering an uninstall.
2. Connect both devices to the same reachable LAN. The phone uses Wi-Fi; the PC may use Wi-Fi or Ethernet. Guest networks and client isolation may prevent communication.
3. Open Unagi on the phone and allow Bluetooth permissions. Allow notifications to access the service's notification controls. The app displays one or more IPv4 addresses and a pairing code; choose its reachable Wi-Fi address.
4. Extract the complete Windows package. Start `Unagi67_WiFi_Bridge.exe`; do not separate it from `_internal`.
5. Enter the phone IP and pairing code. Select **CONNECT / WIFI**. Normal use does not need USB debugging, ADB or a cable.
6. Pair the phone and PC through Bluetooth settings while the app is open. A previously working pairing can be reused. Registration/connection and pairing are different states; an interrupted connection does not automatically mean you need to delete the pairing.
7. Select **CALIBRATE MOUSE** and click the physical mouse's left button. Calibration identifies which Raw Input device should control the modes.

## Controls

Tap a mode card to toggle it. Tap its title to edit settings. Stroke controls vertical movement; tapping controls repeated clicks. Save a preset after changing its value. Use the gear icon to change the language.

**STOP** on the phone or the physical middle mouse button disables all modes. **DISCONNECT** stops the Android service; **START LINK** starts it again. Reconnection keeps the modes off until you enable them.

## Magnifier

The default center is the primary monitor's full bounds, not its work area or the combined desktop. For another monitor, select **CENTER ON GAME MONITOR** on the PC and click anywhere on that monitor. The phone's magnifier settings provide the same monitor-selection action and reset manual X/Y offsets.

Old X/Y offsets are reset once when migrating to 0.4. Manual offsets can subsequently move the magnifier away from center. Zoom, size and refresh rate are adjustable. The requested refresh rate is a scheduling setting, not a guarantee of achieved FPS.

The center is the monitor center, not the center of a small game window. Use borderless fullscreen for initial testing; exclusive fullscreen behavior depends on the application.

## Background operation

The foreground service owns the connection and input loop. Minimizing or finishing the activity should not stop it. Android force-stop does stop it, and device-specific battery restrictions may affect background or screen-off operation. Physical-device testing is still required.

If the service is unexpectedly stopped, inspect the phone's background/battery settings for Unagi and test again. Reopen the app and use **START LINK** when needed. The app attempts to reconnect to the last successfully connected, still-bonded Bluetooth host.

## Troubleshooting

| Symptom | Check |
|---|---|
| Wi-Fi never connects | Phone app/service running, correct IP and code, same reachable LAN, no guest/client isolation |
| Wrong code | Use the current six digits shown on the phone, not a screenshot's example |
| Wi-Fi works, no mouse action | Bluetooth HID connected, physical mouse calibrated, desired mode enabled |
| Modes turn off after a drop | Expected: enable them manually after recovery |
| Magnifier is on the wrong screen | Choose the game monitor and reset X/Y offsets |
| Magnifier is not centered in a windowed game | It targets monitor center, not game-window center |
| EXE cannot find files | Extract the full package including `_internal` |
| Android reports incompatible update | Check signing keys; uninstalling can remove presets |

TCP port 5005 is hosted by the phone. No firewall rules are changed automatically. Use this protocol only on a trusted local network.
