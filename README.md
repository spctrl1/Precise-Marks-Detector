# Precise Marks Detector

Monitors specific screen regions for game marks (1x, 2x, 3x) and triggers alerts based on visibility duration. 

## [PRESS F6 AND F7 BOTH TO START TRACKING]

[![Download Latest Release](https://img.shields.io/badge/Download-Stable_Release-blue?style=for-the-badge)](https://github.com/spctrl1/Precise-Marks-Detector/releases/latest)

---

## Requirements
* **Resolution**: 1920x1080.
* **Display Scale**: 100% (Windows Settings).
* **Game Mode**: Roblox must be in **Windowed Fullscreen** or **Fullscreen**.
    * *Note: If using Fullscreen, use the "Area Preview" tool while tabbed in to ensure your sliders (X1, Y1, X2, Y2) are correctly framing the UI element.*
<img width="1915" height="136" alt="image" src="https://github.com/user-attachments/assets/a312c4a9-f0cc-4c55-be47-1ace94655507" />


---

## 1. Search Area
You must define the zone where marks appear before tracking.

* **Coordinates**: Use X1, Y1, X2, and Y2 sliders to frame the zone.
* **Area Preview**: Displays a red box indicating the current search perimeter.
* **Debug View**: Shows the grayscale green-channel isolation used for detection logic.

## 2. Alert Rules
Uses conditional logic: **IF [Trigger] > [Wait Time] THEN [Action]**.

* **Triggers**: None, 1x, 2x, or 3x.
* **Wait (s)**: Seconds the condition must stay true before the alert fires.
* **Repeat (Loop)**: If enabled, the alert repeats every X seconds until the condition breaks.
* **Actions**: 
    * **Sound**: Plays pre-loaded audio (Ominous, Elevator, Pipe, etc.).
    * **Flash**: Oscillates the status overlay between white and your custom color.

**Example Logic:**
* `IF None > 10.0s THEN sound (Ominous)` — alerts if a buff is lost.
* `IF 3x > 5.0s THEN flash [LOOP]` — confirms you are at max stacks.

## 3. Overlay
Provides real-time feedback over the game window.

* **Toggle**: Press **F7** to show or hide.
* **Settings**: Adjust position, text size, and color via the menu.
* **Transparency**: The overlay is click-through and transparent to avoid obstructing gameplay.

## 4. Technical Settings
* **Match Confidence**: Accuracy threshold. 0.90 - 0.95 is recommended.
* **Scan Delay**: Seconds between screen checks. 0.5s to 0.8s is recommended.
* **Audio Volume**: Global volume for all alerts.
* **Grace**: Buffer duration. If you briefly lose a mark (walking out of range, etc.), the timer will not reset for this duration.
