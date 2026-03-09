# Elevator Control System - CODESYS Project

An advanced industrial elevator control system developed in **CODESYS** for the *Control Systems Technologies* course made in University of Bologna. The project implements a modular architecture using the **GA (Generic Actuator)** approach, combining **SFC (Sequential Function Chart)** for logic flow and **ST (Structured Text)** for algorithmic calculations.

## 🏗 Project Architecture
The system is built on a "Handshake Policy" and is divided into three main Functional Blocks (GAs):

### 1. Motor GA
The core of the system, managing elevator movement and positioning:
- **Initialization:** Automated sequence to calibrate the elevator position (Descent -> LimitDown -> Ascent -> Ready).
- **Movement Logic:** Handles transitions between floors using "Ramp" and "Deck" sensors to manage acceleration and deceleration.
- **Fault Handling:** Integrated safety checks for sensor mismatches (e.g., detecting a ramp sensor when a deck sensor was expected).

### 2. Door GA
Controls the opening and closing cycles of the elevator doors:
- **Safety First:** Features a "Presence Sensor" logic. If an obstacle is detected during closing, the doors immediately reopen.
- **Handshake Protocol:** Communicates with the main policy to ensure doors are fully closed before the motor starts.

### 3. Leds GA (HMI & Call Management)
Manages the human-machine interface and the logic of floor requests:
- **FIFO & Priority Logic:** Uses an array-based system to store and prioritize calls from both internal panels and floor buttons.
- **Visual Feedback:** Controls LEDs for each floor to indicate active calls and current destination.

## 🛠 Technical Specifications
- **Programming Environment:** CODESYS V3.5
- **Languages:** SFC (Sequential Function Chart) and ST (Structured Text).
- **Control Strategy:** GA (Generic Actuator) approach with Do/Done handshake structure.
- **Logic:** FIFO (First In, First Out) call management with priority shifting.

## 👥 Authors & Collaborators
This project was co-developed by:

*   **Andrea Gallo** ([@andreagallo-dev](https://github.com/andreagallo-dev))
*   **Giorgio Ripani** ([@username_giorgio](https://github.com/giorgioripani))
*   **Francesco Tassi** ([@username_francesco](https://github.com/francesco-tassi))
*   **Leonardo Lodolini** ([@username_leonardo](https://github.com/sassuolo22)) 

---
*Project Date: January 2026*
*Course: Control Systems Technologies*
