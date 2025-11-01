## Setup and Hold Time Requirement

- Setup Time: The minimum amount of time before the clock’s active edge in which data must be 
remained stable in order to latched the latched data correctly.

- Hold Time: The minimum amount of time after the clock’s active edge in which data must be 
remained the stable in order in order to capture the data reliably.

## Basics of Clock Signal

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

## Edge and Level of Clock Signal:

Rising Edge: 
- Where clock toggles from level low to high (or logic 0 to 1)
- It is also called Leading edge / Positive edge.
 
Falling Edge: 
- Where clock toggles from level high to level low (or logic 1 to 0)
- It is also called Trailing edge / Negative edge.

Clock Level: 
- Constant high or constant low level of clock is called level high and level low respectively.
- Latches are level sensitive.

## Clock Period and Frequency: 

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
 
## Rise Time and Fall Time: 

Rise Time:  
- Time requires to rise the clock edge from 10% (or 20%) to 90% (or 80%) of the maximum 
voltage.
  
Fall Time:  
- Time requires to fall the clock edge from 90% (or 80%) to 10% (or 20%) of the maximum 
voltage.

## Transition Time and Slew Rate: 

Transition Time:  
- Time requires to change the logic level of a signal either from 0 to 1 or from 1 to 0 is called 
transition time.

Slew Rate:  
- Rate of change of logic level (voltage) with time during the transition of signal is called 
the slew rate. 
- Higher the slew rate, steeper the transition.

## Pulse Width:

- The time difference between rising edge and falling edge of clock is called the pulse width. 
- To make accurate measurement, we consider 50% voltage level of point as reference in 
raising and falling edge.

## Duty Cycle in Cycle Signal: 

Duty cycle is defined as the ratio of on time of clock (pulse width) to the clock period. 
Generally, it is defined as in form of percentage of on time to clock period. 

## Jitter in Clock Signal:

Jitter is the short-term variation of clock period, which leads the deviation of clock edge 
from its ideal position. Or we can say it is the inability of clock source to produce a clean 
edge of clock.
- Jitter could be either positive or negative. 
- Jitter can impact the timing analysis. 
- To model the effect of Jitter we apply clock uncertainty in timing analysis.

## Clock Latency 

Clock Latency is the time required to reach the clock signal from the clock source pin to the sink 
pin / destination pin. 
Note: But in practically it is not possible because clock signal travel through clock net and every 
segment of the clock net has some resistance and capacitance if there is a resistance and 
capacitance there will occur net delay. For this consequence delay occur between at clock source 
and at sink.

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

Clock Latency = Source Latency + Network Latency 

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

# Launch Flop and Capture Flop

- In reference of reg2reg path, Data is being launched by FF1 on a positive edge of the clock 
and it will travel through the combinational path and finally will be captured by FF2 on the 
next clock edge by default. 
- The flop which launches the data (FF1) is called launch flop and the flop which captures 
the data (FF2) is called capture flop. 
- In a path group it is not necessary that both end of path will always have a register (e.g: 
in2reg, reg2out, reg2mem) 
- In such cases instead of saying launch and capture flop, they are generally called by start 
point and end point.

## Clock to Q Delay

- The moment when active edge of clock reaches the flip flop, data is not being launched 
instantly. It takes some fixed amount of time to launch the data. 
- The delay between arrival of active edge of clock and data launch is called Clock-to-Q 
delay.

Data arrival time = Clock-to-Q delay + Combinational path delay

## Net Delay and Cell Delay

- Each cell has some specific propagation delay defined in the lib file for different process 
corners. 
- A net is combination of R and C, so each segment of net has some delay which is called 
delay. 
- Net delay variation is based on RC corners. 
- A combinational path delay is sum of cell delays on the path and net delays.

## Clock Skew

- Clock skew could be defined as the difference of arrival time of clock edge in two 
sequential elements. 
- It is the difference in latency of two sequential elements. 
- Clock skew is mainly because of difference in length of clock paths and amount of buffer 
/ inverter added in clock tree. 
- Ideally zero skew is expected after CTS, but in practical we provide a constraint of 
maximum skew. 
- Clock Skew = Latency of FF2 (L2) – Latency of FF1(L1)

## Positive and Negative Clock Skew

- If there is timing path between two synchronous elements, then clock skew can be 
defined as: 
Clock Skew = Clock latency at capture flop – Clock latency at launch flop 
- Clock skew could be either positive, negative or zero.

Positive Skew: 
- Capture flop latency is greater than the launch flop latency. 

Negative Skew: 
-- Capture flop latency is lesser than the launch flop latency.

## Local and Global Skew

Local Skew: 
- The difference in clock arrival time of two related flops is called local skew. 
Global Skew: 
- The difference of maximum latency and minimum latency in the design between two 
non-related flops is called the global skew

