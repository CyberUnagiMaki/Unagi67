# UnagiSixSeven — Installation & Setup Guide


🇷🇺 [Читать на русском](INSTALL.ru.md)

---

## What you received

- **`UnagiSixSeven.apk`** — the Android app (install this on your phone)
- **A folder with the PC program** — containing `UnagiSixSeven_Bridge.exe`, `adb.exe` (and its supporting files), `pc_bridge_icon.ico`, `logo_small.png`

You do **not** need to install Python, Android Studio, or anything else. Everything required is already in the folder.

---

## Requirements

- An Android phone with Bluetooth (Android 9 or newer)
- A Windows PC with Bluetooth
- A USB cable to connect the two

---

## Step 1 — Install the app on your phone

1. Copy `UnagiSixSeven.apk` to your phone (via cable, cloud, messenger — any way you like).
2. Open the APK file on your phone to install it.
3. If you see a warning like *"Install blocked"* or *"Unknown sources"*, tap **Settings** in that prompt and allow installation from this source, then go back and install again. This warning is normal — it just means the app wasn't downloaded from the Play Store.

---

## Step 2 — Enable USB debugging on your phone

This lets the PC program talk to your phone over the USB cable.

1. Open **Settings → About phone**.
2. Find **Build number** and tap it **7 times in a row**. You'll see a message saying developer mode is now enabled.
3. Go back to **Settings**, open **Developer options** (it's now a new item in the menu, usually under System or at the bottom of Settings).
4. Turn on **USB debugging**.

---

## Step 3 — Connect the phone and allow the connection

1. Connect the phone to the PC with a USB cable.
2. A prompt will appear on the phone: **"Allow USB debugging?"** — tap **Allow** (you can also check "Always allow from this computer" so you don't see this every time).

---

## Step 4 — Pair the phone as a Bluetooth mouse

This step needs to be done carefully, or Windows won't create the mouse device correctly.

1. **Open the UnagiSixSeven app on your phone and leave it open on screen** (don't lock the phone or switch to another app). This is important — the phone needs to actively announce itself as a mouse.
2. Wait about 10 seconds.
3. On your PC: open **Settings → Bluetooth & devices → Add device**, find your phone in the list, and pair it.
4. Once paired, check the top of the app on your phone — it should say **"connected: [your phone's name]"**. If it still says "waiting for Bluetooth connection," something didn't register — see the troubleshooting note below.

**Every time you start a new session:** if the app doesn't automatically show "connected" within a few seconds of opening it, you may need to redo the pairing:
1. On the PC, go to **Settings → Bluetooth & devices**, find your phone in the list, and **remove/forget** it.
2. Open the app on the phone (keep it in the foreground).
3. Pair again from the PC's Bluetooth settings, as in step 3 above.

This is a known quirk — Windows only creates the virtual mouse device when it detects the phone announcing itself as one *at the exact moment of pairing*, so a fresh pairing is sometimes needed if the connection was lost.

---

## Step 5 — Run the PC program

1. Open the folder you received and double-click **`UnagiSixSeven_Bridge.exe`**.
   - If Windows shows a "protected your PC" / SmartScreen warning, click **More info → Run anyway**. This happens because the program isn't digitally signed, not because it's unsafe.
2. Click **CONNECT VIA USB**. The program automatically sets up the USB connection to your phone.
3. Click **CALIBRATE MOUSE**, then click your **real** left mouse button once. This tells the program which physical mouse to watch.
4. You're ready. Hold your real left mouse button, and — depending on which mode you've turned on in the phone app — your phone will either smoothly move the cursor down (**Stroke**) or click repeatedly (**Tapping**, full version only).

**Middle mouse button click = emergency stop.** If anything ever seems stuck, click your mouse wheel to immediately release the held state.

---

## Using the app

- **Two tiles on the main screen: Stroke and Tapping.** Tap anywhere on a tile to turn that mode on or off. Tap the mode's *name* specifically to open its settings (speed, presets).
- **Presets:** each mode has 11 named presets you can switch between and customize.
- **Settings icon (top right, gear symbol):** switch the app's language between English and Russian. The PC program has the same option in its own header.

---

## Troubleshooting

| Problem | What to do |
|---|---|
| App won't install / "blocked by Play Protect" | Allow installation from this source in the prompt, or check Settings → Security → allow unknown apps for the app you used to open the APK |
| Phone not detected by the PC program | Make sure USB debugging is on and you tapped "Allow" on the phone; try a different USB cable — some cables are charge-only |
| Bluetooth pairs but app still says "waiting for Bluetooth connection" | Remove the device from Windows Bluetooth settings and re-pair with the app open and in the foreground on the phone |
| Calibration doesn't detect your mouse click | Make sure you clicked your PC's actual mouse, not the phone, and that "CONNECT VIA USB" was successful first |
| Windows SmartScreen blocks the exe | Click "More info" → "Run anyway" |
| Everything stops responding after a while | Click the emergency stop (middle mouse button), then try again |


https://t.me/unagilab
