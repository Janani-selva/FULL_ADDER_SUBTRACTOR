# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

![image](https://github.com/user-attachments/assets/b902d982-3c07-4844-aa38-40ed185c2c85)

![image](https://github.com/user-attachments/assets/1e358a1e-7b8d-4562-8840-c761b5086dcb)

```
**Procedure**
1. Type the program in Quartus software.
2. Compile and run the program.
3. Generate the RTL schematic and save the logic diagram.
4. Create nodes for inputs and outputs to generate the timing diagram.
5. For different input combinations generate the timing diagram
```
**Program:**
```
/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. 
Developed by:janani.s 
RegisterNumber:24901127*/
```

```
full adder

module ex04(sum, cout, a, b, cin);
output sum;
output cout;
input a;
input b;
input cin;
//internal nets
wire sl,cl,c2;
//Instantiate logic gate primitives xor (sl,a,b);
and(cl,a,b);
xor (sum, sl, cin);
and(c2, sl, cin);
or(cout, c2,cl);
endmodule

Full subractor

module ex04a (df, bo, a, b, bin);
output df;
output bo;
input a;
input b;
input bin;
wire w1,w2, w3;
assign w1=a^b;
assign w2=(~a&b);
assign w3=(-w1&bin);
assign df-w1^bin;
assign bo-w2/w3;
endmodule
```
**RTL Schematic**

![image](https://github.com/user-attachments/assets/a34e7a9a-d915-42f2-82a3-de614ca51471)
![image](https://github.com/user-attachments/assets/6702c12b-0c42-4b35-abb2-b9b7c912f698)

**Output Timing Waveform**
![image](https://github.com/user-attachments/assets/2ec2bb33-83f8-47b1-af8e-192726748b2a)

![image](https://github.com/user-attachments/assets/db78c9af-0fd9-44b8-b982-90711d25576b)


**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



