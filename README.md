# 🚦 MetaTraffic — Multi-Agent Reinforcement Learning for Smart Cities

MetaTraffic is a **multi-agent AI simulation** that models a fully automated traffic network within an intelligent city.  
Each vehicle acts as an autonomous reinforcement learning agent — learning to **drive safely, coordinate with others, and minimize travel time** across dynamically generated urban environments.

> **Core Idea:** Traffic doesn’t just follow rules — it *learns* them.

---

## 🌆 Inspiration

We were inspired by the vision of **self-managing cities** — intelligent urban ecosystems where traffic moves like a living organism.  
Today’s traffic systems are rigid, rule-based, and reactive.  
MetaTraffic explores how **autonomous AI agents** can transform chaos into order through **real-time communication, learning, and coordination**.

Our goal is to build a **smart urban traffic system** where all vehicles cooperate to create smooth, congestion-free flow while minimizing global travel time —  
bringing faster, safer, and more efficient mobility to intelligent human society.

---

## ⚙️ What It Does

MetaTraffic simulates a **multi-agent reinforcement learning (MARL)** system where:
- Each vehicle controls **acceleration, braking, and steering** autonomously.
- Agents learn to **avoid collisions**, **obey traffic lights**, and **adapt** to random city layouts.
- The city environment is **procedurally generated** each run with new:
  - Roads
  - Intersections
  - Traffic signals
  - Pedestrian paths

Together, hundreds of vehicle agents cooperate to:
- Minimize congestion  
- Avoid accidents  
- Maximize overall traffic efficiency  

---

## 🧠 Algorithm: MADDPG

We implement the **Multi-Agent Deep Deterministic Policy Gradient (MADDPG)** algorithm for continuous control tasks.

Each vehicle agent:
- Observes its **speed**, **distance to nearby vehicles**, **traffic-light states**, and **road layout**.
- Outputs **continuous actions** (acceleration, braking, steering).
- Learns through **joint training** with other agents in a decentralized fashion.

**Reward Function:**

$$
R = \alpha \cdot v - \beta \cdot d_{collision} - \gamma \cdot t_{delay}
$$

where:
- \( v \): vehicle’s forward velocity  
- \( d_{collision} \): collision distance penalty  
- \( t_{delay} \): traffic delay penalty  

**Inter-Agent Communication:**  
Vehicles share basic information (speed, direction, planned maneuvers) to improve coordination and flow.

After **600,000 epochs of training**, agents can:
- Drive autonomously without collisions  
- Obey traffic rules  
- Reach near the maximum legal road speed  
- Adapt to any randomly generated city map  

---

## 🧩 How We Built It

- **Procedural City Generator:** Builds new 3D urban maps each run with random roads, signals, and intersections.  
- **Continuous Sensory Input:** Each car perceives its own state and surroundings.  
- **Multi-Agent Reinforcement Learning:** Agents learn cooperative navigation policies.  
- **Collision Debugging System:** Visualizes collision sensors in real-time for both user and AI control.  
- **Inter-Agent Communication Layer:** Enables shared awareness for smoother coordination.  

---

## 🕹️ Web Demo

You can experience MetaTraffic interactively through our **web demo**: https://youtu.be/Xz2Sc6XNqUs.

### Features:
- Upload your own `map.svg` file.  
- **Green dots** represent car spawn points.  
- **Red dots** are destination goals.  
- **Bottom-left:** Control guide.  
- **Top-right:** Buttons to hide buildings or toggle collision debug mode.  
- Zoom, drag, and explore the city freely.

### Controls:
| Key / Action | Description |
|---------------|-------------|
| **W / S** | Accelerate / Brake |
| **A / D** | Steer Left / Right (auto-centers) |
| **Mouse Wheel** | Zoom in/out (centered on cursor) |
| **Left Mouse Button** | Drag to move the map |
| **B** | Toggle Buildings |
| **V** | Toggle Camera Follow |
| **C** | Enable / Disable Collision Debug |

When **collision debugging** is enabled, cars display sensor points.  
If a car collides with a building, it automatically stops and shows which sensor was triggered.

---

## 🧩 Manual vs AI Driving

In manual mode, users can directly control vehicles using the keyboard —  
but you’ll notice how easily collisions occur.  
After training, however, our AI agents drive smoothly and intelligently through the same city without human input.

This demonstrates how **reinforcement learning + communication** leads to emergent intelligent traffic behavior.

---

## 🏆 Results

- ✅ Stable, collision-free autonomous driving  
- ✅ Agents coordinate naturally without central control  
- ✅ Smooth, congestion-free traffic flow  
- ✅ Scalable to any randomly generated city layout  

---

## 🧪 Challenges

1. **Maintaining stability** in dynamic, randomly changing environments.  
2. **Balancing independence and coordination** among hundreds of agents.  
3. **Accurate collision prediction** and **signal synchronization**.  
4. Ensuring **realistic pedestrian-vehicle interactions**.

---

## 🚀 Future Work

Next, we aim to scale MetaTraffic into a **large-scale intelligent traffic infrastructure simulator**, integrating:
- Real city maps  
- Aerial mobility (drones)  
- IoT sensor data  

Our vision is to evolve MetaTraffic into a framework for **AI-managed urban transportation systems** —  
from cars to drones, from ground to sky.

> Ultimately, MetaTraffic will act as the **digital nervous system** of future cities — orchestrating movement across entire civilizations with precision and grace.

---

## 💾 Repository

You can view our code and demos on GitHub:  
👉 [https://github.com/TensorCraft/CityMap/tree/main/RL](https://github.com/TensorCraft/CityMap/tree/main/RL)

- Clone and run locally to visualize agent collaboration.  
- Watch trained agents navigate dynamic cities.  
- Try manual control to feel the difference between human and AI driving.

---

## 🧩 Tech Stack

- **Python 3.10+**  
- **PyTorch** – for RL training (MADDPG implementation)  
- **OpenAI Gym-like custom environment**  
- **Three.js / WebGL** – for 3D map rendering in browser demo  
- **Flask / FastAPI** – for connecting RL backend to web frontend  

---

## 📜 License

MIT License © 2025 TensorCraft

---

## 💡 Citation

If you use this project in research or demos:

```bibtex
@software{metatraffic_rl,
  title  = {MetaTraffic: Multi-Agent Reinforcement Learning for Intelligent Urban Traffic},
  author = {TensorCraft Team},
  year   = {2025},
  url    = {https://github.com/TensorCraft/CityMap}
}
