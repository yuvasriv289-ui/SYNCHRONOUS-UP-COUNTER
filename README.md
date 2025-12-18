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

**Procedure**

1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register.

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift.


**PROGRAM**

```module ex11(out, clk,rstn);
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
/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:Yuvasri V
RegisterNumber:25008890
*/

**RTL LOGIC UP COUNTER**
<img width="1018" height="426" alt="d1" src="https://github.com/user-attachments/assets/56db305e-3a12-4f3c-ba9b-1d98a836f47e" />

**TIMING DIAGRAM FOR IP COUNTER**
<img width="1921" height="1201" alt="d2" src="https://github.com/user-attachments/assets/2a1a64d6-8cc9-46c1-b5e7-df1147774b37" />


**TRUTH TABLE**
<img width="544" height="275" alt="d3" src="https://github.com/user-attachments/assets/1d91d8bb-c004-4609-92a6-f8020e6e5978" />


**RESULTS**

 Hence a 4 bit synchronous up counter is implemented correctly.
