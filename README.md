<pre>Name - Shubh Mittal
Roll no - 24293916051
2nd year, 3rd sem, CSE-A</pre>

<pre>Here are the codes of verilog:</pre>
________________________________________________________________________________________________________________________________________

</h4>1. Logic Gates:</h4>
  
<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre> `timescale 1ns / 1ps
module gates(
    input a,b,
    output _and , _not , _or , _xor, _xnor, _nand, _nor
    );
assign _and = a & b;
assign _not = (~a);
assign _or = a | b;
assign _xor = a ^ b;
assign _xnor = a ~^ b;
assign _nor = ~(a | b);
assign _nand = ~(a & b);
endmodule
</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps
module gates_test(

    );
reg a,b;
wire _and , _not , _or , _xor, _xnor, _nand, _nor;
gates uut(a,b,_and , _not , _or , _xor, _xnor, _nand, _nor);
initial begin
a=0;
b=0;
#10
a=0;
b=1;
#10
a=1;
b=0;
#10
a=1;
b=1;
#10
$finish;
end
endmodule
</pre>

Schematic:
![gates_schematic](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/Gates_schematic.png)
   
Simulation:
![gates_stimulation](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/gates_Stimulation.png)
________________________________________________________________________________________________________________________________________

<h4>2. Boolean Expression:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps
    module boolean_expression(
input a, b,
    output y
    );
assign y = (a ^ b) & (a ~^ b) | (a & b);
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps
module boolean_expression_test(

    );
reg a,b;
wire y;
boolean_expression uut(a,b,y);
initial begin
a=0;b=0;#10
a=0;b=1;#10
a=1;b=0;#10
a=1;b=1;#10
$finish;
end
endmodule
</pre>

Schematic:
![Boolean](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/Boolean_expression_schematic.png)
  
Simulation:
![Boolean](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/boolean_expression_stimulation.png)
________________________________________________________________________________________________________________________________________

<h4>3. Mux 2x1:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>
  
<pre>`timescale 1ns / 1ps
module mux_2x1(
    input a,b,s,
    output y
    );
assign y=((~s)&a) | (s&b);
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps
module mux_test(

    );
reg a,b,s;
wire y;
mux_2x1 uut(a,b,s,y);
initial begin
a=0;
b=0;
s=0;
#10
a=0;
b=0;
s=1;
#10
a=0;
b=1;
s=0;
#10
a=0;
b=1;
s=1;
#10
a=1;
b=0;
s=0;
#10
a=1;
b=0;
s=1;
#10
a=1;
b=1;
s=0;
#10
a=1;
b=1;
s=1;
#10
$finish;
end
endmodule
</pre>

Schematic:
![mux s](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/mux2x1_schematic.png)

Simulation:
![mux](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/mux2x1_stimulator.png)

________________________________________________________________________________________________________________________________________

<h4>4. 4 to 2 Priority Encoder:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps
module priority_encoder(
input a,b,c,d,
output l,m,v
    );
assign l=c | b;
assign m=c | ((~b)&a);
assign v=(a | b) | (c | d);
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps
module priority_encoder_test(

    );
reg a,b,c,d;
wire l,m,v;
priority_encoder uut(a,b,c,d,l,m,v);
initial begin
a=0;b=0;c=0;d=0; #10
a=0;b=0;c=0;d=1; #10
a=0;b=0;c=1;d=0; #10
a=0;b=0;c=1;d=1; #10
a=0;b=1;c=0;d=0; #10
a=0;b=1;c=0;d=1; #10
a=0;b=1;c=1;d=0; #10
a=0;b=1;c=1;d=1; #10
a=1;b=0;c=0;d=0; #10
$finish;
end
endmodule</pre>

Schematic:
![encoder](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/priorityenc_schematic.png)

Simulation:
![Encoder](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/priority_enc_stimulation.png)
________________________________________________________________________________________________________________________________________

<h4>5. 2 to 4 Decoder:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps
module decoder(
input a,b,
output l,m,n,o
    );
assign l=(~a)&(~b);
assign m=(~a)&b;
assign n=a&(~b);
assign o=a&b;
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps
module decoder_test(

    );
reg a,b;
wire l,m,n,o;
decoder uut(a,b,l,m,n,o);
initial begin
a=0;b=0;#10
a=0;b=1;#10
a=0;b=1;#10
a=1;b=1;#10
$finish;
end
endmodule</pre>

Schematic:
![Decoder](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/decoder_schematic.png)

Simulation:
![Decoder1](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/decoder_stimulation.png)
________________________________________________________________________________________________________________________________________

<h4>6. Half Adder:</h4>
     
<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps
module half_adder(
    input a,b,
    output sum,carry
    );
assign sum=a^b;
assign carry=a&b;
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps
module half_adder_test(

    );
reg a,b;
wire sum,carry;
half_adder uut(a,b,sum,carry);
initial begin
a=0;b=0;#10
a=0;b=1;#10
a=1;b=0;#10
a=1;b=1;#10
$finish;
end
endmodule</pre>

