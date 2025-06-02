# Problem 1
# Orbital Period and Orbital Radius — Theoretical Foundation

## Newtonian Derivation of Kepler’s Third Law

To derive Kepler’s Third Law for circular orbits, we begin by equating the **gravitational force** providing the **centripetal force** required for circular motion.

### Gravitational Force:

$$
F_g = \frac{G M m}{r^2}
$$

Where:  
- \( G \) is the universal gravitational constant  
- \( M \) is the mass of the central body (e.g., a star or planet)  
- \( m \) is the mass of the orbiting object  
- \( r \) is the orbital radius  

### Centripetal Force:

$$
F_c = \frac{m v^2}{r}
$$

For a stable circular orbit, these forces must be equal:

$$
\frac{G M m}{r^2} = \frac{m v^2}{r}
$$

Cancelling \( m \) and rearranging:

$$
v^2 = \frac{G M}{r}
$$

### Orbital Period:

The orbital period \( T \) is the time to complete one full revolution. Since the circumference of the orbit is \( 2\pi r \):

$$
T = \frac{2\pi r}{v}
$$

Substitute for \( v \):

$$
T = \frac{2\pi r}{\sqrt{\frac{G M}{r}}} = 2\pi \sqrt{\frac{r^3}{G M}}
$$

### Final Form of Kepler’s Third Law:

$$
T^2 = \frac{4\pi^2}{G M} r^3
$$

This demonstrates the proportionality:

$$
T^2 \propto r^3
$$

---

## Assumptions in This Derivation

- The orbit is perfectly circular.
- The orbiting body's mass \( m \) is negligible compared to \( M \).
- The system is isolated (no perturbations from other bodies).
- General Relativity effects are ignored (Newtonian approximation).

---

## Interpretation

- For all satellites orbiting the same central mass \( M \), the ratio \( \frac{T^2}{r^3} \) is constant.
- This law allows astronomers to compare orbital periods and radii without knowing \( M \) directly, or to infer \( M \) when \( T \) and \( r \) are known.
# Orbital Period and Orbital Radius — Astrophysical Implications

## Kepler’s Third Law in Astronomy

Kepler’s Third Law:

$$
T^2 = \frac{4\pi^2}{G M} r^3
$$

This fundamental relationship has wide-ranging implications in astronomy and astrophysics.

---

## 1. Determining Masses of Celestial Bodies

Rearranging Kepler's Law to solve for \( M \):

$$
M = \frac{4\pi^2 r^3}{G T^2}
$$

Where:  
- \( M \) is the mass of the central object  
- \( r \) is the orbital radius  
- \( T \) is the orbital period  
- \( G \) is the gravitational constant  

