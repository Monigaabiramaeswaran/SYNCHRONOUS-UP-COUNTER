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

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

**PROGRAM**
```

module up_counter (out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
	if(!rst)
		out<=0;
	else 
		out <= out+1;
end
endmodule
```
```
module down_counter (out,clk,rst);

input clk,rst; 

output reg [3:0]out;

always @ (posedge clk)

begin

if(!rst)

out<=4'b1111;

else 

out <= out-1;

end

endmodule
```
Developed by:MONIGA.A
RegisterNumber:25017526
*/

**RTL LOGIC UP COUNTER**
UP COUNTER
![WhatsApp Image 2025-12-18 at 9 14 57 AM](https://github.com/user-attachments/assets/b90ab5b4-cbc0-48ef-bc69-1722998f99ae)

DOWN COUNTER
![WhatsApp Image 2025-12-18 at 9 16 13 AM](https://github.com/user-attachments/assets/93815e7e-32d5-4792-b420-d09c8c7c9a7a)

**TIMING DIAGRAM FOR IP COUNTER**
UP COUNTER

![WhatsApp Image 2025-12-18 at 9 15 33 AM](https://github.com/user-attachments/assets/b6c86bee-5375-4ecf-b47a-d73632a1af40)

DOWN COUNTER

![WhatsApp Image 2025-12-18 at 9 16 17 AM](https://github.com/user-attachments/assets/3d830aaf-6644-430a-95b5-2d7f49363267)

**TRUTH TABLE**
![WhatsApp Image 2025-12-18 at 9 17 12 AM](https://github.com/user-attachments/assets/cce080c1-8e05-4a0e-9c73-de12a02e409b)


**RESULTS**
