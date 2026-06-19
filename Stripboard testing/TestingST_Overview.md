## AC Voltage test 
![Reference > Input Fig 1](<img width="303" height="359" alt="image" src="https://github.com/user-attachments/assets/d5696ffa-d080-4df6-b2d4-f6c84e8fa611" />)
![Input > Reference Fig 2](<img width="303" height="362" alt="image" src="https://github.com/user-attachments/assets/f0b0a93f-e49f-4491-a984-921a7277eedc" />)

After testing was completed on the breadboard, the design was transferred over to stripboard to create a more reliable prototype. The components were arranged in the same way as the breadboard, but the wiring was made neater so that you can observe every wires path. The results shown in Figures 1 & 2 confirm the circuit behaviour hasn’t changed from the breadboard test. 

---
## Trigger Circuit tested on Protection Circuit
![Resistance Increased Fig 1](<img width="325" height="133" alt="image" src="https://github.com/user-attachments/assets/62e20e52-c359-49db-8fb0-5edd269534ae" />)
![Resistance Decreased Fig 2](<img width="329" height="136" alt="image" src="https://github.com/user-attachments/assets/b7250722-3b87-41f3-b6c4-0654538c5f36" />)

A preset resistor was used to change the input conditions. When the resistance was decreased, the LED remained OFF, as shown in Figure 2, indicating that Vin is greater than Vref . When the resistance was increased, the LED turned ON, as shown in Figure 1, showing that the circuit detected the higher voltage level.

However, when the trigger circuit was tested with the protection stage, the system did not operate consistently. Although the comparator responded to changes in voltage, the protection stage did not consistently activate, likely due to waveform instability and electrical noise affecting the comparator’s performance.

---
## Protection circuit WITH Improvements
![Improvements MADE](<img width="505" height="616" alt="image" src="https://github.com/user-attachments/assets/92a1eafc-2a01-4c88-8f2d-2864ad1bd6df" />)

The issue with the previous circuit is that the reference voltage is only one point so when the Input Voltage is close to the Reference Voltage because it is a little bit unstable which cause constant switching across the relay. Hysteresis is needed to create an upper and lower limit to stop constant switching and to improve the reliability of the circuit.

The testing results proved that the improvements will prevent the constant switching across the relay, improving the protectibility of the protection circuit.

---
