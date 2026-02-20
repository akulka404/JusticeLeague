# Justice League: War Game

> A turn-based terminal combat game — Data Structures Course Project

## Overview

**Justice League: War Game** is a single-player, turn-based battle game written in C++. You choose a hero from the DC Justice League roster, face off against an opponent of your choice, and trade blows until one combatant is defeated. The game demonstrates object-oriented design with C++ inheritance, polymorphism, and a virtual class hierarchy.

## Prerequisites

| Tool | Version |
|------|---------|
| g++ (GCC) | C++11 or later |
| GNU Make | any recent version |

## Build & Run

```bash
# Clone the repository
git clone https://github.com/akulka404/JusticeLeague.git
cd JusticeLeague

# Compile
make

# Launch the game
./main.out

# Remove build artifacts
make clean
```

## How to Play

1. **Enter your name** when prompted.
2. **Pick your hero** (1–5) or choose **6 – Random** to let the game decide.
3. **Pick your opponent's hero** the same way.
4. Each round shows two status panels — your opponent's (in red) on top, yours below — with HP/SP bars, current ATT/DEF values, and your available actions.
5. **Select an action** by number:
   - Action `1` — **Attack** (always free, costs 0 SP)
   - Action `2` — **Special ability** (costs 30 SP)
6. After your turn, the enemy AI takes its turn automatically.
7. The fight continues until one side reaches 0 HP.
8. After each match you are asked whether you want to **play again**.
9. At any prompt, enter **`q`** to quit / forfeit.

> **SP** (Skill Points) regenerate slightly each turn; if you can't afford a special move you must use the basic Attack.

## Characters

| # | Character | HP | SP | ATT | DEF | EVA | Special Ability | Special Effect |
|---|-----------|----|----|-----|-----|-----|-----------------|----------------|
| 1 | **Batman** | 100 | 100 | 70 | 30 | 5 | Get Mad (30 SP) | ATT +10, DEF −5 |
| 2 | **Superman** | 100 | 100 | 50 | 50 | 5 | Well-Placed Blow (30 SP) | High-damage strike with 80% hit chance |
| 3 | **Green Arrow** | 130 | 70 | 30 | 70 | 5 | Dig In (30 SP) | DEF +10 |
| 4 | **Flash** | 70 | 100 | 50 | 30 | 15 | Sidestep (30 SP) | EVA +5; counter-attacks when he dodges |
| 5 | **Martian** | 70 | 130 | 70 | 30 | 5 | Fireball (30 SP) | High-damage ranged attack |
| 6 | **Random** | — | — | — | — | — | Picks one of the above at random | — |

### Stat Guide

| Stat | Description |
|------|-------------|
| **HP** | Hit Points — reaches 0 = defeated |
| **SP** | Skill Points — spent to use special abilities |
| **ATT** | Attack — scales outgoing damage |
| **DEF** | Defence — reduces incoming damage |
| **EVA** | Evasion — percentage chance to dodge an incoming attack |

## Project Structure

```
JusticeLeague/
├── main.cpp            # Game loop, menus, and character selection
├── Character.cpp / .h  # Base class: stats, attack, damage, SP logic
├── Hero.cpp / .h       # Intermediate class inheriting from Character
├── Batman.cpp / .h     # Batman — high ATT, "Get Mad" ability
├── Superman.cpp / .h   # Superman — balanced, "Well-Placed Blow" ability
├── Green_Arrow.cpp / .h# Green Arrow — high HP/DEF, "Dig In" ability
├── Flash.cpp / .h      # Flash — high EVA, "Sidestep" + counter-attack
├── Martian.cpp / .h    # Martian — high SP, "Fireball" ability
├── Monster.cpp / .h    # Monster class (extends Character, reserved for future use)
├── Random.cpp / .h     # Utility: random number generation
└── Makefile            # Build configuration (g++, C++11, -Wall)
```

### Class Hierarchy

```
Character
├── Hero
│   ├── Batman
│   ├── Superman
│   ├── Green_Arrow
│   ├── Flash
│   └── Martian
└── Monster
```

## Contributors

| Name | Role |
|------|------|
| **Aniruddha Kulkarni** | Project lead — Character base class, Green Arrow, main game loop, Makefile |
| **Nikhilesh** | Batman class |
| **Aditya** | Superman class |
| **Sarthak** | Flash class |
| **Sanika** | Martian class |
