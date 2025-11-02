## Setup and Hold Time Requirement

- Setup Time: The minimum amount of time before the clock’s active edge in which data must be 
remained stable in order to latched the latched data correctly.

- Hold Time: The minimum amount of time after the clock’s active edge in which data must be 
remained the stable in order in order to capture the data reliably.

<img width="516" height="186" alt="Screenshot 2025-11-02 113830" src="https://github.com/user-attachments/assets/154b8231-3bf0-41c3-8180-bf8bdaa3fc26" />

## Basics of Clock Signal

<img width="783" height="165" alt="Screenshot 2025-11-02 113855" src="https://github.com/user-attachments/assets/96c84a6d-2d8b-4bac-804a-5d2ab58954e4" />

Digital Clock Signal:
- Having two fixed voltage level on which signal toggles continuously after a fixed time 
interval.
- Most common way to generate the clock signal in digital circuit is Phase Locked Loop 
(PLL). 
- Every sequential element works on clock signal. 
- Latches operation on level of clock, whereas Flip Flops on edge of clock.

Clock Cycle: 
- The smallest part of clock signal, which could generate the entire clock signal by 
repetition of it.

## Edge and Level of Clock Signal

<img width="779" height="179" alt="Screenshot 2025-11-02 113913" src="https://github.com/user-attachments/assets/b3dfbf58-e221-4d17-9f84-4ace4ea8efd5" />

Rising Edge: 
- Where clock toggles from level low to high (or logic 0 to 1)
- It is also called Leading edge / Positive edge.
 
Falling Edge: 
- Where clock toggles from level high to level low (or logic 1 to 0)
- It is also called Trailing edge / Negative edge.

Clock Level: 
- Constant high or constant low level of clock is called level high and level low respectively.
- Latches are level sensitive.

## Clock Period and Frequency

<img width="782" height="223" alt="Screenshot 2025-11-02 113929" src="https://github.com/user-attachments/assets/063d4d84-84f0-4b40-a1c1-74ab6c7c1e97" />

Clock Period (T): 
- The time taken to complete one clock is called clock period. 
- We can also say, the time duration between two conjugate rising edge or two conjugative 
falling edge. 
- Unit: Unit of time (S) [Most commonly used units: us, ns, ps]

Clock Frequency (f): 
- Reciprocal of clock period is called clock frequency. 
- It indicates the number of clock cycle repetition per unit time. 
- In mathematically defined as 𝑓 = 1
 𝑇
  - Unit: Hz [Most commonly used units: MHz, GHz, THz]
 
## Rise Time and Fall Time 

Rise Time:  
- Time requires to rise the clock edge from 10% (or 20%) to 90% (or 80%) of the maximum 
voltage.

<img width="780" height="206" alt="Screenshot 2025-11-02 113945" src="https://github.com/user-attachments/assets/baf944fd-f2cd-48b7-8768-aa9c244488cd" />
  
Fall Time:  
- Time requires to fall the clock edge from 90% (or 80%) to 10% (or 20%) of the maximum 
voltage.

<img width="519" height="275" alt="Screenshot 2025-11-02 113957" src="https://github.com/user-attachments/assets/62057999-05e6-4757-a179-41f069150926" />

## Transition Time and Slew Rate

<img width="474" height="175" alt="Screenshot 2025-11-02 114009" src="https://github.com/user-attachments/assets/3f736b6e-5f6a-4bcc-b6dd-7198dafb5fa9" />

Transition Time:  
- Time requires to change the logic level of a signal either from 0 to 1 or from 1 to 0 is called 
transition time.

Slew Rate:  
- Rate of change of logic level (voltage) with time during the transition of signal is called 
the slew rate. 
- Higher the slew rate, steeper the transition.

<img width="780" height="134" alt="Screenshot 2025-11-02 114024" src="https://github.com/user-attachments/assets/4c3d3560-25bd-411e-8cfc-3bd5f4a19822" />

## Pulse Width

- The time difference between rising edge and falling edge of clock is called the pulse width. 
- To make accurate measurement, we consider 50% voltage level of point as reference in 
raising and falling edge.

<img width="780" height="287" alt="Screenshot 2025-11-02 114040" src="https://github.com/user-attachments/assets/c4f1f7f1-d75f-4452-95b0-97554b72f653" />

## Duty Cycle in Cycle Signal 

Duty cycle is defined as the ratio of on time of clock (pulse width) to the clock period. 
Generally, it is defined as in form of percentage of on time to clock period. 

```
Duty Cycle (%) = Pulse Width * Frequency * 100
```

<img width="778" height="287" alt="Screenshot 2025-11-02 114055" src="https://github.com/user-attachments/assets/884517e0-8192-4fc0-9908-53d95306c87a" />

