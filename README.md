# RC Filter Analysis: Low-Pass and Band-Pass

This section covers the theory, behavior, and mathematical derivation of passive RC filters used in signal processing.

---

## 1. RC Passive Low-Pass Filter (LPF)
An RC passive low-pass filter allows low-frequency signals to pass through and attenuates high-frequency signals beyond the cut-off frequency. 

### Characteristics:
* **Cut-off Frequency ($f_c$):** The point at which the filter attenuates the signal significantly (typically -3dB).
* **First-Order Circuit:** It is a first-order circuit because its frequency response has a slope of **-20 dB per decade**. 
* **Attenuation:** For every factor of 10 increase in frequency, the output voltage becomes 10 times smaller.

### Mathematical Derivation (LPF)
For a standard passive RC low-pass filter, we treat the circuit as a voltage divider in the Laplace domain ($s$-domain):

* Impedance of resistor: $Z_R = R$
* Impedance of capacitor: $Z_C = \frac{1}{sC}$

Using the voltage divider rule:
$$V_{out}(s) = V_{in}(s) \left( \frac{Z_C}{Z_R + Z_C} \right)$$

The transfer function $H(s)$ is:
$$H(s) = \frac{V_{out}(s)}{V_{in}(s)} = \frac{\frac{1}{sC}}{R + \frac{1}{sC}}$$

Multiplying numerator and denominator by $sC$:
$$H(s) = \frac{1}{1 + sRC}$$
<img width="349" height="226" alt="image" src="https://github.com/user-attachments/assets/940f613f-a639-468c-a87a-f34cb950b8d4" />


---

## RC Passive Band-Pass Filter (BPF)
A band-pass filter allows signals between two specific frequencies to pass but attenuates signals outside these frequencies. 

### Characteristics:
* **Cascaded Design:** It is created by connecting a high-pass filter (HPF) and a low-pass filter (LPF) in a cascade.
* **Passband:** The defined frequency range permitted by the filter.
* **Stopband:** The frequency ranges outside the passband that are attenuated.

### Mathematical Derivation (BPF)
A passive band-pass filter can be modeled as the product of a High-Pass Filter and a Low-Pass Filter transfer function (assuming negligible loading effects).

#### High-Pass Stage:
The transfer function for an HPF (where output is taken across the resistor) is:
$$H_{HP}(s) = \frac{sR_1C_1}{1 + sR_1C_1}$$

#### Low-Pass Stage:
The transfer function for an LPF (where output is taken across the capacitor) is:
$$H_{LP}(s) = \frac{1}{1 + sR_2C_2}$$

#### Composite Transfer Function:
The total transfer function $H_{BP}(s)$ for the cascaded Band-Pass filter is the product of the two:
$$H_{BP}(s) = H_{HP}(s) \cdot H_{LP}(s)$$

$$H_{BP}(s) = \left( \frac{sR_1C_1}{1 + sR_1C_1} \right) \cdot \left( \frac{1}{1 + sR_2C_2} \right)$$

To simplify, let $\tau_1 = R_1C_1$ and $\tau_2 = R_2C_2$:
$$H(s) = \frac{s\tau_1}{(1 + s\tau_1)(1 + s\tau_2)}$$

This result shows a zero at the origin (from the high-pass section) and two poles (one from each section), defining the lower and upper cut-off frequencies.
<img width="812" height="333" alt="image" src="https://github.com/user-attachments/assets/9c7948dc-b199-408b-afb8-a1ce0422288a" />


