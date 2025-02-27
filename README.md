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

## Logic Diagram
## Procedure
## Program:
```
/*
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: Meenakshi M
RegisterNumber: 212221230057
```
## NAND:
```
   module na(a,b,c,d,f);
   input a,b,c,d;
   output f;
   wire p,q,r;
   assign p=(~c & b & a);
   assign q=(~d & c & ~a);
   assign r=(c & ~b & a);
   assign f=(~(~p & ~q & ~r));
   endmodule
 ```
 ## NOR:
 ```
    module nr(a,b,c,d,f);
   input a,b,c,d;
   output f;
   wire p,q,r;
   assign p=( c & ~b & a);
   assign q=( d & ~c & a);
   assign r=( c & ~b & a);
   assign f=(~(~( p | q | r)));
   endmodule
 ```
*/
## Output:
## Truth Table:
### For NAND:
![image](https://user-images.githubusercontent.com/94165108/201528894-7eaeaf75-8432-4544-abed-abb2a1ad5234.png)
### For NOR:
![image](https://user-images.githubusercontent.com/94165108/201528957-0320877f-3be5-4444-af1e-03d94c865318.png)

## RTL:
### For NAND:
![image](https://user-images.githubusercontent.com/94165108/201528845-5c7fbb8f-7e9c-4186-a48a-3201b9e4ea92.png)
### For NOR:
![image](https://user-images.githubusercontent.com/94165108/201528990-e87da4cb-6d3f-407b-90f0-77a0d496fa4b.png)

## Timing Diagram:
### For NAND:
![image](https://user-images.githubusercontent.com/94165108/201528867-8b48bb56-a992-47f0-bcc7-c33872d0cfd5.png)
### For NOR:
![image](https://user-images.githubusercontent.com/94165108/201529036-eca41c84-539b-4ac1-b115-bb5b26828fbd.png)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
