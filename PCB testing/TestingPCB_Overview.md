## First PCB Draft design
![First Draft PCB design](<img width="482" height="449" alt="image" src="https://github.com/user-attachments/assets/4dee6163-8a2e-4074-9f0a-399fdda0bf55" />)
 
The image above is the PCB layout design, during testing I realised the capacitor was preventing the comparator from sensing the voltage spikes and causing the system to not work as intended. 

Once the capacitor was removed the circuit behaved a little bit better but the relay constantly switches around the reference voltage. The circuit still works as intended BUT to fully protect the system and stop constant switch Hysteresis is needed to create a broader 'trigger point' for the circuit.

---
## Second PCB Draft design
![Second Draft PCB](<img width="482" height="454" alt="image" src="https://github.com/user-attachments/assets/8e0f9849-b911-4cd2-918a-a768ada3a1a5" />)

Integrated hysteresis and input filtering to improve stability and reduce unwanted switching. During testing the circuit behaved better than the First Draft design, proving that the hysteresis did improve the protection circuit/

Due to lack of time I couldn't fully test the second draft, however it still works and can successfully protect a low level voltage circuit.

Once the second draft is complete I will begin upgrading the circuit to handle mains as this is what this project was originally based on.

---
