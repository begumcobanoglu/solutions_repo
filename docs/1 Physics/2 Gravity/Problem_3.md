# Problem 3
# 1. Physical and Mathematical Modeling

Understanding the motion of a freely released payload near Earth requires a rigorous application of classical mechanics and gravitation theory. This section outlines the foundational physical laws and modeling choices necessary for trajectory analysis.

---

## Governing Physical Laws

### Newton's Second Law

The net force acting on a body is equal to its mass times its acceleration:

$$
\vec{F}_{\text{net}} = m \vec{a}
$$

Where:
- $\vec{F}_{\text{net}}$ is the total force vector,
- $m$ is the mass of the payload,
- $\vec{a}$ is the acceleration vector.

### Newton's Law of Universal Gravitation

The gravitational force between Earth and the payload is given by:

$$
\vec{F}_g = -G \frac{M_E m}{r^2} \hat{r}
$$

Where:
- $G$ is the gravitational constant ($6.67430 \times 10^{-11}\,\text{m}^3\,\text{kg}^{-1}\,\text{s}^{-2}$),
- $M_E$ is the mass of Earth,
- $r$ is the distance from Earth's center to the payload,
- $\hat{r}$ is the unit vector pointing from the payload to the center of Earth.

By Newton's second law, this gives the equation of motion:

$$
m \vec{a} = -G \frac{M_E m}{r^2} \hat{r}
\quad \Rightarrow \quad
\vec{a} = -G \frac{M_E}{r^2} \hat{r}
$$

---

## Coordinate System

### Cartesian Coordinates

In 2D or 3D space, the position vector can be expressed as:

$$
\vec{r} = x \hat{i} + y \hat{j} \quad \text{(2D)}, \qquad \vec{r} = x \hat{i} + y \hat{j} + z \hat{k} \quad \text{(3D)}
$$

Acceleration components in Cartesian coordinates:

$$
\vec{a} = \ddot{x} \hat{i} + \ddot{y} \hat{j} \quad \text{(2D)}, \qquad \vec{a} = \ddot{x} \hat{i} + \ddot{y} \hat{j} + \ddot{z} \hat{k} \quad \text{(3D)}
$$

### Polar Coordinates (for planar motion)

In 2D polar coordinates $(r, \theta)$, the position and acceleration are:

$$
\vec{r} = r \hat{e}_r
$$

$$
\vec{a} = \left( \ddot{r} - r \dot{\theta}^2 \right) \hat{e}_r + \left( r \ddot{\theta} + 2 \dot{r} \dot{\theta} \right) \hat{e}_\theta
$$

---

## Additional Physical Effects

### Earth's Rotation

If the motion is observed from a rotating frame (e.g., Earth’s surface), fictitious forces must be included:

- **Coriolis Force:**
  $$
  \vec{F}_{\text{cor}} = -2m \left( \vec{\omega} \times \vec{v} \right)
  $$

- **Centrifugal Force:**
  $$
  \vec{F}_{\text{cen}} = -m \vec{\omega} \times \left( \vec{\omega} \times \vec{r} \right)
  $$

Where $\vec{\omega}$ is the angular velocity vector of Earth.

---

### Atmospheric Drag

Applicable for low-altitude releases. The drag force is modeled as:

$$
\vec{F}_d = -\frac{1}{2} C_D \rho A v^2 \hat{v}
$$

Where:
- $C_D$ is the drag coefficient,
- $\rho$ is atmospheric density,
- $A$ is the cross-sectional area,
- $v$ is the velocity magnitude,
- $\hat{v}$ is the unit vector in the direction of velocity.

Atmospheric density $\rho$ decreases exponentially with altitude:

$$
\rho(h) = \rho_0 \exp\left(-\frac{h}{H}\right)
$$

Where $H$ is the scale height (approx. 8.5 km near Earth).

---

### Earth's Oblateness (J2 Perturbation)

To model Earth’s non-spherical shape, include the $J_2$ perturbation:

