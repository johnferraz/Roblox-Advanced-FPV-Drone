# 🚁 Advanced FPV Kamikaze Drone System (Roblox)

![Roblox Studio](https://img.shields.io/badge/Engine-Roblox_Studio-blue?style=for-the-badge&logo=roblox)
![Luau](https://img.shields.io/badge/Language-Luau-00A654?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Delivered_to_Client-success?style=for-the-badge)

> ⚠️ **Ownership Notice:** This system was developed exclusively for a client. Due to non-disclosure agreements (NDA) and copyrights, the source code is not public. This repository serves solely as an architectural portfolio and a demonstration of technical skills.

## 📌 About the Project
A complete and highly immersive FPV (First Person View) Drone system focused on Kamikaze attack mechanics. The project was designed to break away from Roblox's standard, rigid physics, delivering a realistic flight experience based on vectors, inertia, and environmental forces.

<img width="1358" height="672" alt="dronfly" src="https://github.com/user-attachments/assets/04137149-3be7-40da-ae4b-85464de0576d" />

## ✨ Key Features

### 1. Custom Flight Physics (Vector-Based)
The system bypasses standard Roblox controllers and uses vector mathematics within a `RenderStepped` loop to calculate:
- **Inertia and Drift:** The drone doesn't magically stop in mid-air; it drifts based on its current velocity.
- **Dynamic Instability (Wobble):** Uses noise algorithms (`math.noise`) to simulate the natural turbulence of wind and rotors.
- **Realistic Tilt:** The physics model dynamically rotates the X and Z axes according to the pressed keys (W, A, S, D).

### 2. Tactical Military HUD
*(Replace this line with a nice print of the green screen we made)*

<img width="1346" height="668" alt="gifexplod" src="https://github.com/user-attachments/assets/54e24325-810b-43a3-b68b-4424e119e989" />

- Graphical Interface generated 100% via code.
- Real-time scanning of Altitude (ELV), Speed (SPD), Distance to Target (DST), and Compass (DIR).
- Minimalist tactical design inspired by military targeting systems.

### 3. Dynamic Audio (Sound Engine)
- **Pitch Modulation:** The engine sound is not a static loop. `PlaybackSpeed` and `Volume` respond directly to the magnitude of the drone's linear velocity, creating a high-pitched "whine" effect during high-speed dives.

### 4. Detonation System and Physical Knockback
- Pressure area calculation (`BlastRadius`) with mathematical decay: targets in the center take more damage than targets on the edges.
- Instant lethal damage (`Insta-kill`) if the detonation occurs within 8 studs of distance.
- **Calculated Knockback:** Surviving targets are thrown based on the inverse vector from the explosion's epicenter, temporarily disabling `PlatformStand` so they react to the environment's gravity.

<img width="1353" height="666" alt="drone" src="https://github.com/user-attachments/assets/0e5e5677-5015-4da5-a032-e524cc684fea" />


## 🧠 Technical Challenges Solved
- **Memory Management:** The system scans and automates the welding (`WeldConstraint`) of parts and ensures all script connections are destroyed (`Disconnect()`) or cleaned up by `Debris` after the explosion, preventing server Memory Leaks.
- **Camera Control:** Advanced scripting for smooth transitions (and player freezing) between the grounded character and the onboard drone view using `Enum.CameraType.Scriptable`.
<img width="1351" height="668" alt="img1" src="https://github.com/user-attachments/assets/3ad2215e-09fa-4652-8987-f80a38d0c87f" />

---
*Developed by JohnFerraz - Focused on Gameplay Engineering and Physical Systems.*
