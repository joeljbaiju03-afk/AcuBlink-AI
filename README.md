# AcuBlink AI 👁️🚗
**An Edge-Based Driver Drowsiness Detection System**  
*Submitted for the India AI Impact Festival 2026 | Track: AI Impact Creators*[cite: 1]

---

## 🚀 Live Links
* **Live Application:** [Launch AcuBlink AI](https://your-username.github.io/AcuBlink-AI/)
* **Source Repository:** [GitHub Code Link](https://github.com/your-username/AcuBlink-AI)

---

## 🛠️ Project Configuration & Technical Specifications

AcuBlink AI runs entirely on the client side (in-browser) using native web technologies to process live webcam streams for early fatigue and impairment detection[cite: 1, 4].

### 💻 System Requirements
* **Hardware:** Any general-purpose computing system (Laptop/Desktop) equipped with a standard built-in or USB webcam[cite: 1, 2].
* **Software:** A modern web browser (Chrome, Edge, Safari, Firefox) with camera permissions enabled.
* **Network:** Zero bandwidth required post-initial load. The application runs entirely offline/on-device[cite: 1, 2].

### 🧱 Core Architecture & Tech Stack
* **Front-End & UI:** Custom HTML5, CSS3, and JavaScript dashboard designed for continuous monitoring, featuring real-time state alerts and dynamic calibration meters[cite: 2, 4].
* **AI & Computer Vision Engine:** `face-api.js` utilizing the pre-trained `TinyFaceDetector` and `faceLandmark68Net` models executed locally[cite: 4].
* **Audio Warning Pipeline:** Native HTML5 Web Audio API generating precise, continuous dual-tone siren frequencies (950 Hz / 650 Hz) locally without relying on external media files[cite: 4].

### ⚙️ Algorithmic Variables & Thresholds
The detection pipeline calculates the **Eye Aspect Ratio (EAR)** across both eyes using a 5-frame moving average to smooth out momentary tracking jitter[cite: 4]:

* **Calibration Period:** Automatically samples the user's natural open eye posture for 1500 ms upon startup[cite: 4].
* **Drowsiness State Threshold:** Dynamically set to Baseline EAR × 0.75[cite: 4].
* **Micro-Sleep Buffer:** Triggered if the EAR drops below the threshold continuously for ≥ 1200 ms (~1.2 seconds)[cite: 4].
* **Safety Watchdog:** Fires a safety alarm if no face is detected in the frame for ≥ 3000 ms (3 seconds) to account for camera obstruction or displacement[cite: 4].

---

## 🌍 Responsible AI Principles Met
* **Privacy by Design:** Video frames are processed strictly in local RAM and are instantly discarded. No facial metrics or streaming data leave the user's local device[cite: 1].
* **Environmental Sustainability:** Zero cloud inference server overhead, heavily minimizing the carbon footprint through optimized client-side processing[cite: 1].
* **Bias & Equity Mitigation:** The integrated real-time calibration mechanism allows the system to adapt dynamically to individual unique eye shapes and changing environmental baselines[cite: 1, 4].

---

## 📜 Credits & Attributions
* **Core Engine:** Models and frameworks powered by open-source [@vladmandic/face-api](https://github.com/vladmandic/face-api)[cite: 4].
* **Dataset Benchmark Alignment:** Validated against edge test cases with future integration alignment targeted for the NTHU Drowsy Driver Detection (NTHU-DDD) public benchmark dataset[cite: 1].
