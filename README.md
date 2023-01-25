# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'


## Procedure
## Program:

Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
PROGRAM USING NAND:

module expfourone(a,b,c,d,f);
input a,b,c,d;
output f;
wire f1,f2,f3;
assign f1 = (~c&~b&~a);
assign f2 = (~d&~c&~a);
assign f3 = (c&~(~b)&~a);
assign f= f1&~f2&~f3;
endmodule
PROGRAM USING NOR:

module expfourtwo(a,b,c,d,f);
input a,b,c,d;
output f;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(f,f4);
endmodule 

## Output:
## RTL realization

FOR PROGRAM USING NAND:
![Screenshot (36)](https://user-images.githubusercontent.com/119475507/214619120-69d786bd-dd1e-4ec5-ae70-c4a525e94831.png)

FOR PROGRAM USING NOR:
![Screenshot (37)](https://user-images.githubusercontent.com/119475507/214619572-532c083b-60fe-4c0d-82d5-d8323f17c64a.png)

TRUTH TABLE:

FOR PROGRAM USING NAND:
![image](https://user-images.githubusercontent.com/119475507/214619929-c9460972-beb8-426c-a575-97af8203ee16.png)

FOR PROGRAM USING NOR:
![image](https://user-images.githubusercontent.com/119475507/214620154-9e2fd44d-c5c1-48b9-8a0a-3bc78630c400.png)


## Timing Diagram
FOR PROGRAM USING NAND:
![image](https://user-images.githubusercontent.com/119475507/214620412-2bd16e60-a483-4f45-bc4c-382b1cdfa5f7.png)

FOR PROGRAM USING NOR:
![image](https://user-images.githubusercontent.com/119475507/214620765-8cfbb081-5b68-4504-b4b7-d91a1f68060d.png)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
