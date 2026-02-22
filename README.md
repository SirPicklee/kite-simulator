# Kite Simulator
**Full Physics Kite Design and Simulation Tool**

An Electron-based desktop application for kite aerodynamics analysis, design optimization, and flight simulation.

---

## Overview

Kite Simulator implements a full aerodynamic physics engine to analyze kite behavior under various wind and design conditions. It provides real-time force calculations, stability analysis, flight trajectory estimation, and comprehensive visualization tools — all within an interactive GUI.

---

## Supported Kite Types

| Type | Description |
|------|-------------|
| Diamond | Classic diamond kite — area factor 0.5, CP at 75% height |
| Delta | Delta wing kite — area factor 0.5, CP at 67% height |
| Box | Box kite — effective area factor 2.0, CP at 50% height |
| Fighter | Fighter kite — area factor 0.4, CP at 75% height |

---

## Features

### Physics Engine
- Thin airfoil lift coefficient: CL = 2*pi*alpha / (1 + 2*alpha/AR)
- Drag coefficient: CD = 1.28*sin(alpha) + CL^2 / (0.7*pi*AR)
- Aspect ratio calculation from kite geometry
- Aerodynamic force computation (lift, drag) using air density and wind speed
- Tail drag modeling (ribbon, streamer, bow tail types)
- Center of gravity (CG) and center of pressure (CP) calculation
- Torque balance analysis for stability determination
- Line tension and bridle angle computation
- Flight height and horizontal distance estimation

### Stability Analysis
- Torque equilibrium check
- Tail stability bonus factor
- Stable/unstable flight condition detection
- Stability sweep over angle of attack (0 to 45 degrees)

### Wind Simulation
- Wind speed range: 5 to 80 mph
- Wind profiles: Steady, Gusts, Turbulent, Increasing, Decreasing
- Real-time wind bar indicator with animated flow effect

### Visualization
- Real-time kite canvas rendering (side view and front view)
- Force vector display (lift, drag, weight, tension)
- Torque vs angle of attack chart
- Force breakdown chart
- Stability map chart
- Wind envelope chart
- Mini and full-size chart modes with tab switching

### Presets
- 4 built-in design presets: Beginner, Sport, Light Wind, Fighter
- Instant parameter loading

### Report Generation
- PDF report via jsPDF
- Includes: design parameters, physics results, stability analysis, chart images

---

## Requirements

```
Node.js 16+
Electron
```

Install dependencies:

```
npm install
```

---

## Running

```
npm start
```

Or use the compiled executable in the dist folder.

---

## Project Structure

```
kite-simulator/
├── index.html       (UI + physics engine + charts)
├── main.js          (Electron main process)
├── package.json
└── dist/            (compiled executables)
```

---

## Physics Reference

Lift and drag are computed using standard aerodynamic relations:

- Lift: L = 0.5 * CL * rho * V^2 * A
- Drag: D = 0.5 * CD * rho * V^2 * A
- CL from thin airfoil theory with finite aspect ratio correction (Prandtl lifting line)
- CD includes flat plate pressure drag and induced drag
- Stability criterion: |torque| < 5.0 lb*in AND net lift > 0

---

## Contact and Collaboration

Open-source project, open for collaboration.

GitHub: https://github.com/SirPicklee/kite-simulator

---

## License

MIT License
