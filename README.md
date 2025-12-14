# SHIFT_RESISTER

AIM:

To implement SISO Shift Register using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED: Quartus prime

THEORY

SISO shift Register

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

 <img width="750" height="227" alt="1" src="https://github.com/user-attachments/assets/952d9188-dbf9-4a1a-a994-31c484efa3e1" />
 
Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next. Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

PROGRAM:
```
module shift_register_3bit (
    input  wire clk,     // clock input
    input  wire rst,     // synchronous reset
    input  wire serial_in, // serial data input
    output reg  [2:0] q   // 3-bit register output
);

always @(posedge clk) begin
    if (rst)
        q <= 3'b000;          // reset all bits
    else
        q <= {q[1:0], serial_in}; // shift left
end
endmodule
```
Developed by: HEMA PRIYA

RegisterNumber:25017270

RTL LOGIC FOR SISO Shift Register: [EX 10 Dia.pdf](https://github.com/user-attachments/files/24151301/EX.10.Dia.pdf)


WAVEFORM: <img width="1919" height="934" alt="Screenshot 2025-12-14 130536" src="https://github.com/user-attachments/assets/e2ea5b76-a58c-49dd-810c-40b4b02d6aed" />

RESULT:
Thus,implemented SISO Shift Register using verilog and validating their functionality using their functional tables
