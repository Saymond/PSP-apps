# PSP-apps
High-performance PSP homebrew collection. Native C ports of J2ME apps (Mini Mine, Cornell Box) featuring real-time Ray Tracing using hardware VFPU assembly.

# PSP Homebrew Collection

![Platform](https://img.shields.io/badge/Platform-PSP-blue?style=for-the-badge&logo=playstation)
![Language](https://img.shields.io/badge/Language-C%20%2F%20VFPU%20Asm-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-orange?style=for-the-badge)

A collection of high-performance homebrew applications and demos for the **Sony PlayStation Portable (PSP)**.
Originally based on J2ME projects, these have been rewritten in **C** using **PSPSDK** and heavily optimized with **VFPU Inline Assembly** to achieve real-time Ray Tracing and Path Tracing on handheld hardware.

## 📥 Downloads

Go to the [**Releases**](#) page to download the latest `EBOOT.PBP` files.
Each app is a standalone homebrew; no extra plugins required.

## 🚀 How to Run

### Real Hardware (PSP-1000/2000/3000/Go/Street)
1. Connect your PSP to PC via USB.
2. Copy the app folder (containing `EBOOT.PBP`) to `ms0:/PSP/GAME/`.
3. Launch via the **Game -> Memory Stick** menu.
   * *Note: Requires Custom Firmware (CFW 6.60/6.61 PRO or LME).*

### Emulator (PPSSPP)
1. Open PPSSPP (Android/PC/iOS).
2. Navigate to the folder where you saved the `EBOOT.PBP`.
3. Tap to launch.

---

## 📦 What’s Inside

### 🧱 Mini Mine RT (VFPU Edition)
A voxel world exploration demo featuring a hybrid rendering engine.
*   **Ray Tracing Mode:** Hardware-accelerated Path Tracer using VFPU (`vsqrt.s`, `vrsq.s`). Features **Global Illumination**, **Ambient Occlusion**, **Soft Shadows**, and **Color Bleeding**.
*   **Progressive Accumulation:** The image quality improves while the camera is stationary.
*   **World Gen:** Procedural terrain generation (Simplex-like noise).

### 🧊 Cornell-Box PSP
Three compact graphics demos in one package:
1.  **Cube 3D:** Rotating wireframe cube (GPU/GU test).
2.  **RayCast:** Sphere tracing preview.
3.  **Cornell Box:** A full Path Traced scene adapted for PSP. Supports material changing (Diffuse, Mirror, Glass) and variable resolution.

### 💧 FluidSim2D (Port)
Real-time 2D fluid simulation. ported to C for better performance. Features smooth advection and vivid flow visualization directly in VRAM.

### 🔦 ReactiveLight 2D
2D ray emission and refraction through prisms. Clean, crisp ray visuals optimized for the PSP's 480x272 screen.

### 👕 Cloth Physics Simulator
Mass–spring cloth simulation with Verlet integration.
*   **Features:** Sphere/ground collisions, Z-buffer rasterization, and simple lighting.
*   **Tech:** Uses CPU for physics calculations and GU for rendering.

### ℹ️ System Info
Device diagnostics tool for PSP. Displays CPU clock (up to 333MHz), Bus speed, Battery info, VRAM usage, and kernel version.

---

## 🎮 Controls

| Button | Action |
| :--- | :--- |
| **Analog Stick** | Move / Strafe |
| **D-Pad** | Look / Rotate Camera |
| **L / R Triggers** | Move Up / Down (Fly) |
| **Triangle** | Change Resolution (Low -> High) |
| **Square / Circle** | Change Time of Day / Light Angle |
| **Select** | Reset Scene / Info |
| **Start** | Switch Mode (where applicable) |

## ⚙️ Compatibility & Notes

*   **Target:** PSP Custom Firmware (6.60+ recommended).
*   **Optimization:** These apps use **Direct VRAM Access** and **VFPU Assembly** for math-heavy tasks (sqrt, normalization).
*   **Performance:**
    *   *Path Tracing demos (Mini Mine RT, Cornell)* accumulate samples over time. For the best image, hold the PSP still.
    *   Clock speed is automatically set to **333MHz** for maximum performance.

## 📜 License

Licensed under the **MIT License**. See `LICENSE` for details.