$$
a_{J_2} = \frac{3}{2} J_2 \frac{GM_E R_E^2}{r^4} \left(1 - 5\sin^2\phi\right) \hat{r}
$$

Where:
- $J_2$ is the zonal harmonic coefficient,
- $R_E$ is Earth’s equatorial radius,
- $\phi$ is the latitude.

---

## Dimensionality of the Model

- **2D Analysis** is sufficient for idealized planar motion.
- **3D Analysis** is necessary when:
  - Inclination effects matter,
  - The trajectory involves polar or equatorial asymmetry,
  - Earth’s rotation or oblateness is included.

---

## Summary

To accurately model a payload's trajectory near Earth, one must choose an appropriate coordinate system, apply Newtonian mechanics, and consider secondary forces like atmospheric drag, Earth's rotation, and oblateness depending on the scenario's complexity and required precision.
# 2. Initial Conditions and Parameters

To simulate the motion of a freely released payload near Earth, precise specification of initial conditions and constants is essential. These values directly affect the resulting trajectory type (suborbital, orbital, or escape).

---

## Initial Position

In a three-dimensional model, the initial position $\vec{r}_0$ is defined in terms of:

- **Altitude above Earth's surface**: $h$
- **Latitude**: $\phi$
- **Longitude**: $\lambda$

The radial distance from Earth’s center is:

$$
r_0 = R_E + h
$$

Where $R_E$ is Earth's mean radius.

The Cartesian coordinates of the payload's position in Earth-Centered Earth-Fixed (ECEF) frame:

$$
\begin{aligned}
x_0 &= (R_E + h) \cos\phi \cos\lambda \\
y_0 &= (R_E + h) \cos\phi \sin\lambda \\
z_0 &= (R_E + h) \sin\phi
\end{aligned}
$$

---

## Initial Velocity

The initial velocity vector $\vec{v}_0$ is specified by:

- **Magnitude**: $v_0$
- **Elevation angle** (from local horizontal): $\theta$
- **Azimuth angle** (relative to geographic north): $\psi$

In local North-East-Down (NED) coordinates:

$$
\begin{aligned}
v_N &= v_0 \cos\theta \cos\psi \\
v_E &= v_0 \cos\theta \sin\psi \\
v_D &= -v_0 \sin\theta
\end{aligned}
$$

These can be transformed to ECEF or inertial frames depending on the simulation needs.

---

## Earth's Physical Parameters

### Mass of Earth

$$
M_E = 5.972 \times 10^{24}\,\text{kg}
$$

### Mean Radius of Earth

$$
R_E = 6.371 \times 10^6\,\text{m}
$$

### Gravitational Constant

$$
G = 6.67430 \times 10^{-11}\,\text{m}^3\,\text{kg}^{-1}\,\text{s}^{-2}
$$

### Standard Gravitational Parameter

Often denoted by $\mu$:

$$
\mu = G M_E = 3.986 \times 10^{14}\,\text{m}^3\,\text{s}^{-2}
$$

---

## Characteristic Velocities

### Escape Velocity

Escape velocity from a distance $r$ (typically $r = R_E + h$):

$$
v_{\text{esc}} = \sqrt{\frac{2 G M_E}{r}} = \sqrt{\frac{2 \mu}{r}}
$$

At the surface ($r = R_E$):

$$
v_{\text{esc, surface}} \approx 11.2\,\text{km/s}
$$

### Circular Orbital Velocity

For a circular orbit at radius $r$:

$$
v_{\text{orb}} = \sqrt{\frac{G M_E}{r}} = \sqrt{\frac{\mu}{r}}
$$

At low Earth orbit (LEO), say $h = 300\,\text{km}$:

$$
r = R_E + 300\,\text{km} \Rightarrow v_{\text{orb}} \approx 7.73\,\text{km/s}
$$

---

## Summary

A realistic simulation requires:

- Accurate geolocation for position and frame alignment
- Velocity decomposition into components aligned with the coordinate system
- Use of precise Earth constants
- Computation of reference velocities ($v_{\text{esc}}, v_{\text{orb}}$) to assess trajectory class

