# Experiment--02-Implementation-of-combinational-logic...

Implementation of combinational logic gates
 
## AIM:

To implement the given logic function verify its operation in Quartus using Verilog programming.

F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D

F2=xy’z+x’y’z+w’xy+wx’y+wxy
 
## Equipments Required:

Hardware – PCs, Cyclone II , USB flasher.

Software – Quartus prime.

## Theory:
 
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output.

## Using NAND gates:

NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram:

![out1](https://user-images.githubusercontent.com/93427534/234936628-83a6ce0f-99e9-487f-825f-f1d5b826b8d1.png)

## Using NOR gates:

NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram:

![out2](https://user-images.githubusercontent.com/93427534/234947763-464e19ba-ba01-4d69-a228-c93e441b138c.png)

## Procedure:

1) Create a project with required entities.
2) Create a module along with respective file name.
3) Run the respective programs for the given boolean equations.
4) Run the module and get the respective RTL outputs.
5) Create university program(VWF) for getting timing diagram.
6) Give the respective inputs for timing diagram and obtain the results.

## Program:

```c
Program to implement the given logic function and to verify its operations in quartus using Verilog programming.
Developed by: Anto Richard.S
RegisterNumber: 212221240005

module combinational(a,b,c,d,w,x,y,z,fl,f2);
input a,b,c,d,w,x,y,z;
output fl,f2;
wire g1=((~a)&(~b)&(~c)&(~d)); 
wire g2=((a)&(~c)&(~d));
wire g3=((~b)&(c)&(~d));
wire g4=((~a)&(b)&(c)&(d)); 
wire g5=((b)&(~c)&(d));
assign fl=g1|g2|g3|g4|g5; 
wire g6=((x)&(~y)&(z));
wire g7=((~x)&(~y)&(z));
wire g8=((~w)&(x)&(y)); 
wire g9=((w)&(~x)&(y));
wire g10=((w)&(x)&(y)); 
assign f2=g6|g7|g8|g9|g10;
endmodule

```

## Output:

## RTL realization of NAND and NOR gates:

![out3](https://user-images.githubusercontent.com/93427534/234953136-9f68fd89-b3dd-479d-a707-d7983ec2f7de.png)

## Truth Table of NAND gate:

![out4](https://user-images.githubusercontent.com/93427534/234953703-8a245942-a190-43c9-95a3-87e38115a2b4.png)

## Truth Table of NOR gate:

![out5](https://user-images.githubusercontent.com/93427534/234953727-e5e28043-b921-4878-841c-e78af018d82e.png)

## Timing Diagram:

![out6](https://user-images.githubusercontent.com/93427534/234953740-b8ad1171-1ebb-465f-8531-6b8192a9e543.png)

## Result:

Thus the given logic functions are implemented using  and their operations are verified using Verilog programming.


