# Voxel Architect v4.1

**Voxel Architect** is a browser-based Augmented Reality (AR) spatial modeling tool that enables users to construct 3D voxel structures using touch-free hand gestures.

Powered by **Three.js** and **Google MediaPipe**, this application leverages computer vision to translate skeletal hand tracking into a "Minority Report" style interface, complete with a sci-fi HUD and intent-locking mechanisms to prevent accidental inputs.

## 🚀 Features

* **Touch-Free Interaction:** Fully controlled via webcam input using specific hand signs (fist, pinch, open palm).
* **Real-Time Hand Tracking:** Visualizes "Cyber Hands" with skeletal overlays and smoothed landmark tracking for stability.
* **Smart Building System:**
* **Voxel Snapping:** Blocks snap to a 1.2-unit grid for precision.
* **Axis Locking:** Automatically detects the primary direction of movement (X, Y, or Z) to draw straight lines.


* **Intent Detection:** Uses "Hold" timers (visualized by HUD circles) to confirm destructive or system-level actions, preventing jitter-based errors.
* **Cyberpunk UI:** Custom CSS and Canvas rendering provide a neon, high-contrast aesthetic with real-time status updates.

## 🛠️ Tech Stack

* **Core:** HTML5, CSS3, Vanilla JavaScript (ES6+).
* **3D Engine:** [Three.js (r128)](https://threejs.org/) - Handles the voxel rendering, scene management, and lighting.
* **Computer Vision:** [MediaPipe Hands](https://www.google.com/search?q=https://google.github.io/mediapipe/solutions/hands) - Provides high-fidelity hand tracking and landmark detection directly in the browser.

## 🎮 Controls & Gestures

The system uses a specific gesture language to manage the environment. Ensure both hands are visible to the camera.

### Building & Editing

| Action | Gesture | Description |
| --- | --- | --- |
| **Build Voxel** | **Right Hand Pinch** (Thumb + Index) | Creates voxels at the cursor location. Hold to draw lines. |
| **Erase Voxel** | **Left Pinch** + **Right Point** | Locks the eraser mode. Hover over existing blocks to remove them. |
| **Commit Sketch** | **Open Right Palm** | Finalizes the current sketch, converting wireframes into solid blocks. |

### Navigation & System

| Action | Gesture | Description |
| --- | --- | --- |
| **Grab / Pan** | **Left Hand Fist** | Clench the left hand to "grab" the world and move the camera position. |
| **Rotate World** | **Two Open Palms** | Hold both palms open to enable rotation mode. Move hands relative to each other to rotate. |
| **Hard Reset** | **Two Fists** | Hold two fists simultaneously to wipe the scene and reset the camera. |

## 📦 Installation & Usage

This application is designed as a standalone HTML file with no build step required.

1. **Download:** Save the code as `index.html`.
2. **Run:** Open the file in a modern web browser (Chrome/Edge/Firefox).
* *Note:* Because this app requires webcam access, you must run it either from `localhost` or via a secure HTTPS connection. If opening the file directly (file://) blocks the camera, use a simple local server (e.g., VS Code "Live Server" extension).


3. **Permissions:** Allow camera access when prompted by the browser.

## ⚙️ Configuration

Key variables can be adjusted within the `<script>` tag:

* **`gridSize`**: Controls the size of the voxels (Default: `1.2`).
* **Timers**:
* `GRAB_HOLD`: Time required to trigger a grab (Default: 500ms).
* `INTENT_HOLD`: Time required to lock build/erase modes (Default: 500ms).
* `RESET_HOLD`: Time required to trigger a hard reset (Default: 1000ms).