These initial parameters form the foundation for determining whether the payload will enter orbit, return to Earth, or escape its gravitational pull.
# 3. Classification of Trajectories

The classification of a payload’s trajectory under Earth's gravity depends fundamentally on **mechanical energy** and **angular momentum**. These physical quantities govern whether the object remains bound to Earth, escapes it, or reenters.

---

## Total Specific Mechanical Energy

The specific mechanical energy $\mathcal{E}$ (energy per unit mass) of a payload in a gravitational field is given by:

$$
\mathcal{E} = \frac{v^2}{2} - \frac{\mu}{r}
$$

Where:
- $v$ is the speed of the payload,
- $r$ is the radial distance from Earth's center,
- $\mu = GM_E$ is the standard gravitational parameter.

This total energy determines the **type of conic section** the trajectory traces:

---

### 1. **Elliptical Orbit** (Bound)

$$
\mathcal{E} < 0
$$

- The payload is gravitationally **bound** to Earth.
- The trajectory is an **ellipse**.
- The semi-major axis $a$ can be computed as:

$$
a = -\frac{\mu}{2\mathcal{E}}
$$

- Special case: **circular orbit** when eccentricity $e = 0$ and $v = v_{\text{orb}}$.

---

### 2. **Parabolic Trajectory** (Escape with Exact Energy)

$$
\mathcal{E} = 0
$$

- The payload has just enough energy to **escape** Earth's gravity.
- The trajectory is a **parabola**.
- This corresponds to moving at exactly **escape velocity**:

$$
v = v_{\text{esc}} = \sqrt{\frac{2\mu}{r}}
$$

---

### 3. **Hyperbolic Trajectory** (Unbound)

$$
\mathcal{E} > 0
$$

- The payload is **unbound** from Earth and escapes permanently.
- The trajectory is a **hyperbola**.
- Speed exceeds escape velocity:

$$
v > \sqrt{\frac{2\mu}{r}}
$$

---

### 4. **Suborbital or Reentry Trajectory**

This is a special case of **elliptical motion** where the perigee lies within Earth's surface, leading to impact:

- Still $\mathcal{E} < 0$, but trajectory intersects Earth.
- Common in reentry vehicles, ballistic missiles, and failed orbit insertions.

---

## Angular Momentum

Specific angular momentum $\vec{h}$ is defined as:

$$
\vec{h} = \vec{r} \times \vec{v}
$$

Its magnitude (scalar form in 2D motion):

$$
h = r v \sin\theta
$$

Where $\theta$ is the angle between $\vec{r}$ and $\vec{v}$.

Angular momentum is **conserved** in a central gravitational field:

$$
\frac{d\vec{h}}{dt} = 0
$$

It governs orbital geometry:

- Determines **orbital plane** in 3D motion
- Influences trajectory shape (with energy)

---

## Eccentricity and Orbit Shape

The **eccentricity** $e$ is a function of energy and angular momentum:

$$
e = \sqrt{1 + \frac{2 \mathcal{E} h^2}{\mu^2}}
$$

- $e = 0$: circular
- $0 < e < 1$: elliptical
- $e = 1$: parabolic
- $e > 1$: hyperbolic

---

## Summary Table

| Trajectory Type     | Specific Energy $\mathcal{E}$ | Eccentricity $e$ | Bound? |
|---------------------|-------------------------------|------------------|--------|
| Circular Orbit       | $< 0$                         | $0$              | Yes    |
| Elliptical Orbit     | $< 0$                         | $0 < e < 1$      | Yes    |
| Parabolic Escape     | $= 0$                         | $1$              | No     |
| Hyperbolic Escape    | $> 0$                         | $> 1$            | No     |
| Suborbital/Reentry   | $< 0$                         | $e$ varies       | Yes    |

---

## Conclusion

By analyzing the **mechanical energy** and **angular momentum** of a payload, we can classify its trajectory into one of several conic sections. This classification is essential for understanding whether the payload will orbit Earth, escape it, or return to the surface.