### Application:
- By measuring \( T \) and \( r \), astronomers can calculate the mass of:
  - Planets (from their moons' orbits)
  - Stars (from exoplanets’ orbits)
  - Galaxies (using orbital motion of stars or gas clouds)

---

## 2. Determining Orbital Distances

If the central mass \( M \) is known (e.g., mass of the Sun), Kepler’s Law can be used to calculate the orbital radius \( r \) for satellites or planets:

$$
r = \left( \frac{G M T^2}{4\pi^2} \right)^{1/3}
$$

Useful for:
- Predicting satellite altitudes
- Estimating distances of exoplanets from their host stars

---

## 3. Validating Observational Data

By comparing observed values of \( T \) and \( r \) with theoretical predictions, scientists can:
- Confirm the validity of Newtonian mechanics
- Detect anomalies (e.g., additional massive bodies, non-gravitational forces)

---

## 4. Inferring Existence of Hidden Objects

If observed \( T \) and \( r \) values deviate from expectations:
- May suggest presence of dark matter
- Or reveal gravitational influence of unseen exoplanets or black holes

---

## 5. Limitations and Generalizations

- The law applies **strictly to two-body circular orbits**.
- **Elliptical orbits** require a more general form using the semi-major axis \( a \):
  
  $$
  T^2 = \frac{4\pi^2}{G M} a^3
  $$

- For very massive systems or high velocities, **General Relativity** corrections may be necessary.

# Orbital Period and Orbital Radius — Real-World Examples

Kepler's Third Law can be directly applied to various real-world systems, from the Earth's Moon to planets in the Solar System.

---

## 1. The Moon Orbiting Earth

Let’s analyze the Moon’s orbit as a test of Kepler's Third Law.

### Known values:
- Orbital radius:  
  $$ r_{\text{Moon}} \approx 3.84 \times 10^8 \, \text{m} $$
- Orbital period:  
  $$ T_{\text{Moon}} \approx 27.32 \, \text{days} = 2.36 \times 10^6 \, \text{seconds} $$
- Gravitational constant:  
  $$ G = 6.67430 \times 10^{-11} \, \text{m}^3\,\text{kg}^{-1}\,\text{s}^{-2} $$
- Mass of Earth:  
  $$ M_{\text{Earth}} \approx 5.972 \times 10^{24} \, \text{kg} $$

### Theoretical Prediction:

Using:

$$
T = 2\pi \sqrt{\frac{r^3}{G M}}
$$

Plugging in the values:

$$
T_{\text{calc}} = 2\pi \sqrt{\frac{(3.84 \times 10^8)^3}{6.67430 \times 10^{-11} \times 5.972 \times 10^{24}}} \approx 2.36 \times 10^6 \, \text{seconds}
$$

✅ Matches observed period — confirms accuracy of Kepler's Law.

---

## 2. Planetary Orbits in the Solar System

Let’s examine the relation between \( T^2 \) and \( r^3 \) for several planets.

| Planet   | Orbital Radius \( r \) (AU) | Orbital Period \( T \) (years) | \( T^2 \) | \( r^3 \) |
|----------|-----------------------------|-------------------------------|----------|----------|
| Mercury  | 0.39                        | 0.24                          | 0.058    | 0.059    |
| Venus    | 0.72                        | 0.62                          | 0.384    | 0.373    |
| Earth    | 1.00                        | 1.00                          | 1.000    | 1.000    |
| Mars     | 1.52                        | 1.88                          | 3.534    | 3.512    |
| Jupiter  | 5.20                        | 11.86                         | 140.7    | 140.6    |
| Saturn   | 9.58                        | 29.46                         | 867.6    | 880.0    |

Here, units are in **Astronomical Units (AU)** and **years**, making \( G M = 4\pi^2 \) in these units.

✅ The values of \( T^2 \) and \( r^3 \) are nearly equal, confirming:

$$
T^2 \approx r^3
$$

---

## 3. Graphical Validation

Plotting \( T^2 \) vs \( r^3 \) for planetary data gives a **linear graph** with slope ≈ 1, as expected.

### Logarithmic Version:
Taking log of both sides:

$$
\log T = \frac{3}{2} \log r + \text{const}
$$

This implies that a log-log plot of \( T \) vs \( r \) will be a straight line with slope 1.5.

---

## 4. Applications Beyond the Solar System

- Used to determine distances of **exoplanets** from host stars (via transit or radial velocity methods).
- Used to estimate the mass of **binary star systems** or even **black holes** in binary orbits.

---

## Summary

Real-world data strongly supports Kepler's Third Law in both our Solar System and beyond. Small deviations can often point to exciting new physics or unseen objects.

## 4. Computational Model & Simulation.
Kepler's Third Law Simulation
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11          # Universal gravitational constant [m^3 kg^-1 s^-2]
M_sun = 1.989e30         # Mass of the Sun [kg]

# Function to compute orbital period
def orbital_period(radius_m):
    """
    Calculates orbital period T [seconds] for a given orbital radius r [meters].
    Assumes circular orbit around a mass M_sun.
    """
    T = 2 * np.pi * np.sqrt(radius_m**3 / (G * M_sun))
    return T

Earth's Orbital Period
# Earth's orbit radius
r_earth = 1.496e11  # meters

# Compute Earth's orbital period
T_earth = orbital_period(r_earth)
print(f"Earth's orbital period: {T_earth / (60 * 60 * 24):.2f} days")

T² vs r³ Comparison
# Orbital radii [meters] for selected planets
planet_data = {
    "Mercury": 5.79e10,
    "Venus": 1.08e11,
    "Earth": 1.496e11,
    "Mars": 2.28e11,
    "Jupiter": 7.78e11
}

# Calculate and store data
results = []
for planet, r in planet_data.items():
    T = orbital_period(r)
    results.append({
        "Planet": planet,
        "Radius (m)": r,
        "Period (s)": T,
        "T^2 (s²)": T**2,
        "r^3 (m³)": r**3
    })

# Create DataFrame
df = pd.DataFrame(results)
print(df)

Plot: T² vs r³ (Kepler's Law Linearity)
# Extract data
r_cubed = df["r^3 (m³)"].values
T_squared = df["T^2 (s²)"].values

# Plot T² vs r³
plt.figure()
plt.scatter(r_cubed, T_squared)
plt.xlabel("r³ (m³)")
plt.ylabel("T² (s²)")
plt.title("Kepler’s Third Law: T² vs r³")
plt.grid(True)
plt.savefig("kepler_t2_vs_r3.png", dpi=300)
plt.show()

 Plot: log(T²) vs log(r³) — Slope ≈ 1
 # Log-log plot
plt.figure()
plt.plot(np.log10(r_cubed), np.log10(T_squared), 'o-')
plt.xlabel("log₁₀(r³)")
plt.ylabel("log₁₀(T²)")
plt.title("Log-Log Plot: Kepler’s Third Law")
plt.grid(True)
plt.savefig("kepler_loglog_plot.png", dpi=300)
plt.show()

Optional: User Input for Radius
# Optional: dynamic user input
try:
    r_input = float(input("Enter orbital radius in meters: "))
    T_result = orbital_period(r_input)
    print(f"Orbital period: {T_result / 86400:.2f} days")
except:
    print("Invalid input. Please enter a numerical value.")










