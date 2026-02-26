# SSB

EXP NO: 3	SSB-SC-AM MODULATION using SCILAB

AIM:

To write a program to perform SSBSC modulation and demodulation using SCI LAB and study its spectral characteristics

EQUIPMENTS REQUIRED

•	Computer with i3 Processor

•	SCI LAB

Note: Keep all the switch faults in off position


Algorithm
1.	Define Parameters:
•	Fs: Sampling frequency.
•	T: Duration of the signal.
•	Fc: Carrier frequency.
•	Fm: Frequency of the message signal.
•	Amplitude: Maximum amplitude of the message signal.
2.	Generate Signals:
•	Message Signal: The baseband signal that will be modulated.
•	Carrier Signal: A high-frequency signal used for modulation.
•	Analytic Signal: Constructed using the Hilbert transform to get the in-phase and quadrature components.
3.	SSBSC Modulation:
•	Modulated Signal: Create the SSBSC signal using the in-phase and quadrature components, modulated by the carrier.
4.	SSBSC Demodulation:
•	Mixing: Multiply the SSBSC signal with the carrier to retrieve the message signal.
•	Low-pass Filtering: Apply a low-pass filter to remove high-frequency components and recover the original message signal.
5.	Visualization:
•	Plot the message signal, carrier signal, SSBSC modulated signal, and the recovered signal after demodulation.


PROCEDURE

•	Refer Algorithms and write code for the experiment.
•	Open SCILAB in System
•	Type your code in New Editor
•	Save the file
 
•	Execute the code
•	If any Error, correct it in code and execute again
•	Verify the generated waveform using Tabulation and Model Waveform

Model Waveform

<img width="704" height="178" alt="image" src="https://github.com/user-attachments/assets/32ee29b3-0d95-4192-9762-972d50c05c90" />
<img width="706" height="167" alt="image" src="https://github.com/user-attachments/assets/bff0d8fd-d679-444e-af37-0b34585853c1" />

Program
```
am1=3.2;
ac1=6.4;
fm1=154;
fc1=1540;
fs1=15400;
t1=0:1/fs1:2/fm1;
em1=am1*cos(2*3.14*fm1*t1);
subplot(4,1,1);
plot(t1,em1);
ec1=ac1*cos(2*3.14*fc1*t1);
subplot(4,1,2);
plot(t1,ec1);
eam1=ac1*(1+(em1/ac1)).*cos(2*3.14*fc1*t1);
eam2=ac1*(-1+(em1/ac1)).*cos(2*3.14*fc1*t1);
edsbsc1=eam1+eam2;
am2=3.2;
ac2=6.4;
fm2=154;
fc2=1540;
fs2=15400;
t2=0:1/fs2:2/fm2;
em2=am2*sin(2*3.14*fm2*t2);
ec2=ac2*sin(2*3.14*fc2*t2);
eam3=ac2*(1+(em2/ac2)).*sin(2*3.14*fc2*t2);
eam4=ac2*(-1+(em2/ac2)).*sin(2*3.14*fc2*t2);
edsbsc2=eam3+eam4;
elsb=edsbsc1 - edsbsc2;
subplot(4,1,3);
plot(t,elsb);
eusb=edsbsc1 + edsbsc2;
subplot(4,1,4);
plot(t,eusb);
```

OUTPUT WAVEFORM

TABULATION

<img width="1280" height="722" alt="image" src="https://github.com/user-attachments/assets/2994bbc9-e455-42e6-8379-0f7719992bda" />

RESULT:

Thus, the SSB-SC-AM Modulation and Demodulation is experimentally done and the output is verified.





