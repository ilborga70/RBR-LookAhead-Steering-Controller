# 🏎️ RBR LookAhead Steering Controller

> **Universal Telemetric Camera Bridge for Richard Burns Rally (RBR)**  
> Developed by **ilborga70**

A lightweight, high-frequency (60Hz UDP) telemetry bridge designed to simulate realistic head and camera movement in Richard Burns Rally without requiring VR headsets or head-tracking hardware.

---

## 🆕 What's New in Version 0.9.0.0

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

| Destination | Source | Pre-invert | Post-invert |
| :--- | :--- | :---: | :---: |
| **Yaw** | `Yaw` | ☐ | ☐ |
| **Pitch** | `Roll` | ☐ | ☐ |
| **Roll** | `Roll` | ☐ | ☐ |
| **X** | `Disabled` | ☐ | ☐ |
| **Y** | `Disabled` | ☐ | ☐ |
| **Z** | `Disabled` | ☐ | ☐ |

#### B. Options → Filter Setup
Select the **Accela + Hamilton Filter** and set the parameters as follows:
- **Rotation filtering (Yaw, Pitch, Roll):**
  - **Smoothing:** `1.5°`
  - **Deadzone:** `0.03°`
- **Position filtering (X, Y, Z):**
  - **Smoothing:** `1mm`
  - **Deadzone:** `0.1mm`
- **Rotation Smoothing (Zoomed):**
  - **Max Added:** `0°`
  - **Max Z:** `9.6mm`

---

### 4. Run & Drive
1. Click **Start** inside OpenTrack.
2. Verify the status in the LookAhead Steering Controller's **System Process Status** diagnostic panel.
3. Launch **Richard Burns Rally** and scendi in pista! 🏎️💨

---

👨‍💻 **Created by ilborga70** • [Pro-Sim Utilities Hub](https://github.com/ilborga70)
