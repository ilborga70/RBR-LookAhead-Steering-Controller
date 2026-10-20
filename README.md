# 🏎️ RBR LookAhead Steering Controller

> **Universal Telemetric Camera Bridge for Richard Burns Rally (RBR)**  
> Developed by **ilborga70**

A lightweight, high-frequency (60Hz UDP) telemetry bridge designed to simulate realistic head and camera movement in Richard Burns Rally without requiring VR headsets or head-tracking hardware.

---

## 🆕 What's New in Version 1.0.0.0

### ✨ New Features
- **Pitch Axis Integration:** Added full support for dynamic control of the *Pitch* axis, allowing you to vertically tilt the camera view based on the steering angle.
- **Dedicated GUI Controls:** Introduced a new `Checkbox` and `NumericUpDown` on the right-hand column to enable/disable and finely adjust the intensity of the *Pitch Tilt*.
- **Extended UDP Telemetry:** The monitoring label at the bottom right now displays the three active axes (**Yaw**, **Pitch**, and **Roll**) in real-time.

### 🛠️ Improvements & Optimizations
- **OpenTrack UDP Protocol:** Updated the 48-byte binary buffer to correctly map *Pitch* at offset `8..15`, alongside *Yaw* (`24..31`) and *Roll* (`40..47`).
- **Configuration Persistence (`config.json`):** Updated save, load, import, and export functions to include `EnablePitchTilt` and `PitchTiltSens` parameters.
- **Internationalization (i18n):** Added complete translation strings (Italian / English) and related descriptive tooltips for the new controls.

## 🆕 What's in Version 0.9.0.0

- **Dynamic Apex Roll Tilt:** Added natural camera roll/tilt toward the corner apex when steering for enhanced immersion during high-speed cornering and drifting.
- **UI Controls:** Added an **ON/OFF toggle** for the Roll Tilt feature, along with an intensity percentage adjustment slider/spinbox.
- **Complete UDP Telemetry:** Real-time visual display in the GUI for both **Yaw** and **Roll** values sent directly to OpenTrack at 60Hz.
- **JSON Configuration Persistence:** Integrated automatic saving and loading for the Roll Tilt settings into the project's `.json` configuration file.

---

## 🛠️ Step-by-Step Setup Guide (RBR)

### 0. Download & Install Prerequisites
- Download and install **OpenTrack**:  
  👉 [OpenTrack Releases (GitHub)](https://github.com/opentrack/opentrack/releases)

---

### 1. Enable TrackIR in RBR Configuration
1. Open your main **Richard Burns Rally** installation folder.
2. Locate and open the `RichardBurnsRally.ini` file using Notepad.
3. Add or modify the following line:
   ```ini
   UseTrackIR = true
   ```
4. Save and close the file.

---

### 2. Configure LookAhead Steering Controller
1. Extract the `LookAhead Steering Controller` archive and launch `LookAhead Steering Controller.exe` as **Administrator**.
2. Set **Wheel Degrees (Lock-to-Lock)** to `1800°`.  
   > 💡 **Technical Note:** Keeping `1800°` as a fixed baseline in the software provides a full 5-rotation dynamic scale (`1800 ÷ 2 = 900°`, `1800 ÷ 3.33 = 540°`, `1800 ÷ 5 = 360°`, `1800 ÷ 10 = 180°`), guaranteeing 100% linear telemetry without rounding errors.  
3. **Important:** Adjust real physical steering lock degrees **exclusively within your wheelbase software** (e.g., Fanatec Fanalab, Simucube True Drive, Thrustmaster Control Panel) to match the car's specifications.

---

### 3. OpenTrack Universal Output Mapping
Open OpenTrack and set **Input** to `UDP over network` (Port `4242`) and **Output** to `freetrack 2.0 Enhanced`.

#### A. Options → Output Matrix
Configure the mapping matrix so a single profile works universally across both **LHD** and **RHD** vehicles:

<img width="2560" height="1044" alt="RBR LookAhead Steering Controller v1 0 0 0" src="https://github.com/user-attachments/assets/f7ab919f-bef1-439b-b305-a78b015d4a19" />

---

### 4. Run & Drive
1. Click **Start** inside OpenTrack.
2. Verify the status in the LookAhead Steering Controller's **System Process Status** diagnostic panel.
3. Launch **Richard Burns Rally** and scendi in pista! 🏎️💨

---

## 🎮 Windows Security & SimRacing: Why exclude the LookAhead Steering Controller? 🏎️💨

Have you noticed this file in the Windows Defender exclusions? Let’s break down why adding `LookAhead Steering Controller.exe` is essential for your setup! 👇

### 🛡️ 1. Preventing False Positives (Unjustified Blocks)
This program is a third-party utility designed to calculate wheel movements and camera angles for racing simulators. Because it reads hardware data and shares it directly with other software (like OpenTrack), Windows Defender might mistake this behavior for malicious activity (like a keylogger). Adding it to your exclusions stops Windows from blocking or deleting it by mistake!

### ⚡ 2. Eliminating Micro-Stuttering & Input Lag
Windows Antivirus scans files in real-time. As shown in the software window, this controller transmits data at a very high frequency (**60Hz — 60 times per second**). If the antivirus analyzed every single data packet while you were driving, it would cause:
- 📈 **Abnormal CPU spikes**
- ⏱️ **Delayed inputs (input lag)**
- 🛑 **Micro-stuttering during your races**

### 📂 3. Why the Entire D:\ Drive is Excluded
You can also see that the whole `D:\` folder is listed. Sim-racers often do this to prevent Microsoft Defender from constantly scanning heavy game files installed on a secondary HDD or SSD. This significantly improves overall loading times and game fluidity!

---

## 🔬 Is this file 100% safe?

**Yes!** If you are worried about security, the file has been fully analyzed on Jotti's malware scan. The results show **0/13 scanners** reporting malware, meaning top antiviruses like Kaspersky, BitDefender, and Avast found absolutely nothing.

🔗 **Check the full safety report here:** [Jotti's Malware Scan Report](https://virusscan.jotti.org/it-IT/filescanjob/g84ynyzizw)

---

## 📜 Intellectual Property & Attribution Notice

**Copyright © 2026 ilborga70. All rights reserved.**

**LookAhead Steering Controller** is an original utility developed and owned by **ilborga70**.

* 🚫 **No Unauthorized Redistribution:** You may not re-upload, host, or redistribute the binary executable files (`.exe`), plugins (`.dll`, `.asi`), or codebase on any other website, forum, or repository without prior written consent.
* 🏷️ **Attribution & Derivative Concept:** If you develop, publish, or share a similar utility, derivative project, or concept inspired by or built upon the methodologies introduced by *LookAhead Steering Controller* (such as high-frequency 60Hz UDP telemetry bridging or 1800° linear calibration matrices), **you must explicitly give clear credit and attribute the original concept and work to ilborga70** with a direct link back to this official repository.
* 📦 **Mod Packaging:** Modpack creators and community developers must link directly to this official repository rather than bundling the software directly.
* 💼 **Non-Commercial Use Only:** This software is provided free for personal, non-commercial use. Commercial monetization or bundling is strictly prohibited.
* 🛡️ **Disclaimer:** Provided "as is" without warranty of any kind.

---

👨‍💻 **Created by ilborga70** • [Pro-Sim Utilities Hub](https://ilborga70.github.io/Pro-Sim-Utilities-Hub)
