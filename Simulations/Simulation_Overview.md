## Comparator Simulation
![Comparator Simulation](<img width="625" height="326" alt="image" src="https://github.com/user-attachments/assets/86264716-e274-4da0-8852-600e8d62e75b" />)

The comparator compares the Input voltage(pin2) and Reference voltage(pin3). When the Input < Reference the comparator output is pulled HIGH by the pull up resistor. Similiarly, when Input > Reference the comparator output is LOW.

---
## N-MOSFET Simulation
![MOSFET Simulation](<img width="601" height="347" alt="image" src="https://github.com/user-attachments/assets/dae2356f-e2a1-4275-a401-3b41dcf1cda2" />)

The N-MOSFET acts like a power switch that activates when the gate voltage exceeds a threshold of the MOSFET. When the Gate to Source voltage exceeds the threshold the MOSFET is ON and allows power to run from the drain to source, completing the circuit. However, whenever the Gate to Source is less than the threshold voltage the MOSFET is OFF, preventing power going from the drain to source.

---
## Relay Simulation
![Relay Simulation](<img width="556" height="319" alt="image" src="https://github.com/user-attachments/assets/5ff71a23-bb52-4840-852b-efc2d3515fe8" />)

The Relay is used to isolate the input voltage from the protected circuit. When the relay coil is energised it closes the contact allowing the input voltage to reach the protected circuit(LED). 

---
## DC Voltage Test Simulation
![DC Voltage Simulation](<img width="727" height="373" alt="image" src="https://github.com/user-attachments/assets/bb4ba919-eddb-41bf-8aed-47860c9ac1aa" />)

This is the combination of 3 stages Comparator, MOSFET, and Relay. This test used DC voltage to confirm each component can work together to protect a circuit from a surge. When Input < Reference the Comparator ouput is pulled HIGH and the MOSFET becomes ON allowing the relay coil to become energised and allows the input voltage to power the protected circuit. However, when the Input > Reference the Comparator output becomes LOW turning the MOSFET OFF and de-energising the relay coil preventing the input voltage from the reaching the protected circuit.

---
## AC Voltage Test Simulation 
![AC Voltage Simulation](<img width="902" height="319" alt="image" src="https://github.com/user-attachments/assets/f0168e08-1611-42fd-9e6a-3b2b73c4eaa7" />)

To make this simulation work on AC voltage, I have to use a bridge rectifier and voltage divider to successfully scale the input voltage to become readable for the comparator. The diode across the relay coil acts as a feedback diode to stop contant switching. The logic is the same as the DC voltage test.

---
