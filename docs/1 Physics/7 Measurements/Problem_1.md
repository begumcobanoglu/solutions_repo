# Problem 1
# 1. Theoretical Framework

## Objective

To derive the mathematical relationship between the period of oscillation $T$ of a simple pendulum and the local gravitational acceleration $g$.

---

## Ideal Simple Pendulum

An **ideal simple pendulum** consists of:
- A point mass (bob) suspended by a **massless, inextensible string**
- Oscillating in a **vertical plane** under the influence of gravity
- No air resistance or friction at the pivot
- **Small-angle approximation**: angular displacement $\theta$ (in radians) is small enough that $\sin\theta \approx \theta$

---

## Derivation of the Pendulum Period

The angular equation of motion for a simple pendulum is:

$$
\frac{d^2\theta}{dt^2} + \frac{g}{L}\sin\theta = 0
$$

This is a nonlinear second-order differential equation. However, for small angles ($\theta \ll 1$ rad), we can apply the approximation:

$$
\sin\theta \approx \theta
$$

This simplifies the equation to a linear form:

$$
\frac{d^2\theta}{dt^2} + \frac{g}{L}\theta = 0
$$

This is the standard form of the simple harmonic oscillator (SHO):

$$
\frac{d^2x}{dt^2} + \omega^2 x = 0
$$

By comparison, the **angular frequency** $\omega$ is:

$$
\omega = \sqrt{\frac{g}{L}}
$$

The **period** $T$ of the oscillation is related to angular frequency by:

$$
T = \frac{2\pi}{\omega}
$$

Substituting the expression for $\omega$:

$$
T = 2\pi\sqrt{\frac{L}{g}}
$$

---

## Final Formula

The period of a simple pendulum is:

$$
T = 2\pi \sqrt{\frac{L}{g}}
$$

Where:
- $T$ is the time for one complete oscillation (s)
- $L$ is the length of the pendulum (m)
- $g$ is the gravitational acceleration (m/s²)

---

## Assumptions

To derive this expression, the following assumptions are made:

1. **Point Mass**: The pendulum bob is treated as a point mass; rotational inertia is ignored.
2. **Massless String**: The string or rod has negligible mass and does not stretch.
3. **Frictionless Pivot**: The pivot point is ideal and does not resist motion.
4. **Small-Angle Approximation**: Valid for angular displacements $\theta < 15^\circ$ (typically).
5. **No Air Resistance**: The effects of drag or damping are neglected.

---

## Implications

Under these assumptions, the pendulum behaves as an ideal simple harmonic oscillator, and the period depends **only on the length $L$** of the pendulum and the **gravitational field $g$**, not on mass or amplitude (for small angles).

This relationship enables precise experimental determination of $g$ through period measurements.

---
# 2. Experimental Design

## Objective

To design an experiment capable of accurately determining the local gravitational acceleration $g$ by measuring the oscillation period $T$ of a simple pendulum.

---

## 2.1 Determining Pendulum Length $L$

### Definition

The length $L$ of a simple pendulum is defined as the distance from the **pivot point** to the **center of mass** of the pendulum bob:

$$
L = l_{\text{string}} + r_{\text{cm}}
$$

Where:
- $l_{\text{string}}$ is the measured length of the string or rod
- $r_{\text{cm}}$ is the distance from the attachment point to the center of mass of the bob

### Measurement Techniques

- Use a **meter ruler** or **measuring tape** with millimeter precision.
- Measure from the fixed pivot to the **center of mass** of the bob (typically the geometric center if spherical).
- Ensure the string is **taut and straight** during measurement.
- Record uncertainty in $L$, typically $\pm 0.5 \ \text{mm}$ to $\pm 1 \ \text{mm}$.

---

## 2.2 Measuring Oscillation Period $T$

### Method Options

1. **Manual Stopwatch Timing**
   - Time a large number of complete oscillations (e.g., 20 or 30)
   - Divide the total time by the number of oscillations:
     $$
     T = \frac{t_{\text{total}}}{N}
     $$
   - Use a stopwatch with precision of at least $0.01 \ \text{s}$

2. **Photogate Timer**
   - Automatically detect pendulum passing through a reference point
   - Provides higher precision and minimizes human error

