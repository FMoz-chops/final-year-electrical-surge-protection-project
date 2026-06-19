## Comparator Breadboard test
To verify the comparator stage, the circuit was built and tested on a breadboard. The comparator is used to compare the Vin with a defined Vref. When the Vin exceeds Vref, the output of the comparator changes state.

![Reference > Input](<img width="315" height="255" alt="image" src="https://github.com/user-attachments/assets/579a6225-9f2c-4a4f-805a-d6d8fc67bf91" />)

When the Vref is greater than Vin the comparator output is pulled HIGH by a pull up resistor, allowing power to flow through the LED shown above. This indicates that the comparator has detected that the reference is higher than the input.

![Input > Reference](<img width="322" height="240" alt="image" src="https://github.com/user-attachments/assets/51b9b90b-2e2d-4bed-85aa-18940c700d64" />)

However, the image above shows when the Vref is less than Vin. The comparator output is pulled LOW to ground and the LED turns OFF, showing that the input has exceeded the reference.

These results confirm that the comparator works as expected from the simulation and can be used to detect when the input voltage exceeds a defined reference voltage.

---
## MOSFET Breadboard test
## N-MOSFET test
To understand how a MOSFET works I watched a YouTube video (1) that explains how MOSFETs work. Also using the IRLZ44N (2).
![N-MOSFET Diagram](<img width="519" height="233" alt="image" src="https://github.com/user-attachments/assets/3dff1817-539b-4369-a6c1-bb28c260df9e" />)

![Gate voltage > Threshold voltage Fig 1](<img width="302" height="218" alt="image" src="https://github.com/user-attachments/assets/37b6aa78-2f1f-4f58-b627-4bada51c073b" />)
![Gate voltage < Threshold voltage Fig 2](<img width="299" height="214" alt="image" src="https://github.com/user-attachments/assets/a623b0be-3553-4b47-a39a-708e067b4fe5" />)

After setting up the diagram from the YouTube video I realised that the MOSFET needs a pull-down resistor to stop the MOSFET from constantly switching. Figure 1 shows the gate voltage has exceeded the threshold voltage, the MOSFET is ON, allowing voltage to flow from the drain to source, LED is ON. However, Figure 2 shows when the gate voltage is less than the threshold voltage which prevents the voltage from flowing from the drain to source, LED is OFF.

- (1) MOSFETs explained - https://www.youtube.com/watch?v=AwRJsze_9m4&start=0
- (2) IRLZ44N Datasheet - https://www.infineon.com/assets/row/public/documents/24/49/infineon-irlz44n-datasheet-en.pdf

## P-MOSFET
![Gate voltage < Threshold voltage Fig 3](<img width="328" height="242" alt="image" src="https://github.com/user-attachments/assets/375d92c9-aa69-402b-96e5-98b3042bad6e" />)
![Gate voltage > Threhsold voltage Fig 4](<img width="326" height="222" alt="image" src="https://github.com/user-attachments/assets/dafa0f7c-dfac-4b73-9e15-d9a364bbc7b2" />)

The exact same test was done on a P-channel MOSFET, using a IRF4905 MOSFET. From the datasheet (3) the drain and source pins are different to the IRLZ44N. The P-channel MOSFET works the opposite way to an N-channel. When the gate voltage is less than the threshold voltage, the MOSFET is ON, allowing voltage to flow from drain LED is ON, shown in Figure 3. However, when the gate voltage exceeds the threshold the MOSFET is OFF, preventing the flow of voltage from the drain to the source, LED is OFF, shown in Figure 4.

- (3) IRL4905 Datasheet - https://www.infineon.com/assets/row/public/documents/24/49/infineon-irf4905-datasheet-en.pdf?fileId=5546d462533600a4015355e329b1197e

## Conclusion on MOSFET testing
I found that using an N-channel MOSFET functions is the correct way to trigger the relay. This would work by the comparator output being HIGH and the MOSFET ON, until the comparator detects a surge pulling the output to ground. This makes the MOSFET change state, de-energising the relay coil.

---
## Relay Breadbaord test
![Relay Coil ENERGISED Fig 1](<img width="268" height="279" alt="image" src="https://github.com/user-attachments/assets/e3e5479d-e7a3-4edb-aa29-59ea7050d6c3" />)
![Relay Coil DE-ENERGISED Fig 2](<img width="262" height="309" alt="image" src="https://github.com/user-attachments/assets/00ed141e-3fb6-4c70-b93b-e0b356067b10" />)

