# 🏎️ Turbo Racers Pro

A local multiplayer + AI racing game built in modern **C++17** with
**raylib**. This is the Phase 1 rebuild of the original Turbo C racing
project: a real curving closed-loop circuit, a full lap/checkpoint
system, nitro boost, drifting, AI opponents that genuinely race you,
a live minimap, and a full racing HUD.

![C++17](https://img.shields.io/badge/C%2B%2B-17-blue.svg)
![raylib](https://img.shields.io/badge/graphics-raylib-orange.svg)
![CMake](https://img.shields.io/badge/build-CMake-064F8C.svg)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey.svg)

---

## ✨ Features

- **Real closed-loop circuit** — a single long, hand-designed track with a hairpin, an S-chicane, and sweeping corners, rendered with kerb stripes and a checkered start/finish line
- **Mixed human + AI grid** — race with 1–3 human players locally *and* up to several AI opponents on the same track, all at once
- **Garage / race setup screen** — choose how many human players, how many AI opponents, how many laps to win, and each human's car color and name, all from a real working menu
- **Lap system with checkpoints** — laps only count once a car has genuinely driven most of the way around the track, not just touched the line
- **Live race HUD** — speedometer, gear indicator, RPM bar, nitro meter, lap counter, live race position, and elapsed time
- **Real-time minimap** — shows the whole track outline and a dot for every racer's live position, player highlighted
- **Nitro boost** — hold to burn a fillable meter for a temporary top-speed increase, with visual flame and smoke effects
- **Drift mechanic** — steer hard while going fast to slide through corners, with a visual slip angle and HUD indicator
- **AI opponents with rubber-banding** — AI cars steer toward the track centerline like a real driver and dynamically adjust their pace to stay competitive without ever being unbeatable or hopeless
- **Camera shake & confetti** — on race finish, for a satisfying payoff
- **Pause / resume**

## 🎮 Controls

| Player    | Accelerate | Steer       | Brake | Nitro        |
|-----------|------------|-------------|-------|---------------|
| Player 1  | **Z**      | **A** / **D** | **S** | **Left Shift** |
| Player 2  | **↑**      | **←** / **→** | **↓** | **Right Ctrl** |
| Player 3  | **M**      | **J** / **L** | **K** | **Right Alt**  |

Hold your accelerate key, steer into corners, and hold steer hard while
fast to drift. Complete the configured number of laps before everyone
else to win.

**Other controls:**

| Key      | Action                          |
|----------|----------------------------------|
| ↑ / ↓    | Navigate menus / garage rows     |
| ← / →    | Change a value in the garage     |
| Enter    | Select / confirm                 |
| Esc      | Back out of a menu or garage     |
| P        | Pause / resume during a race     |

## 🛠️ Technologies Used

- **C++17** — object-oriented architecture (`Game`, `Car`, `Track`, `Menu`, `GarageMenu`, `Audio`)
- **[raylib](https://www.raylib.com/)** — graphics, input, and audio
- **CMake** — cross-platform build configuration

No `graphics.h`, no Turbo C, no DOSBox — standard modern C++ that
compiles with any current GCC/Clang/MSVC toolchain.

---

## 📦 Installation & Setup (Windows + VS Code)

### 1. Install MinGW-w64 via MSYS2

1. Download and run the installer from [msys2.org](https://www.msys2.org/)
2. Open the **MSYS2 MinGW64** terminal (specifically this one, not plain MSYS2 or UCRT64) and run:
   ```
   pacman -S mingw-w64-x86_64-gcc mingw-w64-x86_64-cmake mingw-w64-x86_64-make
   ```
3. Add `C:\msys64\mingw64\bin` to your Windows **PATH** environment variable
4. Open a **new** terminal and confirm: `g++ --version` and `cmake --version`

### 2. Install VS Code extensions

- **C/C++** (by Microsoft)
- **CMake Tools** (by Microsoft)

### 3. Get the project

Unzip this project, then in VS Code: **File → Open Folder...** → select
the `TurboRacersPro` folder (the one with `CMakeLists.txt` directly
inside it).

> raylib is downloaded and built automatically the first time you
> build — no separate install needed. The first build takes a few
> extra minutes; later builds are fast.

---

## ▶️ How to Build & Run

**Using VS Code:** `Ctrl+Shift+P` → `CMake: Configure` (pick the GCC/mingw64
kit if asked) → `Ctrl+Shift+P` → `CMake: Build` → `Ctrl+Shift+P` →
`CMake: Run Without Debugging`.

**Using a terminal:**
```
mkdir build
cd build
cmake .. -G "MinGW Makefiles"
cmake --build .
TurboRacers.exe
```

---

## 🔊 Adding Sound (Optional)

All sound calls are already wired up — engine, countdown, nitro, lap,
win, menu clicks, and background music. The game runs perfectly with
no audio files (it just stays silent); drop files into
`Assets/sounds/` using the names listed in the README inside that
folder to enable them, no code changes required.

## 📁 Folder Structure

```
TurboRacersPro/
├── src/                  # main.cpp, Game.cpp, Car.cpp, Track.cpp, TrackFactory.cpp, Menu.cpp, Audio.cpp
├── include/               # matching headers + RaceConfig.h
├── Assets/sounds/         # drop .wav/.ogg files here (see README inside)
├── Assets/fonts/          # optional custom fonts
├── CMakeLists.txt
└── README.md
```

## 🗺️ What's Next (Phase 2+)

This Phase 1 build focuses on one fully-tested, fully-working circuit
and feature set. Planned next: additional tracks (City, Desert,
Mountain, Forest themes), weather effects, and more sound design —
each as its own tested addition rather than all at once.

## 👥 Credits

Designed and developed by:

- **Umar Patel**
