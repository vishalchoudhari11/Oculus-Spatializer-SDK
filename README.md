# 🎧 Spatializer SDK

**Real-time 3D Audio Simulation for Moving Sound Sources**  

This repository builds upon the **Oculus Audio SDK** to generate immersive spatialized audio that mimics **time-varying, moving sound sources** 🎶.  
Simply provide a set of *N* monaural input tracks, each with its own unique trajectory — and get a **fully rendered 3D spatial audio mix** as output 🌌.  

> 💡 *Reference:* The main logic for `processing_sound.cpp` was derived from `AudioSDK/Include/OVR_Audio.h`.

---

## ⚙️ Installation & Workflow

1. 📂 **Add Sound Files**  
   Create a new folder under `Sound Samples/` and place your *N* monaural sound files inside.

2. 🧠 **Pre-process with MATLAB**  
   Open `preprocessing_sound.m` and tune parameters as needed, then run it to generate intermediate files in the `ToCPP/` directory.

3. 🧱 **Compile & Spatialize**  
   From the repository root, run:  
   ```bash
   g++ processing_sound.cpp -IAudioSDK/Include -LAudioSDK/Lib/Linux64 -lovraudio64
   ```  
   *(You may need to link additional libraries depending on your OS.)*

4. 🎧 **Output Generation**  
   The spatialized audio files will be written to the `FromCPP/` directory.

5. 🎛️ **Post-Processing**  
   Open `post-processing_sound.m` in MATLAB, adjust parameters, and run it to generate the **final spatialized mix** in the `Spatialized/` directory.

---

## 🚀 Features

- 🔊 **Multi-source 3D audio rendering** with smooth spatial transitions  
- 🌀 **Dynamic trajectories** for each source, supporting complex motion paths  
- ⚡ **Hybrid MATLAB + C++ pipeline** for rapid prototyping and efficient rendering  
- 🎯 Compatible with **Oculus Audio SDK** (Linux64 build demonstrated)

---

## 💬 Contributing & Ideas

Open to contributions, feature requests, and crazy audio experiments!  
If you’ve got ideas for generalizing the SDK (multi-listener, HRTF libraries, real-time streaming, etc.), please share.  

> ✉️ *Pull requests and discussions are always welcome — let’s make spatial audio smarter together!*
