# System Overview

> Echo Pass = AI acts as a translator between humans and machines.

## 🧠 Core Concept
Echo Pass connects **AI, assistive devices, and urban signals** to turn raw sensor data into **human-understandable guidance**.

## 🏗️ Architecture (Walking Assistance Only)
- **Smart Stick**: LiDAR / Ultrasonic / IMU → local safety loop (0–50ms)
- **Smart Glass**: Camera / Object detection → on-device analysis
- **Beacons / NFC / GPS**: Location & context
- **AI Core (GPT)**: Language-level summarization & Q&A (1–2s)

```text
[Smart Stick] + [Smart Glass] + [Beacons/GPS/NFC]
            ↓ (Fusion on device)
        [Guidance loop]
            ↓
        [AI Core → Natural speech output]
