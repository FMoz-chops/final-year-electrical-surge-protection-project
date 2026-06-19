## Project aims

Electrical systems in industrial and commercial settings are relying more on sensitive electronics that are vulnerable to Transient Voltage events also referred to as electrical surges. Transient voltage events are short bursts of high electrical energy that can interfere with or damage systems, mainly caused by power switching, wiring faults, and external events like lightning strikes. When subjected to these electrical surges, sensitive electronics can fail or suffer permanent damage, causing loss of data, damage to expensive equipment, and a potential safety risk to users. 
Existing SPDs are primarily designed to limit the transient energy from reaching the system by diverting the energy away from the sensitive electronics. However, SPDs have a finite lifespan and over time their protection threshold can deteriorate allowing transient energy through and damaging the system. The lack of knowledge on SPDs, combined with the current methods not always being effective to protect the evolving electronics needed in industry and commercial use, highlights the importance of SPD improvement.
This project is based on an issue I encountered while I was on industrial placement. A company control panel was struck by lightning, causing damage to several electrical components. This highlights the importance of surge protection devices in real industrial environments and emphasises the need for improved surge protection methods as electronic systems continue to evolve.

---
## Project Aims

The project aim is to create a Surge Protection Device to help protect sensitive electronics in commercial and industrial settings.

---
## Project Objectives

- To identify key surge protection methods currently used in industry
- To research into the design requirements to replicate an SPD
- To develop a CAD design of the system
- To create a fully working prototype to protect a low-level voltage system
- To scale up my prototype to protect circuit from the mains


---
## Results

The experimental testing of the surge protection circuit demonstrated that the system operated according to the intended design. The rectifier stage successfully converted the simulated AC input signal into a DC voltage suitable for the scaling stage. Measurements taken using a digital multimeter showed that the output of the bridge rectifier was approximately 8.34 V, confirming that the rectifier and smoothing capacitor were functioning correctly.

The voltage divider stage successfully reduced the rectified voltage to a lower level that could be safely compared by the comparator. Using resistor values of 10kΩ and 4.7kΩ, the measured output of the voltage divider was approximately 2.6 V, which matched the designed threshold voltage for the comparator reference input. 

During testing, the comparator was able to detect when the input voltage exceeded the reference voltage. When the input voltage was less than the reference voltage (Vin < Vref), the comparator output was HIGH using a pull-up resistor, the MOSFET remained ON, allowing the relay coil to become energised and power the protected circuit. When the input voltage exceeded the reference voltage (Vin > Vref), the comparator output changed state, causing the MOSFET to switch and de-energise the relay, isolating the protected circuit from the supply. Overall, the experimental results confirm that the circuit successfully detects over-voltage conditions and automatically isolates the load using the relay switching stage. This demonstrates that the proposed protection circuit can protect sensitive electronics from potentially damaging voltage surges.

---
## Conclusion

The project achieved the main objectives that were outlined at the start of the report. Research into existing surge protection methods helped identify the main design requirements needed to develop a similar protection circuit. Using this information, a circuit was designed using CAD software, simulated to check its behaviour, and then built and tested in the laboratory. The testing showed that the comparator was able to detect when the input voltage exceeded the reference voltage, while the MOSFET and relay switching stage disconnected the protected circuit during these conditions. The laboratory testing also showed behaviour that was very similar to what was observed in the simulation. Overall, the project shows that a simple and low-cost design can provide effective protection, with scope for further improvements and real-world use.
The proposed circuit also shows potential for use in commercial and industrial applications, particularly in systems where sensitive electronics require protection from transient events. Compared to traditional surge protection devices, which often rely on passive components such as MOVs that degrade over time. The developed circuit introduces an active approach by monitoring voltage levels and disconnecting the load when a threshold is exceeded. This provides an additional layer of protection, reducing the risk of component failure under repeated surge conditions. While the current design is implemented at a low-voltage level, the concept could be further developed and scaled for higher voltage systems, making it suitable for integration into control panels and other industrial machines where improved surge protection is required.

---
## Future Improvements

- The trigger circuit could be improved to create a more stable waveform, allowing the protection circuit to switch more clearly, to then improve on the protection circuit further.
- The response time of the circuit could be improved by replacing the relay with faster switching components such as solid-state devices or faster transistors, allowing the circuit to react more quickly to transient voltage spikes.
- The prototype was tested using low-voltage laboratory equipment, so future work could involve scaling the design to operate with higher voltage systems such as mains to better represent real industrial conditions.
- An additional LED indicator could be added on the protected side of the circuit to provide a visual indication when a surge event has occurred.
- The circuit could be further developed for use in specific environments listed in this report such as data centres or telecommunication where protection of sensitive electronics is required.

---
