### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.


**PROGRAM**
```
Developed by:SANTHOSH KUMAR P RegisterNumber:212224040295
```
```
module ex11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```

**RTL LOGIC UP COUNTER**

![image](https://github.com/user-attachments/assets/9e8d611f-caf6-42f3-a322-9b1bcdf454ae)


**TIMING DIAGRAM FOR IP COUNTER**

![image](https://github.com/user-attachments/assets/849ca07d-36c7-4656-8127-17704728e391)

**TRUTH TABLE**

![image](https://github.com/user-attachments/assets/1f0207a5-07f3-4c60-84a5-f8347947ee09)


**RESULTS**

The 4-bit synchronous up-counter was successfully implemented using Verilog in Quartus Prime. The functionality was validated by simulating the counter, which correctly counted up from 0000 to 1111 in binary, incrementing by 1 on each clock pulse. The synchronous nature of the counter ensured that all flip-flops were clocked simultaneously, with each flip-flop toggling based on the state of the preceding flip-flops. The output sequence followed the expected counting pattern, confirming the correct operation of the 4-bit synchronous up-counter.