## Jitter in Clock Signal

<img width="698" height="204" alt="Screenshot 2025-11-02 114109" src="https://github.com/user-attachments/assets/536220cc-bbf7-4431-9da9-2f99125967ee" />

Jitter is the short-term variation of clock period, which leads the deviation of clock edge 
from its ideal position. Or we can say it is the inability of clock source to produce a clean 
edge of clock.
- Jitter could be either positive or negative. 
- Jitter can impact the timing analysis. 
- To model the effect of Jitter we apply clock uncertainty in timing analysis.

<img width="690" height="196" alt="Screenshot 2025-11-02 114124" src="https://github.com/user-attachments/assets/18b5a125-d1dc-46d9-b58a-97b88afdb2df" />

## Clock Latency 

Clock Latency is the time required to reach the clock signal from the clock source pin to the sink pin / destination pin. 

<img width="671" height="405" alt="Screenshot 2025-11-02 114136" src="https://github.com/user-attachments/assets/d33b68e7-758c-4f3b-88de-6b968b7fc858" />

Note: But in practically it is not possible because clock signal travel through clock net and every 
segment of the clock net has some resistance and capacitance if there is a resistance and 
capacitance there will occur net delay. For this consequence delay occur between at clock source and at sink.

<img width="495" height="303" alt="Screenshot 2025-11-02 114146" src="https://github.com/user-attachments/assets/440f2e23-b2f7-4389-b9bc-233c8a902528" />

Clock latency due to clock tree buffer / inverter cell delay plus the clock net delay.

## Source Latency & Network Latency

Clock latency further could be divided into parts: 
1. Source Latency 
2. Network Latency

Source Latency:  
• The time required to reach the clock signal to clock definition point from the clock source 
point is called source latency. 

Network Latency: 
• The time required to reach the clock signal to the sink pin from the clock definition point 
is called network latency. 
• Insertion delay is same as network latency.

<img width="668" height="418" alt="Screenshot 2025-11-02 114202" src="https://github.com/user-attachments/assets/e4b7baa9-6d30-4e13-874e-49579826564f" />

```
Clock Latency = Source Latency + Network Latency 
```

## Latency in SDC file 

Clock latency information is provided in SDC file through the SDC command. 
set_clock_latency 

Example: 
• Set network latency 

```
set_clock_latency <value> [get_clocks <clock_name>] 
set_clock_latency 0.8 [get_clocks coreCLK]
```
• Set source latency 

```
set_clock_latency <value> [get_clocks <clock_name>] -source 
set_clock_latency 1.2 [get_clocks coreCLK] -source
```

<img width="778" height="302" alt="Screenshot 2025-11-02 114215" src="https://github.com/user-attachments/assets/11587420-5d8b-49ca-98c7-a21f6ac34a8b" />

Data Path:  
- The path through which data travels from input pin to output pin of block. 
Clock Path: 
- The path through which clock is being distributed to all sequential elements in the design 
from the clock source. 

## Launch Clock Path and Capture Clock Path

Launch Clock Path:  
- The clock path from the common point to the launch flop is called launch clock path.

Capture Clock Path: 
- The clock path from the common point to the capture flop is called capture clock path.

<img width="631" height="383" alt="Screenshot 2025-11-02 114230" src="https://github.com/user-attachments/assets/4cb60def-d259-4eef-befd-28a53266e474" />

## Launch Flop and Capture Flop

- In reference of reg2reg path, Data is being launched by FF1 on a positive edge of the clock 
and it will travel through the combinational path and finally will be captured by FF2 on the 
next clock edge by default. 
- The flop which launches the data (FF1) is called launch flop and the flop which captures 
the data (FF2) is called capture flop. 
- In a path group it is not necessary that both end of path will always have a register (e.g: 
in2reg, reg2out, reg2mem) 
- In such cases instead of saying launch and capture flop, they are generally called by start 
point and end point.

<img width="610" height="309" alt="Screenshot 2025-11-02 114245" src="https://github.com/user-attachments/assets/d131c85a-16a1-40cd-9106-5dcbda027b10" />

## Clock to Q Delay

- The moment when active edge of clock reaches the flip flop, data is not being launched 
instantly. It takes some fixed amount of time to launch the data. 
- The delay between arrival of active edge of clock and data launch is called Clock-to-Q 
delay.

<img width="602" height="321" alt="Screenshot 2025-11-02 114257" src="https://github.com/user-attachments/assets/9b8b12da-8d47-4b66-8140-f0b17a4f5495" />

```
Data arrival time = Clock-to-Q delay + Combinational path delay
```

## Net Delay and Cell Delay

