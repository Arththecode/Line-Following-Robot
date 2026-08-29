# Internet-Controlled Autonomous Robot

> **Developing a robot from an analogue line-following system into an internet-connected platform with my own collision-avoidance system.**

This project is an ongoing robotics and electronics project that started with the design and construction of an analogue line-following robot.

The long-term goal is to develop the robot into a more capable autonomous system by introducing an **ESP32**, enabling control from a phone across the internet, and eventually designing and implementing **my own collision-avoidance system**.

Rather than building the final system all at once, I am developing it progressively. Each stage introduces a new part of the system and provides a foundation for the next.

---

## 🚀 Project Goal

The main goal of this project is to develop and implement **my own collision-avoidance system** rather than relying solely on a pre-built robotics platform or a simple demonstration circuit.

The intended progression is:

```text
Analogue Line-Following Robot
              ↓
       ESP32 Integration
              ↓
   Internet / Phone Control
              ↓
      Obstacle Detection
              ↓
      Obstacle Avoidance
              ↓
   My Own Collision-Avoidance
            System
```

The final system is intended to combine **electronics, sensing, software, communications and mechanical control** into one integrated robot.

---

# 🤖 Project Phase 1

## V2 Analogue Line-Following Robot

The current version of the robot is a physical prototype based around analogue electronics.

It uses:

* LDRs for line detection
* LM393 dual comparator
* NPN transistors
* DC gear motors
* Lego wheels
* LEDs for circuit indication
* Breadboard electronics
* A custom mechanical structure

The LDR sensing circuit detects differences in reflected light from the track. These differences produce different voltages, which are compared using the LM393 comparator.

The comparator outputs are then used to control the appropriate motor side, allowing the robot to correct its position and follow the line.

The detailed report explains the sensing circuit, comparator circuit and motor-control design in more detail.

---

# 🎥 Robot Demonstration

**Current V2 demonstration:**

> Add the final robot demonstration video here.

The demonstration shows the current physical prototype and its line-following system.

---

# 📸 Build Gallery

## Final V2 Robot

![Final V2 robot](images/robot-v2.jpg)

## Electronics

![Electronics](images/circuit.jpg)

## Mechanical Construction

![Mechanical construction](images/mechanical.jpg)

## Testing

![Robot testing](images/testing.jpg)

---

# 🔧 Development Process

This project has been developed through physical experimentation and iteration.

The first version of the robot revealed several problems that were not obvious from the theoretical design.

## V1 — Initial Prototype

The first mechanical design used a lunchbox as the robot body, with the motors mounted underneath using a torch body and zip ties.

During testing, the motors could move within their mounts. This changed the wheel alignment and affected the robot's movement.

A caster wheel was also introduced to support the front of the robot, but the wheel was too loose and caused instability.

These problems led to a complete redesign of the movement system.

## V2 — Mechanical Redesign

For V2, the caster wheel was removed and a bamboo support was attached underneath the robot body.

The motors were carefully aligned and secured to this support.

This prevented the motors from moving and significantly improved the rigidity and consistency of the movement system.

### V1 → V2

| Area                 | V1                            | V2              |
| -------------------- | ----------------------------- | --------------- |
| Motor mounting       | Motors could move             | Rigid support   |
| Wheel alignment      | Could change during operation | Fixed           |
| Front support        | Loose caster                  | Caster removed  |
| Mechanical stability | Unstable                      | Improved        |
| Movement consistency | Inconsistent                  | More consistent |

---

# ⚡ Electronics

The sensing system uses two LDRs positioned to detect the contrast between the track and its surrounding surface.

When one sensor moves over the black line, the reduction in reflected light changes the resistance of the LDR and therefore changes the voltage produced by the sensing circuit.

The two sensor voltages are compared using the LM393.

The comparator then determines which side of the robot has moved over the line and activates the corresponding motor-control circuit.

One of the challenges was working with the LM393's open-collector outputs while using the NPN transistors available to me.

Instead of replacing the transistors, I adapted the circuit by introducing an additional LED stage that allowed the NPN transistors to be switched successfully.

---

# 🧠 Engineering Approach

A major part of the project has been learning through **iteration**.

The aim has not been simply to produce a robot that works once. Instead, I have been trying to understand why problems occur and then modify the design to solve them.

For example:

**Problem → Investigation → Design change → Testing → Improved design**

The V1 mechanical problems demonstrated how important physical construction and alignment are to the performance of an electronic control system.

The V2 redesign was therefore not just a cosmetic change; it was a response to problems identified during testing.

---

# 🌐 Next Stage — ESP32

The next stage is to introduce an **ESP32** into the robot.

The purpose of this stage is to move beyond the current analogue-only system and create a connected robotic platform.

The intended system will allow me to control the robot from a phone **across the internet**.

This stage will involve developing:

* ESP32 integration
* Motor control through the ESP32
* Internet connectivity
* Communication between the phone and robot
* A phone-based control interface
* Integration between the new digital system and the existing hardware

This will provide the platform required for the later autonomous features.

---

# 📡 Internet-Controlled Robot

