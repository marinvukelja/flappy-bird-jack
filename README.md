# Flappy Bird (Jack / Nand2Tetris)

A tiny **Flappy Bird–style side scroller** written in the Jack language (Project 9–11 of the Nand2Tetris course). It runs on the Hack platform via the provided JackCompiler and VM Emulator.

https://github.com/marinvukelja/flappy-bird-jack

## ✨ Features
- Start screen with **difficulty selection** (1 = Easy, 2 = Hard)
- **SPACE** to flap/jump, **Q** to quit or return to the menu
- Moving pipes with a vertical gap; **score** increments when you pass a pipe
- **Win at 10 points**, otherwise _Game Over_ with option to replay
- Pure Jack implementation with minimal helpers

## 🎮 Controls
- **SPACE** — jump / flap (first press starts the game)
- **1 / 2** — set difficulty (Easy / Hard) on the start screen
- **Q** — quit the current run (back to menu / exit)
- Score and chosen difficulty are rendered on-screen

## 🧱 How it works (high level)
- `Main.jack` — boots the game loop and delegates to `Game`.
- `Game.jack` — orchestrates input, start menu, difficulty, pipes, scoring, collisions, win/lose, and restart.
- `Player.jack` — bird sprite rendering and simple physics (gravity + jump impulse).
- `Pipe.jack` — obstacle logic, scrolling, random vertical gap, collision + scoring (“coin”) logic.
- `Score.jack` — score state + drawing.
- `LCGRandom.jack` — PRNG used for pipe placement (BSD 2-Clause, see **Licensing**).
- `Utils.jack` — small helpers (e.g., `mod`).

## ▶️ Run it locally

### Requirements
- Java (for the official Nand2Tetris tools)
- Nand2Tetris **JackCompiler** and **VMEmulator** (GUI or CLI)

### Quick start (GUI)
1. Open **JackCompiler** and compile this folder (you should get `.vm` files).
2. Open **VMEmulator**, **Load Program** → choose the folder with the compiled `.vm` files.
3. (Optional) Set **No Animation** or higher speed.
4. **Run**. Use the controls above.

### Quick start (CLI)
```bash
# Compile Jack → VM
path/to/JackCompiler.sh .
```

## 🧪 Difficulty & goals
- **Easy**: slower pipes / larger gap.
- **Hard**: faster pipes / smaller gap.
- **Goal**: reach **10 points** to see the “YOU WON!!” screen; otherwise, you’ll see “YOU LOST :(”.

## 📁 Project structure
```
.
├─ Game.jack
├─ Main.jack
├─ Player.jack
├─ Pipe.jack
├─ Score.jack
├─ LCGRandom.jack
├─ Utils.jack
└─ README.md
```

## 🚀 Put this on GitHub
```bash
git init
git add .
git commit -m "Add Flappy Bird in Jack (Nand2Tetris)"
git branch -M main
git remote add origin https://github.com/marinvukelja/flappy-bird-jack.git
git push -u origin main
```

## 🧾 Licensing
- **This repository (your code)**: MIT (see `LICENSE`).
- **Third-party**: `LCGRandom.jack` is © 2013 Rowan Limb, **BSD 2-Clause**. See `THIRD_PARTY_LICENSES.md`.

## 🙌 Notes
- Designed for the standard nand2tetris toolchain.
- The code is intentionally straightforward for readability.