- Each cell has some specific propagation delay defined in the lib file for different process 
corners. 
- A net is combination of R and C, so each segment of net has some delay which is called 
delay. 
- Net delay variation is based on RC corners. 
- A combinational path delay is sum of cell delays on the path and net delays.

<img width="778" height="202" alt="Screenshot 2025-11-02 114310" src="https://github.com/user-attachments/assets/a70ae338-cb89-4f6a-87b7-183842d50aec" />

## Clock Skew

- Clock skew could be defined as the difference of arrival time of clock edge in two 
sequential elements. 
- It is the difference in latency of two sequential elements. 
- Clock skew is mainly because of difference in length of clock paths and amount of buffer 
/ inverter added in clock tree. 
- Ideally zero skew is expected after CTS, but in practical we provide a constraint of 
maximum skew.

<img width="755" height="338" alt="Screenshot 2025-11-02 114333" src="https://github.com/user-attachments/assets/05eda2ee-5897-44a6-a930-3ec7a3d3ca09" />

```
Clock Skew = Latency of FF2 (L2) – Latency of FF1(L1)
```

## Positive and Negative Clock Skew

- If there is timing path between two synchronous elements, then clock skew can be 
defined as: 
Clock Skew = Clock latency at capture flop – Clock latency at launch flop 
- Clock skew could be either positive, negative or zero.

<img width="365" height="266" alt="Screenshot 2025-11-02 114344" src="https://github.com/user-attachments/assets/21bb3533-5484-4079-9f10-cda6ad6660a1" />

Positive Skew: 
- Capture flop latency is greater than the launch flop latency.

<img width="457" height="239" alt="Screenshot 2025-11-02 114412" src="https://github.com/user-attachments/assets/d4abaa70-c108-4c41-87e3-4691b660ce10" />

Negative Skew: 
- Capture flop latency is lesser than the launch flop latency.

<img width="459" height="219" alt="Screenshot 2025-11-02 114426" src="https://github.com/user-attachments/assets/d2ef08ae-1e16-4b2b-b6a4-75fec7a1167f" />

## Local and Global Skew

Local Skew: 
- The difference in clock arrival time of two related flops is called local skew.

Global Skew: 
- The difference of maximum latency and minimum latency in the design between two 
non-related flops is called the global skew

<img width="514" height="374" alt="Screenshot 2025-11-02 114437" src="https://github.com/user-attachments/assets/e7cb3b1d-d3cc-47af-b800-4d1b14f49715" />

## Clock Uncertainity

<img width="536" height="285" alt="Screenshot 2025-11-02 114450" src="https://github.com/user-attachments/assets/0e906642-82f0-4590-9b00-b929d8ff5227" />

- In practice no clock source could be so ideal that it is free from jitter, there is always 
some variation in clock period in the source of clock itself.

- Ideally source clock:

<img width="780" height="94" alt="Screenshot 2025-11-02 114501" src="https://github.com/user-attachments/assets/8a9a133e-c8ed-46fe-853e-c7b9cbd9d742" />

- In Pratical source clock:

<img width="782" height="126" alt="Screenshot 2025-11-02 114512" src="https://github.com/user-attachments/assets/ca84b027-f0d0-4181-90e7-c435498cd3f3" />

There is always some skew in a clock tree, so launch and capture flop will get the clock edge at different point of time. 

<img width="780" height="117" alt="Screenshot 2025-11-02 114523" src="https://github.com/user-attachments/assets/1958aebd-664e-4c91-96da-3ebfaa5b095a" />

Clock tree may suffer from many variations (like: Crosstalk, IR, Process Variation etc) which 
can affect the clock tree delay of individual clock paths. These variations may vary the clock edge arrival time at sink pin.

## Factors we should take care about clock uncertainty

PreCTS Stage: 
```
• Setup Uncertainty: Jitter + Skew + Setup Margin 
• Hold Uncertainty: Skew + Hold Margin
```

PostCTS Stage: 
```
• Setup Uncertainty: Jitter + Setup Margin 
• Hold Uncertainty: Hold Margin
```

<img width="531" height="284" alt="Screenshot 2025-11-02 114536" src="https://github.com/user-attachments/assets/93d9253e-f8df-4d9b-9df7-491ef0fd892b" />

<img width="742" height="334" alt="Screenshot 2025-11-02 114551" src="https://github.com/user-attachments/assets/bf8a8f11-4a67-49bc-a408-63a423e040fa" />

Set Clock Uncertainty (How to define clock uncertainty): 

- set_clock_uncertainty 
```
set_clock_uncertainty -setup 0.15 [get_clock clk_core] 
set_clock_uncertainty -hold 0.05 [get_clock clk_core]
```

<img width="466" height="175" alt="Screenshot 2025-11-02 114700" src="https://github.com/user-attachments/assets/97651ae2-8103-4e55-819e-30b061099377" />

