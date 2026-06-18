## Simulation
---
## 555-timer Simulation
![555-timer Simulation](<img width="570" height="395" alt="image" src="https://github.com/user-attachments/assets/d89aef46-e2ea-45f1-86b9-a8539eadc034" />)

I used from the Multisim live website (1). This pulse generator circuit uses a 555-timer configured as an astable oscillator to generate a pulse signal. Pins 2 and 6 are connected, allowing the timer to continuously trigger itself and operate as a free-running oscillator. During operation, the capacitor C1 charges through resistors R1, R2, and R3 until the voltage reaches approximately 2/3 of the supply voltage. This switches the output state of the internal comparators, and the capacitor begins to discharge through R2 through the discharge pin (pin 7) (2). When the capacitor voltage falls to approximately 1/3 Vcc, the timer switches again and the capacitor begins charging again. This repeated charging and discharging cycle produces a pulse waveform at the output, which is seen on the oscilloscope in image above (2). The LED is used to visually show the output state changing. I then added a preset resistor (3) to be able to change the width of the impulse signal, to increase or decrease the frequency of the impulses.

(1) 555-timer multisim live circuit - https://www.multisim.com/content/mqyrwJnai3YXxheMHwvpdf/ic-555using-pulse-generator/ 
(2) Electronics tutorial on 555-timers - https://www.electronics-tutorials.ws/waveforms/555_oscillator.html
(3) Potentiometer Pinout - https://www.jotrin.com/technology/details/potentiometer-pinout-symbol-wiring-and-working

---
## Op-Amp Simulation
![Op-Amp Simulation](<img width="559" height="464" alt="image" src="https://github.com/user-attachments/assets/16b943a3-a433-4bbb-8f54-253b1acc4dd4" />)

The image above shows the simulation uses a TL071 OpAmp (1) that works by comparing the voltages at the inverting (−) and non-inverting (+) inputs. When the voltage at the non-inverting input becomes greater than the voltage at the inverting input, the output switches to a high voltage close to the positive supply. When the voltage at the inverting input becomes greater, the output switches to a low voltage close to the negative supply. This switching behaviour causes the output to alternate above and below zero creating the square wave signal shown on the oscilloscope. (2)

(1) TL071CP datasheet - https://www.ti.com/lit/ds/symlink/tl071.pdf
(2) Electronics tutorial on comparators - https://www.electronics-tutorials.ws/opamp/op-amp-comparator.html 

---
## Combined Trigger circuit Simulation
![Combined Trigger circuit simulation](<img width="849" height="444" alt="image" src="https://github.com/user-attachments/assets/11cdf0af-6390-49ef-ae63-4c0040743303" />)

The image above shows the simulation of the combined 555 timer impulse circuit and op-amp to generate an AC waveform. The 555 timer produces a repeating pulse signal, which outputs into the op-amp. The operational amplifier inverts and amplifies the voltage using an offset voltage on the non-inverting pin (+). The oscilloscope shows AC waveform, confirming that the impulse generator and op-amp work together correctly. This demonstrates that the trigger circuit can generate a signal suitable for testing the protection circuit.

---
## Testing
---
## 555-timer test
![555-timer breadbaord test](<img width="400" height="158" alt="image" src="https://github.com/user-attachments/assets/41114f60-337c-4949-802c-1c8cd76bf060" />)

The image above shows the circuit was built on a breadboard based on the design from the Multisim Live page. The circuit was first constructed without the preset resistor to confirm that the 555 timer was operating correctly and producing the expected square wave output.the 10kΩ preset resistor (2) is set to 50% resistance. The oscilloscope shows that the pulse width has increase, demonstrating that the timing characteristics of the circuit can be adjusted.

(1) 555-timer multisim live circuit - https://www.multisim.com/content/mqyrwJnai3YXxheMHwvpdf/ic-555using-pulse-generator/
(2) Potentiometer Pinout - https://www.jotrin.com/technology/details/potentiometer-pinout-symbol-wiring-and-working

---
## Op-Amp test
![Op-Amp breadboard test](<img width="369" height="124" alt="image" src="https://github.com/user-attachments/assets/9e282f3c-7a6d-49a9-b9cf-62c7ac74f564" />)

This image above shows the breadboard circuit connected in the same way as the simulation. An input voltage of 5V square wave signal from the waveform generator is used to replicate the output of the 555-timer circuit. The outputted waveform matches the expected behaviour from the simulation, confirming that the operational amplifier is functioning correctly within the circuit.

---
## Combined 555-timer and Op-Amp test
![Combined breadboard test](<img width="335" height="88" alt="image" src="https://github.com/user-attachments/assets/20bc897d-f78e-4263-b15b-c1912f533f54" />)

The image above shows the fully integrated circuit of the 555 timer and operational amplifier. The oscilloscope output shows a waveform that closely resembles the waveform observed in the simulation. However, the measured output voltage is slightly lower than the simulated value. This difference is because the preset resistor was set to 100% resistance, which reduces the pulse width of the signal and increases the switching frequency of the circuit.

---
## SUMMARY OF FINDINGS
The trigger circuit was found to be unreliable during testing due to instability in the generated waveform and the presence of high-frequency noise. This made it difficult to produce a consistent transient signal and resulted in unpredictable triggering behaviour. As a consequence, the trigger circuit could not reliably generate the surge conditions required for repeatable testing.

For future development, a more controlled approach would be to use a function generator to create the surge event. By combining a sinusoidal waveform representing the normal AC supply with a burst signal to simulate a transient overvoltage, repeatable and adjustable surge conditions can be produced. This would provide a more reliable method of evaluating the circuit's response to surge events while eliminating the instability observed in the original trigger circuit.

---
