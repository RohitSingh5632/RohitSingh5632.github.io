# RohitSingh5632.github.io
# Maze Game with Remote Control and AWS Integration  
**EEC 172 A03 - Embedded Systems**  
**Team Members:** Brandon Wong, Rohit Singh  
**Instructor:** Professor Soheil Ghiasi  

---

## 1. Project Description

This project is a full-stack embedded system implementation of an interactive **Maze Game**, combining hardware control, on-device display, and cloud-based logging.

- The game is displayed on an **OLED screen**, with a movable ball controlled via an **AT&T IR remote**.
- The player navigates the maze using directional inputs.
- Progress and win states are sent securely to **AWS IoT Core**, showcasing integration of local hardware with cloud infrastructure.

---

## 2. System Design

### 2.1 Functional Specifications

- Game starts upon receiving a “Start” command from the remote.
- Players control a ball using directional buttons.
- Collisions with maze walls are detected and blocked.
- Upon reaching the goal, a **"Win"** message is displayed.
- The game state (win or reset) is securely logged to **AWS via TLS**.
- A remote button can be used to reset the game.

We are planning to implement a second communication protocol (e.g., **SPI**) to expand functionality.

### 2.2 System Architecture





**Component Roles:**

- **IR Receiver + Remote:** User input system.
- **Microcontroller:** Controls game logic, input handling, display updates, and communication.
- **OLED Display:** Displays maze and game state.
- **WiFi Module (via CC3200):** Sends game data to AWS.
- **AWS IoT Core:** Stores and visualizes player data over secure TLS connection.

---

## 3. Implementation Goals

### ✅ Minimal Goal
- Use IR remote to control a ball on the OLED screen.
- Detect and block collisions with walls.

### ✅ Core Goal
- Display a win message upon successful navigation.
- Log the win state to **AWS IoT** securely using TLS.

### 🌟 Stretch Goals
- Implement **dynamic maze generation**.
- Build a **web dashboard** to visualize game statistics.

---

## 4. Bill of Materials

| Component             | Quantity | Cost | Vendor     |
|-----------------------|----------|------|------------|
| CC3200 Dev Board      | 1        | Free | UC Davis   |
| OLED Display (SSD1306)| 1        | Free | UC Davis   |
| IR Receiver Module    | 1        | Free | UC Davis   |
| AT&T Remote Control   | 1        | Free | UC Davis   |
| Jumper Wires          | 1 pack   | Free | UC Davis   |
| Breadboard            | 1        | Free | UC Davis   |
| TLS Certificate Setup | -        | Free | AWS IoT    |

---

## 🔧 Technologies Used

- **C/C++** (embedded programming)
- **IR Protocols**
- **AWS IoT Core**
- **TLS (Transport Layer Security)**
- **I2C / SPI** (planned)

---

## 🚀 Future Plans

- Integrate an additional protocol like SPI for inter-device communication.
- Build a front-end dashboard for analytics.
- Add game difficulty levels and time tracking.

---

> Built with ❤️ by Brandon Wong & Rohit Singh  
> UC Davis — Spring 2025
