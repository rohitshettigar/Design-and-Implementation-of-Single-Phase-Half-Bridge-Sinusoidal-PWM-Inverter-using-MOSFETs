#  Single-Phase Half-Bridge Sinusoidal PWM Inverter using MOSFETs

---

##  Abstract

This project involves designing and implementing a single-phase **half-bridge sinusoidal PWM inverter** using MOSFETs to generate a 9V, 50Hz AC output from a DC source. The inverter uses a **555 timer-based PWM generator** operating at 18kHz, with filtering and amplification circuits for waveform shaping. The system is designed to drive the secondary side of a 9-0-9 transformer with an expected load of 120mA at the primary.

---

##  Project Objective

- Generate a 50Hz AC waveform using PWM control at 18kHz
- Design a sine wave generator using an RC phase shift oscillator
- Implement a PWM comparator circuit using a 555 timer
- Use op-amp-based difference and inverting amplifiers for waveform conditioning
- Feed the signal to a half-bridge MOSFET-based inverter
- Drive a 9-0-9 transformer with 9V, 50Hz output

---

##  Circuit Design and Equations

###  Sine Wave Generator (RC Phase Shift Oscillator)
- Formula:  
  `f = 1 / (2πRC√2N)`  
- Chosen: `C = 0.47µF`, `R ≈ 2.2kΩ` (trial and error)

###  Sawtooth Generator (555 Timer PWM)
- Formula:  
  `f ≈ 3 / RC`  
- Chosen: `C = 0.01µF`, `R ≈ 16.66kΩ`  
- Final setup: 10kΩ + 10kΩ potentiometer to tune PWM frequency

###  Difference Amplifier
- Gain setup: `Vout = 1.5Vin1 - Vin2`
- Values used:  
  `R1 = Rf = 10kΩ`, `R2 = 3.33kΩ`, `R3 = 12kΩ`

###  Inverting Amplifier
- Op-amp configuration for phase inversion  
- Formula: `Vout = -Vin`  
- Components: `R1 = R2 = Rf = 10kΩ`

---

##  Simulation Results

###  Inverting Amplifier Output
- Successfully inverts sine waveform

###  Generated Waveforms
- **Sine wave**
- **Sawtooth waveform**
- **PWM signal**
- **Comparator output**

###  Sample Output:

![PWM Output](outputs/pwm_output.png)

---

##  Hardware Implementation

- Breadboard prototype with all designed circuits
- Half-bridge inverter stage using MOSFETs
- Connected to a 9-0-9 transformer as load
- Oscilloscope used to verify final AC output waveform

---

##  Final Result

The hardware model successfully produces a **9V, 50Hz AC waveform**, with PWM switching at **18kHz**, and the generated waveform closely resembles a sinusoidal signal when observed through a transformer.

---


