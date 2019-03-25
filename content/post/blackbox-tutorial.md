---
title: "Blackbox Tutorial"
date: 2019-03-25T14:21:27-04:00
draft: true
---

I've created this tutorial for first year undergraduate students at Ryerson University attending ELE202. This forum will allow students to communicate doubts using the Disqus comments feature. 

There are four possible combinations in the black box:
* RC Series
* RC Parallel
* RL Series
* RL Parallel

We will use AC analysis to figure out which of the four combinations is
inside the black box and also, what the values of the components are.

### Step 1: Build the circuit
![Set up circuit in series with a test resistor of your choice. I've chosen $20 \Omega$.](static/imgs/blackbox/setup.jpg)

![Add in the oscilloscope probes.](static/imgs/blackbox/probes.jpg)

### Step 2: Determine RC or RL

By setting up the circuit as depicted in Figure 2, CH1 on the oscilloscope corresponds to the voltage signal $V_1$ across the black box and CH2 corresponds to the voltage signal $V_2$ across the test resistor. However, we require a 'current' signal to do AC analysis and so we denote CH2 to be the current signal of the black box by dividing $V_2$ by the value of the resistor.

Therefore, CH1 = $V_1$ = $V_{bb}$ and CH2 = $\frac{V_2}{Test Resistor}$ = $I_{bb}$.\\ 

To determine if the circuit in the black box is an RC or RL, we observe which of the signals $V_{bb}$ or $I_{bb}$ are leading.\\

#### Case 1
If the oscilloscope output resembles Figure 1, then the current signal leads the voltage signal and therefore, we have a capacitive circuit (RC). 

#### Case 2
If the oscilloscope output resembles Figure 2, then the voltage signal leads the current signal and therefore, we have an inductive circuit (RL).
![]()
### Step 3: Determine Series or Parallel

Once we know if the blackbox configuration is RC or RL, we have reduced the four choices to only two. To figure out if the circuit inside the black box is series or parallel, we can simply increase the frequency of the function generator's AC signal and observe the behavior of the phase difference between the $V_{bb}$ and $I_{bb}$ signals.

#### Case 1: Phase Angle Decreases
If on increasing the source frequency, the phase angle decreases, the circuit must be either an RC series or an RL parallel. 

##### Why RC Series?
When we increase the frequency, the impedance of the capacitor $Z_C$ is affected while the impedance of the resistor $Z_R$ stays the same. As we keep increasing the frequency $f$, we observe that the capacitor's impedance effectively becomes a short circuit denoted by zero impedance in Equation \ref{eqn:rc_impedance}. Since $Z_C$ approaches a short circuit, the black box impedance becomes \textit{purely resistive}, as expressed in Equation \ref{eqn:rcseries} and therefore the voltage signal $V_{bb}$ will be in phase with the current signal $I_{bb}$. 

![]()
(Recall, purely resistive circuits do not have any phase difference between their signals). Therefore, increasing the source frequency will reduce the phase angle between the voltage and current signals.