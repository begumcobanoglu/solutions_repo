# Problem 1
# Measuring Earth's Gravitational Acceleration with a Pendulum

## 1. Prepare Materials

Precise measurement of the gravitational acceleration, $g$, begins with careful preparation and selection of experimental apparatus. Each component must be chosen and recorded with attention to measurement accuracy and resolution, as these foundational steps propagate through all subsequent calculations.

### 1.1 String

* A lightweight, inextensible string of known length, $L$.

### 1.2 Pendulum Bob (Weight)

* Small, dense object (e.g., metal washer, bag of coins, or keychain) as the bob.
* $L$ measured to the geometric center of the bob.

### 1.3 Measuring Tools

* **Ruler/Tape measure:** Resolution $r$, so uncertainty $\Delta L = r/2$.
* **Stopwatch/timer:** Resolution $r\_t$.
* Combined timing uncertainty $\Delta t = \sqrt{u\_\text{human}^2 + (r\_t/2)^2}$.

### 1.4 Table of Materials

| Item   | Symbol      | Typical Value     | Uncertainty       | Notes                             |
| ------ | ----------- | ----------------- | ----------------- | --------------------------------- |
| String | $L$       | $1.00,\text{m}$ | $\Delta L$      | Length from support to bob center |
| Timer  | $T\_{10}$ | N/A               | $\Delta t$      | Time for 10 oscillations          |
| Ruler  | $r$       | $1,\text{mm}$   | $0.5,\text{mm}$ | Resolution/2                      |

---

## 2. Set Up the Pendulum

* Secure string to fixed support.
* Attach bob to free end, identify center of mass.
* Measure $L$ from suspension point to center of mass of bob.
* Ensure the pendulum swings freely and vertically.
* Keep swing angle $< 15^\circ$ for the small-angle approximation: $\sin \theta \approx \theta$ (in radians).

---

## 3. Measure Pendulum Length

* Hold string taut and measure $L$ with ruler/tape to the center of the bob.
* Record $L$ and instrument resolution $r$.
* Compute uncertainty: $\Delta L = r/2$.

---

## 4. Record the Length and Its Uncertainty

* Record measured value and uncertainty:

  $$
  L = (\text{measured value})\,\text{m} \pm \Delta L
  $$
* Example: $L = 1.003,\text{m} \pm 0.0005,\text{m}$

---

## 5. Collect Oscillation Data

* Displace bob $< 15^\circ$ and release smoothly.
* Time $10$ complete oscillations ($T\_{10}$).
* Repeat for $n = 10$ trials: $T\_{10,1}, T\_{10,2}, ..., T\_{10,10}$.
* Record each value in a table:

| Trial ($i$) | $T_{10,i}$ (s) |
|-------------|----------------|
| 1           | 19.85          |
| 2           | 19.83          |
| 3           | 19.81          |
| 4           | 19.87          |
| 5           | 19.84          |
| 6           | 19.86          |
| 7           | 19.82          |
| 8           | 19.85          |
| 9           | 19.83          |
| 10          | 19.84          |


---

## 6. Calculate Statistics

* Mean:

  $$
  \overline{T}_{10} = \frac{1}{n} \sum_{i=1}^n T_{10,i}
  $$
* Standard deviation:

  $$
  \sigma_T = \sqrt{ \frac{1}{n-1} \sum_{i=1}^n (T_{10,i} - \overline{T}_{10})^2 }
  $$
* Uncertainty in mean:

  $$
  \Delta T_{10} = \frac{\sigma_T}{\sqrt{n}}
  $$

---

## 7. Find the Period and Its Uncertainty

* Period:

  $$
  T = \frac{\overline{T}_{10}}{10}
  $$
* Uncertainty:

  $$
  \Delta T = \frac{\Delta T_{10}}{10}
  $$

---

## 8. Calculate Gravitational Acceleration ($g$)

* Use:

  $$
  g = \frac{4\pi^2 L}{T^2}
  $$

---

## 9. Propagate Uncertainties

* Use:

  $$
  \Delta g = g \sqrt{ \left( \frac{\Delta L}{L} \right)^2 + \left( 2 \frac{\Delta T}{T} \right)^2 }
  $$

---

## 10. Results Summary

| Quantity                | Value    |
|-------------------------|----------|
| $\overline{T}_{10}$ (s) | 19.84    |
| $\sigma_T$ (s)          | 0.020    |
| $\Delta T_{10}$ (s)     | 0.006    |
| $T$ (s)                 | 1.984    |
| $\Delta T$ (s)          | 0.0006   |
| $L$ (m)                 | 1.003    |
| $\Delta L$ (m)          | 0.0005   |
| $g$ (m/s$^2$)           | 10.04    |
| $\Delta g$ (m/s$^2$)    | 0.007    |

---


## 11. Visualization: Histogram of Timing Measurements

To better understand the spread of timing data, a histogram of the $T\_{10}$ values was constructed. This provides a visual check for consistency and outliers.

```python
import matplotlib.pyplot as plt
# Replace with your measured values
T_10 = [19.85, 19.83, 19.81, 19.87, 19.84, 19.86, 19.82, 19.85, 19.83, 19.84]
plt.figure(figsize=(6, 4))
plt.hist(T_10, bins=5, edgecolor='black', alpha=0.7)
plt.title('Histogram of Timing Measurements ($T_{10}$)')
plt.xlabel('Time for 10 Oscillations (s)')
plt.ylabel('Frequency')
plt.grid(axis='y', alpha=0.3)
plt.tight_layout()
plt.show()
```
![alt text](<WhatsApp Görsel 2025-06-10 saat 00.03.26_7c68e1db.jpg>)

---

## 12. Compare and Analyze

* Compare your $g$ to the standard value: $g\_{\text{standard}} = 9.81,\text{m/s}^2$
* Does your result agree within uncertainty?
* Discuss:

  * Major sources of uncertainty (length, timing, etc.)
  * Potential systematic errors (angle, air resistance, pivot friction)
  * Any improvements for future experiments

---

## 13. Discussion

### Measurement Resolution

* The resolution of the ruler sets the lower bound for $\Delta L$.
* Timing uncertainty is dominated by human reaction time and the stopwatch resolution.

### Timing Variability

* Standard deviation and standard error quantify random timing errors.
* Outliers (if any) may indicate procedural errors or distractions.

### Assumptions and Model Limitations

* Small-angle approximation
* Negligible damping (air resistance, pivot friction)
* Point-mass bob

### Implications for Experimental Accuracy

* Identify the largest contributors to total uncertainty.
* Suggest specific improvements (better tools, more trials, automated timing, etc.)
