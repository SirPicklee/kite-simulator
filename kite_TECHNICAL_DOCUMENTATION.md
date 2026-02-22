# Kite Simulator — Technical Documentation

**Version:** 1.0.0

---

## Physics Engine

Lift and drag forces are calculated using standard aerodynamic relations. Lift coefficient is derived from thin airfoil theory with finite aspect ratio correction. Drag includes flat plate pressure drag and induced drag components.

Each kite type has a different effective area factor and center of pressure position, reflecting their physical geometry.

Stability is determined by torque balance about the bridle point. The kite is considered stable when the net torque is within acceptable limits and lift exceeds total weight. Tail length increases stability through a damping correction factor.

Flight height and horizontal distance are estimated from line length and bridle angle, with correction factors accounting for line sag.

---

## Kite Types

- **Diamond** — Classic geometry, balanced lift and drag
- **Delta** — Lower center of pressure, stable in light wind
- **Box** — High effective area, strong lift in low wind
- **Fighter** — Small area, agile, responsive in high wind

---

## Wind Profiles

Steady, gusts, turbulent, increasing, and decreasing wind profiles are simulated to test kite behavior across different conditions.

---

## Technology Stack

| Component | Technology |
|-----------|-----------|
| Desktop shell | Electron |
| UI | HTML5 + CSS3 |
| Physics | Vanilla JavaScript |
| Charts | Chart.js |
| PDF export | jsPDF |
