# 🧪 Mixing & Heating Tank System (TIA Portal, S7-1500)

A complete automation project simulating a heated mixing tank controlled with Siemens TIA Portal (S7-1500) and visualized with WinCC HMI. The simulation is tested in PLCSIM Advanced and meets safety requirements based on EN 60204-1.

---

## 📌 Features

- 💧 Fill control using two level sensors (Low, High)
- 🔥 Heating control with temperature sensor and setpoint
- ⚙️ Mixer motor operation during heating cycle
- 🚪 Automatic outlet valve control after mixing
- 🧠 Intelligent alarm system for overheat, overfill
- 👨‍💻 HMI with:
  - Start / Stop buttons
  - Tank visualization
  - Real-time temperature & level
  - Alarm messages

---

## 🧾 PLC Components

| Component            | Description                          |
|----------------------|--------------------------------------|
| S7-1500 CPU          | Central logic unit                   |
| 2x DI Sensors        | Level (Low, High)                    |
| 1x AI Sensor         | Temperature                          |
| 2x Pumps (DO)        | Water Inlet                          |
| 1x Heater (DO)       | Heating Coil                         |
| 1x Mixer Motor (DO)  | Mixer during heat cycle              |
| 1x Outlet Valve (DO) | Opens when process ends              |

---

## 🧠 Logic Flow

1. Press **Start**
2. Pump 1 fills tank until **Low Level Sensor = TRUE**
3. Pump 2 fills tank until **High Level Sensor = TRUE**
4. Start Mixer and Heating
5. When **Temperature >= Setpoint**, run mixer 30s more
6. Open outlet valve, then reset system

---

## 🔐 Safety Functions (EN 60204-1)

- Overtemperature interlock disables heater
- Manual Stop button overrides all actions
- Alarm messages logged in HMI

---

## 🖥️ HMI Layout

- Tank with fill animation
- Thermometer for real-time temperature
- Buttons: Start, Stop, Reset
- Alarm screen: Overheat, Sensor Fault, etc.

---

## 🧪 Simulation

Tested in **PLCSIM Advanced** with all sensors simulated via Watch Tables and Signal Generators.

---

## 📂 File Structure

See folders:
- `/PLC_Logic/`: SPS logic in ST & LAD (text-based)
- `/HMI_Screens/`: Layout sketch and tags
- `/Documentation/`: Norm compliance & control documentation

---

## 📜 License

MIT License – free for use and modification.