Schematic:
![Half Adder](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/half_adder_schematic.jpeg)

Simulation:
![Half adder ](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/half_adder_stimulation.jpeg)
________________________________________________________________________________________________________________________________________

<h4>7. Half Subtractor:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps
module half_subtractor(
    input a,b,
    output diff,borrow
    );
assign diff=a^b;
assign borrow=((~a)&b);
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps
module half_subtractor_test(

    );
reg a,b;
wire diff,borrow;
half_subtractor uut(a,b,diff,borrow);
initial begin
a=0;b=0;#10
a=1;b=0;#10
a=1;b=1;#10
a=0;b=1;#10
$finish;
end
endmodule</pre>

Schematic:
![half subtractor](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/half_subtractor_schematic.jpeg)

Simulation:
![half subtractor](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/half_adder_stimulation.jpeg)
________________________________________________________________________________________________________________________________________
   
<h4>8. Full Adder:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps
module full_adder(
input a,b,c,
output sum,carry
    );
assign sum=((a^b)^c);
assign carry=(a&b) | ((a^b)&c);
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps
module full_adder_test(

    );
reg a,b,c;
wire sum,carry;
full_adder uut(a,b,c,sum,carry);
initial begin
a=0;b=0;c=0;#10
a=0;b=0;c=1;#10
a=0;b=1;c=1;#10
a=1;b=1;c=1;#10
$finish;
end
endmodule</pre>

Schematic:
![Full Adder ](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/Full%20adder%20schematic.jpeg)

Simulation:
![Full adder](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/Full%20adder%20Stimulation.jpeg)
_______________________________________________________________________________________________________________________________________
   
<h4>9. Full Subtractor:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps
module full_sub(
input a,b,bin,
output dif,bout
    );
assign dif=(a^b)^bin;
assign bout=(~a)&bin | a&bin | (~a)&b;
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps
module full_sub_test(

    );
reg a,b,bin;
wire dif,bout;
full_sub uut(a,b,bin,dif,bout);
initial begin
a=0;b=0;bin=0;#10
a=0;b=0;bin=1;#10
a=1;b=0;bin=0;#10
a=1;b=0;bin=1;#10
a=0;b=1;bin=0;#10
a=0;b=1;bin=1;#10
$finish;
end
endmodule</pre>

Schematic:
![Full subtractor](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/full_subtractor_schematic.jpeg)

Simulation:
![Full Subtractor](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/full_subtractor_stimulator.jpeg)
________________________________________________________________________________________________________________________________________

<h4>10. Universal Adder / Subtractor with Overflow Check:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps


module universal_adder_subtractor(
input a0, a1, a2, a3, b0, b1, b2, b3, m,
output c4, s0, s1, s2, s3,v
    );
assign c0= m;
assign s0= a0 ^ (b0 ^ m) ^ c0;
assign c1= (a0 & (b0 ^ m)) | (c0 & (a0 ^ (b0 ^ m)));
assign s1= a1 ^ (b1 ^ m) ^ c1;
assign c2= (a1 & (b1 ^ m)) | (c1 & (a1 ^ (b1 ^ m)));    
assign s2= a2 ^ (b2 ^ m) ^ c2;
assign c3= (a2 & (b2 ^ m)) | (c2 & (a2 ^ (b2 ^ m)));    
assign s3= a3 ^ (b3 ^ m) ^ c3;
assign c4= (a3 & (b3 ^ m)) | (c3 & (a3 ^ (b3 ^ m)));
assign v= c3 ^ c4;
endmodule
</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps


module universal_adder_subtractor_test(

    );
reg A0, A1, A2, A3, B0, B1, B2, B3, M;
wire C4, S0, S1, S2, S3,V;

universal_adder_subtractor uut(A0, A1, A2, A3, B0, B1, B2, B3, M,C4, S0, S1, S2, S3,V);

initial begin
// ADD: 9 and 10 [1001 + 1010]
A3=1; A2=0; A1=0; A0=1; 
B3=1; B2=0; B1=1; B0=0; 
M=0;
#10

// SUBTRACT: 10 from 9 [1001- 1010]
A3=1; A2=0; A1=0; A0=1; 
B3=1; B2=0; B1=1; B0=0; 
M=1;
#10
$finish;

end

endmodule
</pre>

Schematic:
![universal](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/universal%20adder%20schematic.jpeg)

Simulation:
![Universal](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/universal%20adder%20stimulation.jpeg)
________________________________________________________________________________________________________________________________________

<h4>11. SR Latch:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps



module sr_latch(
input s,r,
output q,q_
    );
assign #1 q=~(q_&s);
assign #1 q_=~(q&r);
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps

module sr_latch_test(

    );
reg s,r;
wire q,q_;
sr_latch uut(s,r,q,q_);
initial begin
s=0;r=1;#10
s=1;r=1;#10
s=1;r=0;#10
s=1;r=1;#10
s=0;r=0;#10
$finish;
end
endmodule</pre>

Schematic:
![SR latch](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/Sr%20latch%20Schematic.jpeg)

