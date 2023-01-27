# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
# Implementation of combinational logic using universal-gates

# AIM:

To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
# Equipments Required:

# Hardware – PCs, Cyclone II , USB flasher

# Software – Quartus prime

# Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output.

# Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

# Logic Diagram
![Screenshot (88)](https://user-images.githubusercontent.com/119476322/215169184-dabce38f-b49b-4d2e-b926-fa4a230be3e3.png)

# Using NOR gates

NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

# Logic Diagram
![Screenshot (89)](https://user-images.githubusercontent.com/119476322/215169285-cc01d3d2-25d1-4df9-b6dd-64f3b540fd17.png)

# Procedure

1.Using NAND Gates and Wires construct F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

2.Construct the same for F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR Gates and Wires

3.Find RTL and Timing Diagram for both the expressions 

4.End the program

# Program:

Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: Sivaramakrishnan B
RegisterNumber:  22006798

# Using NAND Gates

```
module combin1(a,b,c,d,f);


input a,b,c,d;

output f;

wire p,q,r;

assign p=(~c & b & a);

assign q=(~d & c & c & a);
assign r=(c & ~b & a);

assign f=(~(~p & ~q & ~r));

endmodule
```

# Using NOR Gates
```
module combin2(a,b,c,d,f);

input a,b,c,d;

output f;

wire p,q,r;

assign p=(c & ~b & a);

assign q=(d & ~c & a);

assign r=(c & ~b & a);

assign f=~(~(p | q | r));

endmodule
```

# Output:

# RTL realization

# Using NAND Gates

![Screenshot (90)](https://user-images.githubusercontent.com/119476322/215169458-a3550d8c-f62d-415d-9953-dda5313e9d5c.png)

# Using NOR Gates
![Screenshot (91)](https://user-images.githubusercontent.com/119476322/215169505-9d384e33-035b-4bac-9e67-9aeed8e5f0c9.png)

# Timing Diagram

# Using NAND Gates 
![Screenshot (92)](https://user-images.githubusercontent.com/119476322/215169558-096fcd90-9fcd-49f8-a961-c0ab68115fcc.png)

# Using NOR Gates
![Screenshot (93)](https://user-images.githubusercontent.com/119476322/215169740-6bd00a96-c60e-480a-b38f-5fbdfe8731af.png)

# Result:

Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