This relay component GS-SH-212D (1) has two sides the relay coil and the load side. The load side has a common where the Vin goes and two contact (NO & NC). When the relay coil is energised it creates a magnetic field that changes the relay contact to NO powering the LED shown in Figure 1. Similarly, when the relay coil is de-energised the magnetic field is gone and a spring pushes the contact back to NC, protecting the load shown in Figure 2.

-(1) GS-SD-212D Datasheet - https://www.infineon.com/assets/row/public/documents/24/49/infineon-irf4905-datasheet-en.pdf?fileId=5546d462533600a4015355e329b1197e 

---
## Comparator & N-MOSFET Breadboard test
![Circuit drawing Fig 1](<img width="597" height="295" alt="image" src="https://github.com/user-attachments/assets/54666a4b-6616-402a-83c8-e6afb987774a" />)
![Truth table T1](<img width="359" height="79" alt="image" src="https://github.com/user-attachments/assets/ce5a23dc-97d8-475b-806d-cbd7e4eb7ca1" />)
![Reference > Input Fig 2](<img width="403" height="258" alt="image" src="https://github.com/user-attachments/assets/29c38a9f-4cea-4b35-96b2-3701946be7d0" />)
![Input < Reference](<img width="401" height="282" alt="image" src="https://github.com/user-attachments/assets/b104f629-0ddb-46a3-8b14-ec376c6ac7cb" />)

After testing each component individually, I then tested the comparator and N-MOSFET to ensure they could work together, using an LED to represent the relay coil. Before testing I drew a circuit drawing, Figure 1. T1 shows the truth table on how the logic works for this circuit. The circuit observations are shown in Figure 2 & 3.

---
## DC Voltage Breadboard test
![Circuit drawing Fig 1](<img width="614" height="314" alt="image" src="https://github.com/user-attachments/assets/7550eebb-85eb-4765-9fe2-ddb15c45c29c" />)
![Protected circuit POWERED Fig 2](<img width="420" height="293" alt="image" src="https://github.com/user-attachments/assets/2cc22955-680e-40ce-84c4-19da1b89fe48" />)
![Protected circuit PROTECTED Fig 3](<img width="418" height="287" alt="image" src="https://github.com/user-attachments/assets/9dc71aa9-6a30-4d29-8c6f-b88fbafd4a0e" />)

To verify the protection circuit under DC conditions, the complete circuit consisting of the comparator, N-MOSFET, and relay was built and tested on a breadboard. The purpose of this test was to confirm that the protection circuit doesn’t interfere when Vref is greater than Vin. A circuit drawing was designed for the breadboard before testing, Figure 1.

As shown in Figure 2, the circuit is operating under normal conditions where the input is less the reference. The comparator output drives the MOSFET gate above the threshold voltage, allowing the MOSFET to conduct, energising the relay coil, the LED is ON indicating that the load is powered.

However, Figure 3 shows the circuit operating in the protected state. The input has exceeded the reference; the comparator output switches LOW which removes the gate voltage from the MOSFET. As a result, the MOSFET turns OFF, the relay coil has become de-energised, and the LED turns OFF, demonstrating the protection circuit has successfully isolated the load.

---
## AC Voltage Breadboard test
![Circuit drawing](<img width="888" height="391" alt="image" src="https://github.com/user-attachments/assets/2a0a10cb-e004-454d-9d93-5076903f1ea1" />)

After assembling the circuit on the breadboard, the system was tested to verify the operation of the rectifier, voltage divider, comparator, MOSFET and relay stages. A waveform generator was used to simulate an AC input signal, and the oscilloscope was used to observe the rectifier output.

![AC Reference > Input Fig 1](<img width="619" height="296" alt="image" src="https://github.com/user-attachments/assets/cdd009be-458d-4ef0-a9cf-9ede05e18fcb" />)
![AC Input > Reference Fig 2](<img width="619" height="285" alt="image" src="https://github.com/user-attachments/assets/3ce85f98-0ff1-4187-99aa-369728a8eca0" />)

- When Vin < Vref, the comparator output remains low and the MOSFET is OFF, which causes the relay to energise. This closes the normally open contact and allows power to reach the protected circuit, as shown in Figure 1.
- When Vin > Vref, the comparator output switches state, turning the MOSFET ON and de-energising the relay. This isolates the protected circuit from the supply, as shown in Figure 2.

---