Simulation:
![SR latch](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/SR%20latch%20stimulation.jpeg)
________________________________________________________________________________________________________________________________________

<h4>12. SR Flip Flop:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps 

//Positive edge triggered SR Flip Flop

module sr_flip_flop(
input  S, R, CLK, 
output reg Q, 
output Qbar
 );
assign Qbar = ~Q;

always @(posedge CLK) begin
     case ({S, R}) 
     2'b10: Q <= 1'b1;   // Set 
     2'b01: Q <= 1'b0;   // Reset 
     2'b00: Q <= Q;      // Hold (no change) 
     2'b11: Q <= 1'bx;   // Invalid condition 
endcase
end
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps 

module sr_flip_flop_test(

    );
reg S, R, CLK; 
wire Q, Qbar; 

sr_flip_flop uut (S,R,CLK,Q,Qbar); 

initial begin 
CLK = 0; 
forever #5 CLK = ~CLK; 
end
initial begin 
S = 0; R = 0;   
#12;            
S = 0; R = 1;   
#10; 
S = 0; R = 0;   
#10; 
S = 1; R = 0;   
#10; 
S = 0; R = 0;   
#10; 
S = 1; R = 1;   
#10; 
$finish; 
end
endmodule</pre>

Schematic:
![SR FLIPFLOP](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/SR%20flipflop%20Schematic.jpeg)

Simulation:
![Sr flipflop](https://github.com/user-attachments/assets/a1960adb-c7e1-4a45-8283-f31d47558fef)
____________________________________________________________________________________________________________________________________

<h4>13. D Flip Flop:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps 

//Positive edge triggered D Flip Flop

module d_flip_flop(
input  D, CLK, 
output reg Q, 
output Qbar
    );
assign Qbar = ~Q;
always @(posedge CLK) begin
     Q <= D;
end
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps 

module d_flip_flop_test(

    );
reg  D, CLK;  
wire Q, Qbar; 

d_flip_flop uut (D,CLK,Q,Qbar); 

initial begin 
CLK = 0; 
forever #5 CLK = ~CLK; 
end 

initial begin 
D = 0;  #10;            
D = 1;  #10; 
$finish; 
end
endmodule</pre>

Schematic:
![D flipflop](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/D%20flipflop%20schematic.jpeg)

Simulation:
![D flipflop](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/d%20flipflop%20stimulator.jpeg)
________________________________________________________________________________________________________________________________________________

<h4>14. JK Flip Flop:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps 

//Positive edge triggered JK Flip Flop

module jk_flip_flop(
input  J, K, CLK, 
output reg Q, 
output Qbar 
    );
assign Qbar = ~Q;
always @(posedge CLK) begin
     case ({J, K}) 
     2'b10: Q <= 1'b1;   // Set
     2'b01: Q <= 1'b0;   // Reset
     2'b00: Q <= Q;      // No change 
     2'b11: Q <= Qbar;   // Toggle 
endcase
end
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps 

module jk_flip_flop_test(

    );
reg J, K, CLK; 
wire Q, Qbar; 

jk_flip_flop uut (J,K,CLK,Q,Qbar); 

initial begin 
CLK = 0; 
forever #5 CLK = ~CLK; 
end
initial begin  
J = 0; K = 0;   
#12;           
J = 0; K = 1;   
#10; 
J = 0; K = 0;   
#10; 
J = 1; K = 0;   
#10; 
J = 0; K = 0;   
#10; 
J = 1; K = 1;   
#10; 
$finish; 
end
endmodule</pre>

Schematic:
![JK](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/Jk%20Flipflop%20Schematic.jpeg)

Simulation:
![Jk](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/Jk%20flipflop%20Stimulator.jpeg)
________________________________________________________________________________________________________________________________________________

<h4>15. T Flip Flop:</h4>

<h5>Code:</h5>
<h5>Design source file code:</h5>

<pre>`timescale 1ns / 1ps 
 
//Positive edge triggered T Flip Flop

module t_flip_flop(
input  t, clk, 
output reg q, 
output qbar 
    );
assign qbar = ~q;
initial q=0;

always @(posedge clk) begin
   case ({t}) 
     1'b1: q <= qbar;   // Toggle
     1'b0: q <= q;   // Hold
endcase
end
endmodule</pre>

<h5>Test bench file code:</h5>

<pre>`timescale 1ns / 1ps 

module t_flip_flop_test(

    );
reg  T, CLK;  
wire Q, Qbar; 

t_flip_flop uut (T,CLK,Q,Qbar); 

initial begin 
CLK = 0; 
forever #5 CLK = ~CLK; 
end 

initial begin 
T = 0;  #10;            
T = 1;  #10; 
T = 0;  #10;            
T = 1;  #10;
$finish; 
end
endmodule</pre>

Schematic:
![T](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/t%20Flipflop%20Schematic.jpeg)

Simulation:
![T](https://github.com/shubhmittaldu/24293916051_DSD_Verilogcodes/blob/main/T%20flipflop%20stimulation.jpeg)
________________________________________________________________________________________________________________________________________________
