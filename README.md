### Mathematical Derivation of the Transfer Function (Low-Pass Filter)

For a standard passive RC low-pass filter, we treat the circuit as a voltage divider in the Laplace domain ($s$-domain). 

* The impedance of the resistor is $Z_R = R$
* The impedance of the capacitor is $Z_C = \frac{1}{sC}$

Using the voltage divider rule:
$$V_{out}(s) = V_{in}(s) \left( \frac{Z_C}{Z_R + Z_C} \right)$$

To find the transfer function $H(s)$, we divide both sides by $V_{in}(s)$:
$$H(s) = \frac{V_{out}(s)}{V_{in}(s)} = \frac{Z_C}{Z_R + Z_C}$$

Substitute the impedance values into the equation:
$$H(s) = \frac{\frac{1}{sC}}{R + \frac{1}{sC}}$$

To simplify and remove the fractions inside fractions, multiply both the numerator and the denominator by $sC$:
$$H(s) = \frac{1}{1 + sRC}$$
