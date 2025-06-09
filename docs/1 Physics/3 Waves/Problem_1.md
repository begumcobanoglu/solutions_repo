# Problem 1
# Interference Patterns on a Water Surface
## 1. Mathematical Representation of Single Wave Source

The disturbance on a water surface caused by a point source emitting circular waves can be mathematically described using a **wave equation** for a single disturbance.

### General Form of the Wave Equation

The displacement of the water surface at a point $\vec{r}$ and time $t$ is given by:

$$
\eta(\vec{r}, t) = A \cos(kr - \omega t + \phi)
$$

Where:

- $\eta(\vec{r}, t)$: Displacement function — describes the vertical displacement of the water at position $\vec{r}$ and time $t$.
- $A$: Amplitude of the wave — the maximum displacement from the equilibrium position.
- $k$: Wave number — describes the spatial frequency of the wave.
- $r$: Distance from the wave source to the point $\vec{r}$.
- $\omega$: Angular frequency — describes how rapidly the wave oscillates in time.
- $\phi$: Initial phase — phase offset at $t = 0$ and $r = 0$.

---

### Definitions of Wave Parameters

#### **Amplitude ($A$)**

The amplitude is a scalar representing the maximum displacement of the wave from its mean level. It is directly proportional to the energy carried by the wave.

#### **Wave Number ($k$)**

The wave number $k$ relates to the wavelength $\lambda$ by:

$$
k = \frac{2\pi}{\lambda}
$$

Where:

- $\lambda$: Wavelength — the distance between two successive points in phase (e.g., two adjacent crests).

#### **Angular Frequency ($\omega$)**

The angular frequency is defined as:

$$
\omega = 2\pi f
$$

Where:

- $f$: Frequency — the number of oscillations per second.

#### **Radial Distance ($r$)**

The distance $r$ is the Euclidean distance from the wave source (at point $\vec{r}_0$) to the observation point $\vec{r}$:

$$
r = \|\vec{r} - \vec{r}_0\| = \sqrt{(x - x_0)^2 + (y - y_0)^2}
$$

#### **Initial Phase ($\phi$)**

The initial phase $\phi$ determines the wave's starting position at time $t = 0$. It introduces a phase shift, affecting the position of the peaks and troughs.

---

### Summary Equation

Combining all the above components, the complete expression for a **circular wave** emanating from a point source is:

$$
\eta(\vec{r}, t) = A \cos\left( \frac{2\pi}{\lambda} r - 2\pi f t + \phi \right)
$$

or, equivalently:

$$
\eta(\vec{r}, t) = A \cos(kr - \omega t + \phi)
$$

This equation will form the foundation for constructing more complex wave interference patterns when multiple sources are considered.

---
## 2. Extension to Multiple Wave Sources

When multiple wave sources emit waves simultaneously, the **net displacement** of the water surface at any point is governed by the **principle of superposition**. According to this principle, the total disturbance at any location is the **sum of the individual wave contributions** from all sources.

---

### **Superposition Principle**

If there are $N$ point sources located at positions $\vec{r}_1, \vec{r}_2, \ldots, \vec{r}_N$, each generating a wave, the net displacement at position $\vec{r}$ and time $t$ is:

$$
\eta_{\text{total}}(\vec{r}, t) = \sum_{n=1}^{N} A_n \cos(k r_n - \omega t + \phi_n)
$$

Where:

- $A_n$: Amplitude of the $n$-th source.
- $r_n = \|\vec{r} - \vec{r}_n\|$: Distance from the $n$-th source to observation point.
- $\phi_n$: Initial phase of the $n$-th source.
- $k$: Wave number (assumed common to all sources for same wavelength).
- $\omega$: Angular frequency (assumed common to all sources for same frequency).

---

### **Key Considerations**

#### **1. Number of Sources**

Let $N$ be the number of wave sources.

- Each source contributes a term to the total wave function.
- Interference becomes richer and more complex as $N$ increases.

#### **2. Source Locations**

Each source is defined by a 2D position vector:

$$
\vec{r}_n = (x_n, y_n)
$$

The radial distance to observation point $\vec{r} = (x, y)$ is:

$$
r_n = \sqrt{(x - x_n)^2 + (y - y_n)^2}
$$

#### **3. Phase Difference Between Sources**

Each source may have a unique initial phase $\phi_n$, which introduces a **phase difference** between the waves. This phase difference can cause:

- **Constructive interference**: when phase difference leads to in-phase summation.
- **Destructive interference**: when waves are out of phase by $\pi$ (or odd multiples).

---

### **Two-Source Interference Example**

For two identical sources with equal amplitude $A$, wavelength $\lambda$, frequency $f$, and no phase difference, the net wave at point $\vec{r}$ is:

$$
\eta_{\text{total}}(\vec{r}, t) = A \cos(k r_1 - \omega t) + A \cos(k r_2 - \omega t)
$$

Using the trigonometric identity:

$$
\cos \alpha + \cos \beta = 2 \cos\left( \frac{\alpha + \beta}{2} \right) \cos\left( \frac{\alpha - \beta}{2} \right)
$$

We get:

$$
\eta_{\text{total}}(\vec{r}, t) = 2A \cos\left( \frac{k(r_1 - r_2)}{2} \right) \cos\left( \frac{k(r_1 + r_2)}{2} - \omega t \right)
$$

This shows that the amplitude of the resulting wave is **modulated** by the path difference $(r_1 - r_2)$, producing **interference fringes** in space.

---

### **Summary**

- Multiple wave sources produce a **net wave field** through superposition.
- The pattern depends on:
  - Relative positions of sources
  - Phase differences
  - Path length differences to the observation point
- The resulting interference patterns can exhibit **regions of constructive and destructive interference**, crucial in understanding wave phenomena like diffraction and coherence.

---