3. **Video Analysis (High Frame Rate)**
   - Record oscillation with a camera
   - Analyze motion frame-by-frame to measure period

---

## 2.3 Repetition for Accuracy

To reduce **random errors**, the experiment should be repeated:

- Time at least **$N = 20$ to $50$** oscillations to average out reaction delays:
  $$
  T = \frac{t_{\text{total}}}{N}
  $$

- Conduct **at least 3 full trials** at the same length $L$
- Average the periods to find a more precise estimate:
  $$
  \bar{T} = \frac{T_1 + T_2 + T_3}{3}
  $$

---

## 2.4 Angle of Release

- Keep angular displacement $\theta$ **below $15^\circ$** to satisfy the small-angle approximation.
- Use a **protractor** or angular guide to maintain consistency.
- Avoid pushing the pendulum — release it gently from rest.

---

## 2.5 Equipment Checklist

- Rigid support stand
- Light, inextensible string
- Dense spherical bob
- Meter scale or tape
- Stopwatch (or photogate system)
- Protractor
- Clamp and pivot

---

## Summary

An accurate measurement of $g$ via a pendulum requires:
- Precise length measurement from pivot to bob center
- Timing many oscillations to minimize human error
- Repeated trials and small angular displacements

By optimizing these factors, the experiment can yield a high-fidelity value of gravitational acceleration with quantified uncertainty.

---
# 3. Apparatus Setup

## Objective

To establish a physically stable and reproducible experimental setup for pendulum motion that minimizes systematic error and maximizes accuracy in measuring the period $T$.

---

## 3.1 Selection of Materials

### **String**

- **Type**: Thin, **non-elastic**, low-mass thread or fishing line
- **Purpose**: To approximate an **ideal massless string**
- **Length**: Varies based on lab space, typically 0.5 m – 1.5 m
- **Requirements**:
  - Minimal stretch under tension
  - Uniform diameter to avoid bias in swing plane

### **Bob (Mass)**

- **Type**: Dense, **symmetric** solid object (e.g., a steel or brass sphere)
- **Shape**: Spherical to ensure **uniform center of mass**
- **Mass**: Sufficient to reduce air resistance effects but not so heavy as to introduce safety issues
- **Attachment**: Secure, centered, and aligned with the string to avoid torque

### **Support Stand**

- **Type**: Laboratory-grade **retort stand** or **tripod** with a horizontal rigid bar
- **Pivot**: Low-friction hook, clamp, or nail for minimal energy loss
- **Requirements**:
  - Must not wobble or shift during oscillation
  - Height must allow the bob to swing freely without touching any surfaces

---

## 3.2 Stability Considerations

- Secure the support stand to a **non-vibrating, level surface**
- If necessary, add **weights or clamps** at the base for stability
- Ensure that the pendulum swings in a **single vertical plane** by:
  - Aligning the release angle
  - Avoiding sideward components at release

---

## 3.3 Release Mechanism

To minimize initial energy input and avoid systematic error, develop a **consistent release method**:

### Manual Release (Basic)

- Hold bob at the desired angle using a **rigid object (e.g., ruler)** or **thread**
- Gently release without applying force
- Use a **reference protractor** to set and confirm the angle

### Thread Burn or Cut Method (Advanced)

- Hold bob in place with a taut horizontal thread
- Cut or burn the thread for a **near-perfect zero-force release**

### Mechanical Clamp Release (Precision)

- Use a spring-loaded or latch-based clamp to hold and release the bob at a set position
- Provides consistency across multiple trials

---

## 3.4 Safety Considerations

- Keep observers clear of the pendulum path
- Ensure the string is not frayed or damaged
- Use safety goggles if flame or cutting method is used

---

## Diagram (optional in rendered markdown)

If supported by your markdown environment, include a labeled diagram to illustrate the apparatus components and geometry.

---

## Summary

A successful pendulum setup depends on:

- Using **non-elastic string** and a **symmetric bob**
- Ensuring a **rigid, stable support** structure
- Implementing a **zero-force release mechanism** for repeatability
- Maintaining **alignment and small angle displacement** for theoretical consistency

Proper setup minimizes experimental uncertainty and ensures reproducibility of the measured period $T$.

---


