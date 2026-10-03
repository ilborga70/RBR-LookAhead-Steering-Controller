# RBR-LookAhead-Steering-Controller

Looking for a dynamic cockpit view that automatically turns toward the apex as you steer? Here is the complete guide to installing and configuring this innovative utility for RBR!

<img width="1408" height="768" alt="RBR LookAhead Steering Controller v0 9 0 0" src="https://github.com/user-attachments/assets/89e1c572-1618-433e-9230-e0e0736910d7" />
<img width="1362" height="623" alt="RBR LookAhead Steering Controller v0 9 0 0_" src="https://github.com/user-attachments/assets/83172801-16c6-4b36-bd73-628c42e08d69" />

🇬🇧 What's New in Version 0.9.0.0
- Dynamic Apex Roll Tilt: Added natural camera roll/tilt toward the corner apex when steering.
- UI Controls: Added an ON/OFF toggle for the roll tilt along with an intensity percentage adjustment slider/spinbox.
- Complete UDP Telemetry: Real-time display of both Yaw and Roll values sent to OpenTrack at 60Hz.
- JSON Configuration Save: Integrated automatic saving and loading for the Roll Tilt settings in the JSON configuration file.

## ✨ Why Try It?

* **Zero Game File Modifications:** Operates completely as an independent external controller.
* **Zero Lag:** Sends camera movement data directly to OpenTrack via UDP at 60Hz.
* **Maximum Stability:** No risk of file corruption, bans, or plugin conflicts in online platforms (RSF / RBRCZ / Etc).
* **Real-Time Adjustments:** Fine-tune sensitivity, filters, and deadzones on the fly while out on the stage without restarting!

## 🛠️ Step-by-Step Setup Guide
0. **Download OpenTrack: https://github.com/opentrack/opentrack**
1. **Configure OpenTrack:**
   * Open OpenTrack and set **Input** to *UDP over network* (default port is usually `4242`).
   * Set **Output** to *freetrack 2.0 Enhanced*.
   * Click **Start**.

2. **Enable TrackIR in RBR:**
   * Open `RichardBurnsRally.ini` in your main RBR installation folder using Notepad.
   * Add or edit the line: `UseTrackIR = true`

3. **Launch the Utility:**
   * Extract the ZIP package and run the GUI executable.
   * Check the built-in diagnostic panel (**System Process Status**) to verify real-time connections for your wheel, OpenTrack, and the simulator.

## ⚙️ Recommended Tuning for Surfaces

### 🚗 TARMAC / ASPHALT
Set a **Low Smoothing Filter** ➔ Delivers an instant, highly responsive view for quick direction changes.

### 🌲 GRAVEL / SNOW
Set a **Medium-High Smoothing Filter + Small Deadzone** ➔ Eliminates micro-stuttering and violent camera shakes caused by rough Force Feedback over bumps.

> 💡 **Pro Tip:** Use the Save / Export / Import features in the GUI to create preset profiles (e.g., `tarmac_preset.json` and `gravel_preset.json`) so you can swap setups instantly before any stage! ⏱️

---

### Have you noticed this file in the Windows Defender exclusions?
Let’s break down why adding `lookahead steering controller.exe` is essential for your setup!

#### 🛡️ 1. Preventing False Positives (Unjustified Blocks)
This program is a third-party utility designed to calculate wheel movements and camera angles for racing simulators. Because it reads hardware data and shares it directly with other software (like OpenTrack), Windows Defender might mistake this behavior for malicious activity (like a keylogger). Adding it to your exclusions stops Windows from blocking or deleting it by mistake!

#### ⚡ 2. Eliminating Micro-Stuttering & Input Lag
Windows Antivirus scans files in real-time. As shown in the software window, this controller transmits data at a very high frequency (60Hz — 60 times per second). If the antivirus analyzed every single data packet while you were driving, it would cause:
* 📈 **Abnormal CPU spikes**
* ⏱️ **Delayed inputs** (input lag)
* 🛑 **Micro-stuttering** during your races

#### 📂 3. Why the Entire D:\ Drive is Excluded
In the screenshot, you can also see that the whole `D:\` folder is listed. Sim-racers often do this to prevent Microsoft Defender from constantly scanning heavy game files installed on a secondary HDD or SSD. This significantly improves overall loading times and game fluidity! 🏎️💨

## 🔬 Is this file 100% safe?

**Yes!** If you are worried about security, the file has been fully analyzed on Jotti's malware scan. The results show **0/13 scanners** reporting malware, meaning top antiviruses like Kaspersky, BitDefender, and Avast found absolutely nothing.

🔗 [Check the full safety report here](https://virusscan.jotti.org/it-IT/filescanjob/g84ynyzizw)


​
