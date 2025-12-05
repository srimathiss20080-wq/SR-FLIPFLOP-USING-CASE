# SR-FLIPFLOP-USING-CASE
**Date:05/12/2025**

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/0f710028-ad52-4d3e-9276-8714cf023a25)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dd90d16c-aec5-4290-a586-e2346b1e9eb5)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/473efad6-d70b-4ca7-aeb7-898bbfca319f)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

/* write all the steps invloved */

**PROGRAM**
Flip flop
-------------------------------------------------
// SR Flip-Flop (with async reset)
```
module sr_ff (
    input  wire clk, rst, S, R,
    output reg  Q
);
    always @(posedge clk) begin
        if (rst)
            Q <= 1'b0;         // Reset
        else begin
            case ({S,R})
                2'b00: Q <= Q;     // No change
                2'b01: Q <= 1'b0;  // Reset
                2'b10: Q <= 1'b1;  // Set
                2'b11: Q <= 1'bx;  // Invalid
            endcase
        end
    end
endmodule
****
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by:Srimathi S
RegisterNumber:25017525
*/

**RTL LOGIC FOR FLIPFLOPS**
<img width="922" height="505" alt="Screenshot 2025-12-05 132550" src="https://github.com/user-attachments/assets/e3ad0bd6-9d40-4fe9-a472-2f97ab0a7535" />


**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1256" height="332" alt="Screenshot 2025-12-05 132617" src="https://github.com/user-attachments/assets/8d5964bf-3af3-4ae5-ad1a-41810e1d89e8" />


**RESULTS**
Thus the SR flipflop using verilog and validating their functionality using their functional tables is implemented and verified.