- Setup analysis (AAT <RAT):
```
Required Arrival Time = T + Skew – Setup Uncertainty – Setup 
Required Arrival Time = 1000ps +100ps – 150ps – 30ps
```
```
Hold analysis (AAT > RAT): 
Required Arrival Time = Hold Time + Skew + Hold Uncertainty 
Required Arrival Time = 20ps +100ps +50ps
```

## Latch and Flip Flop

Latch: 

<img width="482" height="228" alt="Screenshot 2025-11-02 114714" src="https://github.com/user-attachments/assets/37e4e7cd-6d86-4bb3-a73e-aceea23618b7" />

Flip Flop: 

<img width="712" height="225" alt="Screenshot 2025-11-02 114730" src="https://github.com/user-attachments/assets/e95c34a7-ce7a-46b1-826f-8d074eb731b1" />

Latch and Flip Flop in Transistor Level:

<img width="766" height="321" alt="Screenshot 2025-11-02 114747" src="https://github.com/user-attachments/assets/a742d4b4-74d2-4897-b85b-f67c0455a514" />

Functions of Latch:

<img width="655" height="447" alt="Screenshot 2025-11-02 114759" src="https://github.com/user-attachments/assets/cf5238b0-b177-4b51-b3be-e20cc732f6f4" />

Latch Operation Table

| Level | Latch Type | Q Behavior | State | Description | Previous Stage |
|:------|:------------|:-----------|:-------|:-------------|:----------------|
| High  | Transparent | Q = D | Transparent | Output follows input | D |
| Low   | Opaque | Q holds previous value | Latched | Output is held constant | Previous Stage |

Functions of Flip Flop:

<img width="779" height="371" alt="Screenshot 2025-11-02 114814" src="https://github.com/user-attachments/assets/58b25210-f5f8-4d6a-af82-3fde81c82ece" />

Example:

<img width="780" height="313" alt="Screenshot 2025-11-02 114832" src="https://github.com/user-attachments/assets/03d04f3f-2810-4725-aabf-4bc42652f93b" />

| **Properties** | **Latch** | **Flip-Flop** |
|:----------------|:-----------|:---------------|
| **Transistor Counts** | Less | More (approximately double) |
| **Propagation Delay** | Less | More |
| **Operation** | Works on **level** of clock | Works on **edge** of clock |
| **Types** | Positive / Negative **level** sensitive | Positive / Negative **edge** sensitive |
| **Process Variation Sensitivity** | Less prone to process variation | More prone to process variation |
| **Use** | Used as a **lockup latch** and in **high-speed ASICs** | Commonly used in **registers** |

## Setup & Hold Time Requirement inside Latch 

Internal Structure & Operation:

<img width="780" height="380" alt="Screenshot 2025-11-02 114848" src="https://github.com/user-attachments/assets/7fce3e6c-49ea-4d60-8066-895873045f2e" />

<img width="778" height="425" alt="Screenshot 2025-11-02 114900" src="https://github.com/user-attachments/assets/3d03bd18-755a-4956-830d-09fd21c6fe37" />

Need of Internal Setup & Hold Timings:

<img width="779" height="508" alt="Screenshot 2025-11-02 114933" src="https://github.com/user-attachments/assets/8db224ad-db16-4134-a4c8-5c7db461a76c" />

<img width="778" height="407" alt="Screenshot 2025-11-02 114950" src="https://github.com/user-attachments/assets/43af4350-c4b5-43fc-9c57-b0fe457805e2" />

<img width="782" height="372" alt="Screenshot 2025-11-02 115003" src="https://github.com/user-attachments/assets/54c37cc1-bacd-40af-9567-369887dacea2" />

<img width="780" height="392" alt="Screenshot 2025-11-02 115016" src="https://github.com/user-attachments/assets/e13d111a-c0b2-4f06-bb22-8f2c83216a8a" />

## CPPR: Common Path Pessimism Removal

Common Clock Path: 

<img width="778" height="354" alt="Screenshot 2025-11-02 115031" src="https://github.com/user-attachments/assets/09396cbf-5e69-4785-8a4a-da7b332f707a" />

Common Path Pessimism:

<img width="778" height="392" alt="Screenshot 2025-11-02 115050" src="https://github.com/user-attachments/assets/e24471ee-f447-484a-880f-c58683a9f657" />

<img width="779" height="393" alt="Screenshot 2025-11-02 115106" src="https://github.com/user-attachments/assets/a329cdee-9433-4d3c-b5d8-cfca6ecb0339" />

<img width="780" height="391" alt="Screenshot 2025-11-02 115119" src="https://github.com/user-attachments/assets/7377cb0d-f801-4c77-834d-5e6fd7a620de" />

