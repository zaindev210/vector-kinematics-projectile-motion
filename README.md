# Vector Kinematics: 2D Projectile Motion & Ballistics Lab

> **Live Demo:** [zaindev210.github.io/vector-kinematics-projectile-motion](https://zaindev210.github.io/vector-kinematics-projectile-motion/)  
> **Live Demo:** `https://zaindev210.github.io/vector-kinematics-projectile-motion/`

An interactive computational physics simulation built in pure JavaScript and HTML5 Canvas for **ICS / FSc Physics** demonstrations. Developed to bridge textbook analytical kinematics with real-world numerical modeling, this lab visualizes 2D vector decomposition, quadratic aerodynamic drag, and planetary gravity environments in real time.

---

## Key Features

- **Custom 2D Vector Mathematics Engine (`Vector2D`):** Implements Euclidean vector operations (`add`, `sub`, `mult`, `mag`, `normalize`, `fromPolar`) without external physics libraries.
- **4th-Order Runge-Kutta (`RK4`) Numerical Solver:** Integrates non-linear equations of motion at a fixed time step ($\Delta t = 0.005\text{ s}$) with sub-step linear interpolation for exact ground-impact range and time of flight.
- **Analytical vs. Numerical Comparison:** Overlays the closed-form ideal vacuum parabola alongside the active numerical trajectory to highlight aerodynamic drag divergence.
- **Live Vector Decomposition HUD:** Renders scaled directional arrows on the projectile for resultant velocity ($\vec{v}$), orthogonal components ($v_x, v_y$), and net acceleration ($\vec{a} = \vec{g} + \vec{F}_d/m$).
- **Interactive Lab Controls:**
  - Quick angle presets ($30^\circ, 45^\circ, 60^\circ, 75^\circ$) to verify complementary range symmetry.
  - Planetary gravity presets (**Moon** $1.62\text{ m/s}^2$, **Mars** $3.72\text{ m/s}^2$, **Earth** $9.81\text{ m/s}^2$, **Jupiter** $24.79\text{ m/s}^2$).
  - Strobe motion markers every $0.25\text{ s}$, multi-launch trajectory history, and zoom/pan viewport navigation.

---

## Physics & Mathematical Formulation

### 1. Governing Differential Equations

The projectile state is modeled using position $\vec{r}(t) = (x, y)$ and velocity $\vec{v}(t) = (v_x, v_y)$ subject to gravity and quadratic air resistance:

$$\frac{d\vec{r}}{dt} = \vec{v}$$

$$\frac{d\vec{v}}{dt} = \vec{a} = \vec{g} - k \, |\vec{v}| \, \vec{v}$$

where $k = \frac{\rho C_d A}{2m}$ is the aerodynamic drag factor ($\text{m}^{-1}$).

### 2. Analytical Vacuum Reference ($k = 0, y_0 = 0$)

For ideal projectile motion without air resistance, the simulation computes closed-form benchmarks:

- **Time of Flight:** $T = \frac{2 v_0 \sin\theta}{g}$
- **Maximum Altitude:** $H_{\max} = \frac{v_0^2 \sin^2\theta}{2g}$
- **Horizontal Range:** $R = \frac{v_0^2 \sin(2\theta)}{g}$

---

## Getting Started

No build tools, bundlers, or package installations are required.

1. **Clone the repository:**
   ```bash
   git clone https://github.com/zaindev210/vector-kinematics-projectile-motion.git
   cd vector-kinematics-projectile-motion
   ```
2. **Run locally:**
   Open `index.html` directly in any modern web browser (Chrome, Edge, Firefox, Safari).

---

## Tech Stack

- **Core Physics & Math:** Vanilla JavaScript (ES6+ `Vector2D` & `RK4` Integrator)
- **Rendering:** HTML5 2D Canvas API with HiDPI (`devicePixelRatio`) scaling
- **UI & Styling:** Tailwind CSS & JetBrains Mono telemetry readouts

---

## License

This project is open-source under the **MIT License** — feel free to use it for classroom lectures, college technical symposiums, and physics labs.
