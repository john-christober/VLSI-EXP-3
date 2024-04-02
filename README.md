# Exp-3
DATE
SIMULATION AND IMPLEMENTATION OF MULTIPLIER
# AIM:
To simulate and synthesis Multiplier using VIVADO
# APPARATUS REQUIRED:
VIVADO 2023.2
# PROCEDURE:
STEP:1 Start the Vivado, Select and Name the New project.
STEP:2 Select the device family, device, package and speed.
STEP:3 Select new source in the New Project and select Verilog Module as the Source
type.
STEP:4 Type the File Name and Click Next and then finish button. Type the code and
save it.
STEP:5 Select the Behavioural Simulation in the Source Window and click the check
syntax.
STEP:6 Click the simulation to simulate the program and give the inputs and verify the
outputs as per the truth table.

# 2 BIT MULTIPLIER:
![image](https://github.com/john-christober/vlsi-exp-3/assets/145186233/7f3904f7-54eb-4244-9400-1a81eedd6697)
![image](https://github.com/john-christober/vlsi-exp-3/assets/145186233/ef27c430-45c2-45fb-83a2-d95ab07bf370)


# PROGRAM:
`timescale 1ns / 1ps
module ha(a,b,s,c);
input a,b;
output s,c;
xor g1(s,a,b);
and g2(c,a,b);
endmodule
module mux2(a,b,c);
input[1:0]a,b;
output[3:0]c;
wire w1;
and g1(c[0],b[0],a[0]);
ha ha1(a[0]&b[1],a[1]&b[0],c[1],w1);
ha ha2(a[1]&b[1],w1,c[2],c[3]);
endmodule

# output:
![image](https://github.com/john-christober/vlsi-exp-3/assets/145186233/452f231e-067e-4f68-9b61-236832abb69a)
# 4 BIT MULTIPLIER:
![image](https://github.com/john-christober/vlsi-exp-3/assets/145186233/b31cf7f7-6fea-439a-b225-1b3cd3f7a654)


# PROGRAM:
module ha (a,b,s,c);
input a,b;
output s,c;
xor g1(s,a,b);
and g2(c,a,b);
endmodule
module fa(a,b,c,sum,carry);
input a,b,c;
output sum ,carry;
wire w1,w2,w3;
xor g1(w1,a,b);
xor g2(sum,w1,c);
and g3(w2,w1,c);
and g4(w3,a,b);
or g5(carry,w2,w3);
endmodule
module mul_4_bit(x,y,z);
input [3:0]x,y;
output [7:0]z;
wire [17:1]w;
and(z[0],x[0],y[0]);
ha hal (x[1]&y[0],x[0]&y[1], z[1],w[1]);
fa fal (x[2]&y[0],x[1]&y[1],w[1],w[5],w[2]);
fa fa2 (x[3]&y[0],x[2]&y[1],w[2],w[6],w[3]);
ha ha2 (x[3]&y[1],w[3],w[7],w[4]);
ha ha3 (w[5], x[0]&y [2],z[2],w[8]);
fa fa3 (w[6],x[1]&y[2],w[8], w[12], w[9]);
fa fa4 (w[7],x[2]&y[2],w[9],w[13],w[10]);
fa fa5 (w[4],x[3]&y[2],w[10],w[14], w[11]);
ha ha4 (w[12], x[0]&y[3], z[3], w[15]);
fa fa6 (w[13],x[1]&y[3],w[15],z[4],w[16]);
fa fa7 (w[14],x[2]&y[3],w[16], z[5],w[17]);
fa fa8 (w[11],x[3]&y[3],w[17],z[6],z[7]);
endmodule
# OUTPUT:
![image](https://github.com/john-christober/vlsi-exp-3/assets/145186233/df7bfae1-625b-4a7c-8a94-58bcd57cd355)


# RESULT:
Thus, The 2 Bit and 4 Bit Multiplier are simulated successfully.
