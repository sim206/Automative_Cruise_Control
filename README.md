<h1>Automotive Cruise Control Design Analysis</h1>


<h2>Description</h2>

The project focused on the development of a cruise controller, with two distinct parts. In the first part, the report delves into the creation of an optimal control simulation for a car's linearized dynamics under a cruise control system. Seven controller options were evaluated, and the three best controllers were selected. Ultimately, the PI controller with gains Ki = 1.2 and Kp = 0.42 emerged as the optimal choice, effectively functioning within the desired design parameters. The stability of the PI controller was thoroughly assessed using methods such as Routh-Hurwitz, Root Locus, and Bode, confirming its overall stability.

Moving on to the second part, the car dynamics were modeled in Simulink, and the simulation explored the non-linear dynamics of the car operating with the PI controller. Different scenarios were tested by adjusting the car's parameters, examining the robustness of the controller. Phase space plots and gear ratios were compared and analyzed. Additionally, the linearized model was used to investigate the effects of active gains on the error and actuation torque. It was observed that the Kv gain increased control torque while decreasing settling time.

Throughout the report, a critical analysis was conducted, connecting the course material to the cruise controller project in both parts one and two. This analysis aimed to deepen the understanding of the topic and its practical implementation.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Simulink</b> )
- <b>Matlab</b>


<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Project walk-through:</h2>

A cruise control system aims to maintain a steady vehicle speed despite external interferences 
such as environmental factors or incline. This is achieved by measuring the actual vehicle 
speed, comparing it to the reference speed, and altering the throttle according to the control 
law. The following will introduce a basic model of a cruise controller that was modelled in 
Simulink by obtaining the car dynamics and assessing the controllers with respect to the 
design parameters.

</b>
<p align="center">
General Block Diagram for the Car Dynamics: <br/>
<img src="https://i.imgur.com/nbFOaIW.png" height="80%" width="80%" alt="Dynamics"/>
<br />

</b>
<p align="center">
Simulink model of Car dynamics: <br/>
<img src="https://i.imgur.com/m0XbMCG.png" height="80%" width="80%" alt="Dynamics"/>
<br />

**Investigating PID controllers in different variations**

The general trend from this trial and error with testing the controllers concluded that the gains have a significant effect on the performance of the system however the change in slope remained the same at different values. The ideal controller that was chosen was the PI controller as it provided a faster response time than other controllers and was a less complicated system than the PID controller and lowers rise time and error.PID controller would be ideal as it encompasses the advantages of each controller, however, can be an expensive system to implement. A PD controller minimises errors in the output, such as oscillations, overshoot, and rising time. Thus, the three ideal controllers chosen were PI, PD and PID. It should be noted that the damping ζ of the PD controller was overdamped, this was not desirable as the settling time would take longer. However, the PID controller was ζ ≤ 1.

**Assessing the Stability of the PI Controller**

The performance of the PI controller was evaluated using Routh Hurwitz, Root locus and bodeto assess the controller’s performance under various conditions. The Bode plot related the stability through the gain and phase margins, where the gain margin indicated absolute stability until infinity and the phase margin indicated relative stability until 140 degrees as seen. Routh Hurwitz is stable as there are no significant changes in the first column of the array seen. The root locus is determined by the threshold of the criterion, therefore is stable when Ki is greater than 0 and Kp >-0.02 indicated.

</b>
<p align="center">
RH matrix and results: <br/>
<img src="https://i.imgur.com/KUoBOJM.png" height="80%" width="80%" alt="Dynamics"/>
<br />

</b>
<p align="center">
Matlab Root Locus Plot: <br/>
<img src="https://i.imgur.com/qy0tNDG.png" height="80%" width="80%" alt="Dynamics"/>
<br />

</b>
<p align="center">
Matlab Bode Plot: <br/>
<img src="https://i.imgur.com/W9hikqh.png" height="80%" width="80%" alt="Dynamics"/>
<br />

**Part 2**

The next part of the project was to use Simulink to build a simulation of the dynamics of the nonlinear differential equation. The following block diagram was implemented numerically on Simulink.

</b>
<p align="center">
 General Block diagram for Part 2: <br/>
<img src="https://i.imgur.com/L5OLbLv.png" height="80%" width="80%" alt="Dynamics"/>
<br />

</b>
<p align="center">
Parameters: <br/>
<img src="https://i.imgur.com/94nMLzB.png" height="80%" width="80%" alt="Dynamics"/>
<br />

</b>
<p align="center">
Simulink Model for the Dynamics of the Non-Linear Differential Equation: <br/>
<img src="https://i.imgur.com/Ow2bkX2.png" height="80%" width="80%" alt="Dynamics"/>
<br />

Further improvements to this project can be done by choosing the exact parameters for a car and simulating a more realistic incline as the incline implemented on Simulink was a basic MATLAB function that could simulate a basic incline as a disturbance. It would be interesting to look at different types of engines as the engine used in this project was an internal combustion engine and this could be further evaluated in future work to compare the performance between each engine and the controller’s performance.


