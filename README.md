# Lab3Q1
//Verilog code for schematic design. Some variables are different because my quartus was being buggy in class and I just made this code in a whole nother lab called 3A 
module Lab_3A (out, d, d_in, clk, rst);

output [31:0] out;
input d, d_in;
input clk, rst;

reg [31:0] q;

integer index;

always @(posedge clk) begin

 if (rst == 1)   

 q <= 32'h00000000;

 else if (d == 1) begin
 q[31] <= d_in;

 for (index=0; index<=30; index=index+1) begin

 q[index] <= q[index+1];

end

end

end

assign out = q;

endmodule 
