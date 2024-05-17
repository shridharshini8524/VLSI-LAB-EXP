# VLSI-LAB-EXPERIMENTS
Exp - 1

DATE : 

AIM:

To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED:

Xilinx 14.7 Spartan6 FPGA

PROCEDURE: 

STEP:1 Start the Xilinx navigator, Select and Name the New project. 

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 

STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. 

STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. 

STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 

STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. 

STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.

STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

STEP:12 Load the Bit file into the SPARTAN 6 FPGA

Logic Diagram :

Logic Gates:


![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:


![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:


![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:



![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:


![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder


![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



DEVELOPED BY: SHRIDHARSHINI

REGISTERED NUMBER: 212222060240

Logic Gates:
~~~
module gate(a,b,w1,w2,w3,w4,w5,w6,w7);
      input a,b;
      output w1,w2,w3,w4,w5,w6,w7;
      and g1 (w1,a,b);
      or g2 (w2,a,b);
      not g3 (w3,a);
      xor g4 (w4,a,b);
      xnor g5 (w5,a,b);
      nand g6 (w6,a,b);
      nor g7 (w7,a,b);
endmodule
~~~
Half Adder:  
~~~
module halfadder( a,b,sum,carry);
input a,b;
output sum,carry;
xor g1(sum,a,b);
and g2(carry,a,b);
endmodule
~~~
Full Adder:
~~~
  module fulladder(a,b,cin,sum,carry);
       input a,b,cin;
       output sum,carry;
       wire w1,w2,w3;
       xor g1(w1,a,b);
       xor g2(sum,w1,cin);
       and g3(w2,w1,cin);
       and  g4(w3,a,b);
       or g5(carry,w2,w3);
  endmodule
~~~
Half Subtractor:
~~~
module hs(a,b,difference,borrow);
       input a,b;
       output difference,borrow;
       wire w;
       xor g1(difference,a,b);
       and g2(borrow,w,b);
       not g3(w,a);
endmodule

~~~
Full Subtractor:
~~~
module fs(a,b,c,diff,borrow);
    input a,b,c;
    output diff,borrow;
    wire w1,w2,w3,w4,w5;
    xor g1(w3,a,b);
    xor g2(diff,c,w3);
    and g3(w2,b,w1);
    and g4(w5,w4,c);
    not g5(w1,a);
    not g6(w4,w3);
    nor g7(borrow,w5,w2);
endmodule   
~~~
8 Bit Ripple Carry Adder:
~~~
  module fa(a,b,cin,sum,carry);
       input a,b,cin;
       output sum,carry;
       wire w1,w2,w3;
       xor g1(w1,a,b);
       and g2(w3,a,b);
       xor g3(sum,w1,cin);
       and g4(w2,w1,cin);
       or g5(carry,w2,w3);
 endmodule
 
 module rca(a,b,cin,sum,cout);
        input[3:0]a,b;
        input cin;
        output [3:0]sum;
        output cout;
        wire w1,w2,w3;
      fa g1(.a(a[0]),
            .b(b[0]),
            .cin(cin),
            .sum(sum[0]),
            .carry(c1)
            );
       fa g2(.a(a[1]),
             .b(b[1]),
             .cin(c1),
             .sum(sum[1]),
             .carry(c2)
             );
       fa g3(.a(a[2]),
             .b(b[2]),
             .cin(c2),
             .sum(sum[2]),
             .carry(c3)
             );
        fa g4(.a(a[3]),
              .b(b[2]),
              .cin(c3),
              .sum(sum[3]),
              .carry(cout)
              );
 endmodule
~~~
 OUTPUT:
 LOGIC GATES:

 
 ![WhatsApp Image 2024-04-14 at 18 24 53_646cc831](https://github.com/shridharshini8524/VLSI-LAB-EXP/assets/148639799/8b87d7ab-3dbd-4483-b5a8-52dba6d61341)

HALF ADDER:


![WhatsApp Image 2024-04-14 at 18 26 22_ff6651e1](https://github.com/shridharshini8524/VLSI-LAB-EXP/assets/148639799/fa11090f-47bf-4da4-bc55-0e2e6ece211b)

FULL ADDER:


![WhatsApp Image 2024-04-14 at 18 27 08_e5aa708c](https://github.com/shridharshini8524/VLSI-LAB-EXP/assets/148639799/db9fb03d-c8ed-42ea-bb25-a948a4a126b4)

HALF SUBTRACTOR:


![WhatsApp Image 2024-04-14 at 18 27 48_34858efe](https://github.com/shridharshini8524/VLSI-LAB-EXP/assets/148639799/4b209e8d-cd5c-477d-8a18-7d35d30298b8)

FULL SUBTRACTOR:


![WhatsApp Image 2024-04-14 at 18 29 32_075a1990](https://github.com/shridharshini8524/VLSI-LAB-EXP/assets/148639799/545feae1-7509-44e4-bd0f-ecc5fcc5ee19)

8 RIPPLE CARRY ADDER:


![WhatsApp Image 2024-04-14 at 18 33 25_445428f1](https://github.com/shridharshini8524/VLSI-LAB-EXP/assets/148639799/c8f42ce1-74c7-41b5-9cb5-5bf34555d225)

RESULT:

Hence, the stimulation and synthesis of a Logic Gates,Adders and Subtractor was run successfully by using Xilinx ISE.