The intended control architecture is:

```text
             PHONE
               │
               │ Internet
               ↓
        ┌───────────────┐
        │ Communication │
        │    System     │
        └───────┬───────┘
                │
                ↓
             ESP32
                │
                ↓
         Motor Control
                │
                ↓
             Motors
```

The exact communication architecture will be developed as part of the ESP32 stage.

---

# 🚧 Future Development

## Stage 1 — Analogue Line Following

**Status: ✅ Prototype completed**

Development of the original analogue line-following robot, including the sensing circuit, comparator circuit, transistor switching and mechanical system.

---

## Stage 2 — ESP32 Integration

**Status: 🚧 Next stage**

Integrate the ESP32 and develop phone-based control across the internet.

---

## Stage 3 — Obstacle Detection

**Status: 🔜 Planned**

Introduce sensors capable of detecting obstacles around the robot.

The ESP32 will provide the processing required to interpret the sensor information and integrate it with the robot's control system.

---

## Stage 4 — Obstacle Avoidance

**Status: 🔜 Planned**

Develop the robot's ability to respond to detected obstacles instead of simply continuing along its current path.

This stage will build the foundations for the final collision-avoidance system.

---

## Stage 5 — My Own Collision-Avoidance System

**Status: 🔭 Long-term goal**

The ultimate goal of the project is to design and implement **my own collision-avoidance system**.

Rather than treating collision avoidance as a single sensor or component, I want to develop the system as an integrated part of the robot.

The system will combine:

* Environmental sensing
* Decision-making
* Motor control
* ESP32 processing
* The existing mechanical platform
* Remote and autonomous operation

The intention is for the robot to be able to detect potential collisions and make its own decisions about how to respond.

---

# 📈 Project Roadmap

```text
                    CURRENT
                       │
                       ▼
        ┌──────────────────────────┐
        │ V2 Analogue Line Follower│
        └────────────┬─────────────┘
                     │
                     ▼
        ┌──────────────────────────┐
        │      ESP32 Integration   │
        └────────────┬─────────────┘
                     │
                     ▼
        ┌──────────────────────────┐
        │  Phone / Internet Control│
        └────────────┬─────────────┘
                     │
                     ▼
        ┌──────────────────────────┐
        │    Obstacle Detection    │
        └────────────┬─────────────┘
                     │
                     ▼
        ┌──────────────────────────┐
        │    Obstacle Avoidance    │
        └────────────┬─────────────┘
                     │
                     ▼
        ┌──────────────────────────┐
        │  MY COLLISION-AVOIDANCE  │
        │          SYSTEM          │
        └──────────────────────────┘
```

---

# 📚 Full Engineering Write-Up

The original project is documented in a detailed engineering report covering the design decisions, electronics, sensing circuit, comparator system, motors, mechanical construction, V1/V2 development and lessons learned.

**[📄 Read the full engineering write-up](docs/The-Line-Following-Robot.pdf)**

The report represents the development of the analogue V1/V2 prototype. The ESP32, internet control and collision-avoidance stages are the next phase of the project.

---

# 🛠️ Future Improvements to the Existing Hardware

Although the project is moving towards ESP32 integration, there are also several improvements identified from the current prototype.

These include:

* Designing a custom PCB
* Creating a proper motor mounting bracket
* Replacing the permanent wheel-to-motor connection with a removable coupler
* Improving sensor positioning
* Reducing exposed wiring
* Making the body more compact
* Improving sensor calibration

These improvements were identified during the development of the current prototype.

---

# 📂 Repository Structure

```text
line-following-robot/
│
├── README.md
│
├── docs/
│   └── The-Line-Following-Robot.pdf
│
├── images/
│   ├── robot-v1.jpg
│   ├── robot-v2.jpg
│   ├── circuit.jpg
│   ├── sensors.jpg
│   ├── mechanical.jpg
│   └── testing.jpg
│
├── videos/
│   ├── robot-v1-test.mp4
│   └── robot-v2-demo.mp4
│
└── LICENSE
```

As the project develops, the repository will also contain the ESP32 software, control interface and documentation for the autonomous systems.

---

# 🎓 Project Context

This project was started during **Year 12** and is continuing into **Year 13**.

The purpose of documenting it on GitHub is to record the development of the robot over time, including successful designs, failed approaches, testing, redesigns and future development.

The project is therefore intended to be a **continuously developing engineering project**, rather than a finished one-off build.

---

# 📌 Current Status

| Component                      | Status            |
| ------------------------------ | ----------------- |
| Analogue line-following system | ✅ Completed       |
| V2 mechanical redesign         | ✅ Completed       |
| ESP32 integration              | 🚧 Next           |
| Phone control                  | 🔜 Planned        |
| Internet control               | 🔜 Planned        |
| Obstacle detection             | 🔜 Planned        |
| Obstacle avoidance             | 🔜 Planned        |
| Own collision-avoidance system | 🔭 Long-term goal |

---

## Author

**Arth Suthar**

Year 13 student developing an ongoing electronics, robotics and embedded-systems project.

