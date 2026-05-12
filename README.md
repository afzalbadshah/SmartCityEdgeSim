# SmartCityEdgeSim

**SmartCityEdgeSim** is a Python-based simulation framework for AI-driven task offloading in smart city edge computing environments. It models mobile IoT devices, MEC servers, Metro Edge infrastructure, and Cloud resources to evaluate intelligent scheduling decisions under dynamic mobility, congestion, and resource constraints.

## About

SmartCityEdgeSim provides an integrated simulation environment for studying mobility-aware and resource-aware task offloading across multi-tier smart city infrastructure. The framework supports local MEC execution, collaborative MEC offloading, Metro Edge execution, and Cloud fallback. It includes mobility modeling, workload generation, resource utilization tracking, task-level metric logging, live visualization, and a PPO-inspired reinforcement learning scheduler.

## Main Capabilities

- Mobility-aware smart city task offloading
- Multi-tier execution across MEC, Metro Edge, and Cloud
- MEC collaboration for overloaded local edge nodes
- PPO-inspired actor–critic scheduling model
- Resource-aware decision making based on CPU, memory, congestion, delay, cost, and energy
- Random waypoint mobility model for mobile IoT devices
- Handover tracking and wireless access point association
- Live Tkinter-based visualization of devices, servers, and offloading links
- CSV-based metric logging and training plots

## System Architecture

The simulator is organized into the following modules:

```text
SmartCityEdgeSim/
├── applications/          # Main entry point
├── config/                # Simulation parameters and metric functions
├── core/                  # Simulation loop and result reporting
├── entities/              # Task and server models
├── live/                  # Live visualization interface and assets
├── mobility/              # Mobility and handover management
├── scheduler/             # Scheduling algorithms and PPO components
├── workload/              # Task workload generation
├── results/               # Runtime logs and generated plots
├── ppo_Metro_model.pth    # Saved PPO model checkpoint
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation
```

## Execution Tiers

SmartCityEdgeSim supports four main execution choices:

1. **Local MEC execution** for low-latency nearby processing.
2. **Collaborative MEC execution** when the serving MEC is overloaded.
3. **Metro Edge execution** for regional processing with more capacity than MEC.
4. **Cloud execution** as a high-capacity fallback tier.

## Scheduler

The scheduler first attempts feasible local MEC execution. If the serving MEC cannot process the task, the PPO-based scheduler selects among collaborative MEC, Metro Edge, and Cloud. The scheduler uses state information such as server utilization, congestion, propagation delay, transmission cost, processing cost, energy consumption, and distance-based feasibility.

## Metrics Logged

The simulator records detailed task and system-level metrics, including:

- Task execution tier
- CPU, memory, and storage utilization
- Transmission delay
- Propagation delay
- Processing cost
- Transmission cost
- Energy consumption
- Congestion level
- Signal strength
- Wireless access point
- Handover count and handover delay
- MEC collaboration ratio
- MEC collaboration distance
- Failed task count

## Installation

Create a Python virtual environment:

```bash
python -m venv .venv
```

Activate it:

```bash
# Windows
.venv\Scripts\activate

# Linux/macOS
source .venv/bin/activate
```

Install dependencies:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

## Run the Simulator

```bash
python -m applications.MainApplication
```

The live map interface will open, allowing the simulation environment to be displayed visually.

## GitHub Short Description

AI-driven smart city edge simulator for mobility-aware task offloading across MEC, collaborative MEC, Metro Edge, and Cloud infrastructure.

## Suggested GitHub Topics

```text
edge-computing
mec
smart-city
task-offloading
reinforcement-learning
ppo
mobility-aware
cloud-computing
iot-simulation
metro-edge
resource-management
python-simulator
```

## Citation

If you use SmartCityEdgeSim in academic work, please cite the related paper or repository release when available.

## Author

Dr. Afzal Badshah  
Department of Software Engineering, University of Sargodha  
Website: https://afzalbadshah.com/
