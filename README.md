# MetaTraffic — RL Module

MetaTraffic is a multi-agent AI simulation for intelligent urban traffic.  
This `RL/` module contains the reinforcement learning part that trains autonomous vehicle agents to drive safely, follow traffic rules, and optimize city-wide flow in procedurally generated maps.

> **Key idea:** every vehicle is an RL agent. Together they learn to coordinate, avoid collisions, and minimize global travel time in a dynamic city.

---

## 🚀 Features

- **Multi-Agent RL:** each car is an autonomous agent (MADDPG by default).  
- **Procedural City Generator:** new 3D road networks on every run (lanes, intersections, signals, pedestrians).  
- **Inter-Agent Communication:** share speed/intent for smoother, decentralized coordination.  
- **Collision Debugging:** visualize contact points; agents learn to avoid buildings/obstacles.  
- **Map Import:** upload your own `map.svg` and drive/evaluate on custom layouts.  
- **Web Demo Hooks:** optional UI to manually drive, zoom, toggle buildings, and enable debugging.

---

## ⚙️ Quick Start

### 1) Environment Setup

```bash
# Python 3.10+ is recommended
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

pip install -r requirements.txt
# For CUDA, install the right torch build from pytorch.org
