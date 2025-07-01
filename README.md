
# 🎮 Assembly-PinBall

> **A Retro Pinball Game Built from Scratch in 8086 Assembly**

---

## 🧭 Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Game Instructions](#game-instructions)
- [Code Highlights](#code-highlights)
- [Documentation](#documentation)
- [Examples](#examples)
- [Reflections](#reflections)
- [Contributors](#contributors)
- [License](#license)

---

## 📘 Introduction

**Assembly-PinBall** is a DOS-based pinball game written entirely in **8086 Assembly**. It was developed as part of a high school computer science final project and accounted for **30% of the Bagrut (Israeli matriculation) grade** at the 2-unit programming level.

The goal is simple: **get the highest score you can before the ball falls off the screen**. The experience of building this project from low-level hardware interfaces to game logic and graphics was both challenging and fun.

> _"I had a blast developing this project. It was my first experience with assembly language, and I learned so much about how computers work under the hood."_

---

## ✨ Features

- 🎯 Real-time ball physics and collision logic
- 🕹️ Player-controlled flippers using keyboard input
- 🖼️ BMP image background rendering
- 🔊 Sound effects using PC speaker and hardware ports
- ⏱️ Score tracking and high score memory
- 🎲 Randomized ball start positions
- 🧱 Obstacle detection and bouncing mechanics

---

## 🛠 Technology Stack

| Component         | Details                    |
|------------------|----------------------------|
| Language          | Assembly (TASM 8086)       |
| Development Env.  | DOSBox 0.74                |
| Assembler         | Turbo Assembler (TASM)     |
| Text Editor       | Notepad++                  |
| Graphics          | 320x200 VGA, BMP rendering |
| Sound             | PC speaker (via port I/O)  |
| Input             | Keyboard buffer handling   |

---

## 💾 Installation

### Requirements

- DOSBox or compatible 16-bit DOS environment
- Turbo Assembler (`TASM.EXE`) and Turbo Linker (`TLINK.EXE`)
- `base.asm` (main source file)
- `CHEN3.BMP` (BMP background image)

### Setup

```bash
tasm base.asm
tlink base.obj
base.exe
```

Or run directly in DOSBox:

```bash
mount c /path/to/project
c:
base.exe
```

---

## ▶️ Usage

Once launched:

- The game will display a message asking where you want the ball to start:
  - Press `T` for Top
  - Press `R` for Right
  - Press `L` for Left

- Use:
  - `W` and arrow keys to **control the flippers**
  - Try to **bounce the ball** and **hit walls** to earn points
  - At the end of the game, your score is displayed and compared to the high score

To play again, press **C**. To exit, press any other key.

---

## 🎮 Game Instructions

- The objective is to **keep the ball in play** and **score as high as possible**.
- Obstacles in the center of the screen increase your score when hit.
- Side walls and flippers allow you to reflect the ball and keep it from falling.
- Score is calculated and compared against the stored high score.

---

## 🔍 Code Highlights

Here are a few interesting technical components:

- **`RandT`, `RandL`, `RandR`**  
  Custom random number generators using the system clock and memory XORing to determine ball start position.

- **`BALL`, `rectangle`, `pixel`**  
  Manual pixel manipulation and rendering using **interrupt 10h** for VGA graphics.

- **`sound`**  
  Sound effects played through **port 61h and 43h** with timer setup for tone generation.

- **`rect` & `timerrect`**  
  Player paddle input logic and smooth animation with delay loops and key detection.

- **`CopyBitmap`**  
  BMP background loading and drawing using manual byte-by-byte copying to video memory.

---

## 📄 Documentation

📄 A full [project report](תיק%20פרויקט.pdf) is included in this repository. It contains:
- Game overview
- Visuals from the game
- Core code excerpts
- Implementation details in Hebrew

> 💡 Tip: For reading and modifying the game logic, refer directly to `base.asm`.

---

## 🖼️ Examples

Here’s what the game looks like during play (you can upload screenshots here):

```markdown
![Game Start](Screenshots/start.png)
![Gameplay](Screenshots/action.png)
![Game Over](Screenshots/end.png)
```

> To add your own images, place them in `/Screenshots/` and reference them using standard Markdown.

---

## 🪞 Reflections

> “Some parts were easy and came naturally, while others took long hours of thinking and problem-solving. If I had started earlier, maybe I could have done even more — but I'm proud of what I built.”

Possible future improvements:
- Add irregular or circular obstacles
- Expand the number of levels or game speed
- Add real-time scoring overlay during play

---

## 👨‍💻 Contributors

- **Chen Shor** – Developer, Designer  
  > Ben Gurion High School – Computer Science Track  
  Guided by **Lina Schmidt**

---

## 📄 License

**MIT License**  
Feel free to copy, study, or remix this game for learning or personal use — just give credit!
