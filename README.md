<h1>EKG Design</h1>
<h2>Description</h2>
This is my attempt at designing a lightweight EKG machine from scratch. 

<h2>Schemetic</h2>
<img width="570" alt="EKG_schem" src="https://github.com/user-attachments/assets/6b83ed2b-61d0-4dab-9994-3aac9c9dace0">
<h3>Power Supply</h3>
Power supply uses 5V->3.3v voltage regulator with decoupling capacitors attached to input and output. 
<h3>Reference Voltage</h3>
This circuit halves the supply output voltage through the means of voltage divider and  buffer using an op amp. 
<h3>Filtering/Pre-Amplifying Stage</h3>
This stage tries to suppress as much noise present in the inputs before sending them into an instrumentation op amp, cancelling out any common bias present in both inputs and amplifying the output a certain factor(depends on the mountable resistors) 
<h3>Active Filter/Amplifier</h3>
Here, I've designed an active bandpass filter, thus picking out the frequencies only relavant to typical electrocardiac signals(around 1Hz-50Hz). The Amplifier thus then amplify the "clean" signal by the factor of 10. 
*It is imporant to put the amplifier after the bandpass filter, as putting it before will amplify unncessary signals, thus leading to more consumption of power of the circuit. 
<h3>Pin connector</h3>
It uses the typical female 3 leg 3.5mm audio connector. The electrodes with the appropriate male connector will be connected to it. 
  
<h2>PCB Design</h2>
<img width="668" alt="ekg_pcb" src="https://github.com/user-attachments/assets/dcedaf93-6d46-499c-8066-35a59a329e05">
<h3>Description</h3>
This PCB design utilizes the 4 layer structure, where the second layer is used for copper pour for power and the third layer for ground to reduce parasitic impedances. This also provides more room for the signal routes. This is a simpler and more robust design compared to the conventional 2 layer structure.


<h2>3D Model</h2>
<img width="538" alt="ekg_3d" src="https://github.com/user-attachments/assets/90800536-8bd3-48d0-ae00-d5a75385412b">

<h2>Final Product</h2>
<img src="https://github.com/user-attachments/assets/c81cefa6-25c9-413a-9d58-191339361807">

<h2>Obstacles</h2>
<h3>Reference Voltage isn't exact</h3>
I have expected the Rereference voltage to be exactly half of the output voltage 3.3V, but it happened to be significantly higher(more in the 2V region)

<h3>Difficulty getting the amplification right</h3>
I have decided to use mountalbe resistors in the preamplifying stage, in order to test out different amplification factors, but even with this foreseen mitigation, I was not able to get the desired amount of amplification. 

<h3>Possible Stability problems</h3>
An overshoot in voltages was observed in different parts of the circuit. I was not able determine whether this was due to the inherent instability of the circuit, or due to the false handling of PLI(power line interference).

<h3>Power line intereference</h3>
In regard to PLI, one possible solution would be to add a RLD(right leg drive) circuit, thus cancelling out the effects of the power line by feeding the body with destructive voltage. 

<h3>Putting the electrodes on the right spot</h3>
Another possible problem could've been simply that I havn't placed the electrodes in the optimal areas of skin, causing them to not be able to pick up valuable signals. 

<h2>Conclusion</h2>
This circuit has been proven thus far unable to perform practical functions of an ekg and it which should be further developed with various mitigations to the obstacles mentioned above.  

