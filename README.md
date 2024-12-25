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
tep 1: Initialize the Counter
Initialize the counter with n bits, where n is the number of bits in the counter. Set all bits to 0.

Step 2: Receive Clock Pulse
Receive a clock pulse (CLK) from the clock source.

Step 3: Check Enable Signal
Check the enable signal (EN). If EN is 0, go to step 6.

Step 4: Increment Counter
If EN is 1, increment the counter by 1. This is done by adding 1 to the current count.

Step 5: Update Counter Outputs
Update the counter outputs (Qn-1, Qn-2, ..., Q0) to reflect the new count.

Step 6: Repeat
Repeat steps 2-5 for each clock pulse.



**PROGRAM**

module EXP11(out,clk,rst);

input clk,rst;

output reg [3:0]out;

always @ (posedge clk)

begin

   if(rst)
   
     out<=0;
   
   else 
   
     out <= out+1;
end

endmodule




Developed by:D.MEAGESWAR RegisterNumber:24900815


**RTL LOGIC UP COUNTER**
![Screenshot 2024-12-25 152559](https://github.com/user-attachments/assets/44075234-1de9-4e35-aa2c-3f19c20c7ad5)


**TIMING DIAGRAM FOR IP COUNTER**
![Screenshot 2024-12-25 152855](https://github.com/user-attachments/assets/3f25c70d-6318-47e6-b1f7-5563fffc05a1)



**RESULTS**

Thus the program exceeded sucessfully
