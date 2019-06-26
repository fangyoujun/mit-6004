## Lab 1 CMOS

With 8 MOSFETs, design CMOS gate that implements $F = C + A \cdot B$  

Idea:  
There are 3 inputs (A, B, C). The MOSFETs are dual use (one NFET with one PFET). So there should have at least 6 MOSFETs. Besides, CMOS is naturally inverting (directly for negative logical operation), so we need firstly compute $\overline{F}$ with 6 MOSFETs, and then use another 2 MOSFETs to invert $\overline{F}$ to $F$.  

Step 1: NFETs pullup circuit for $\overline{F} = \overline{C+A \cdot B} = \overline{C}\cdot{(\overline{A}+\overline{B})}$

Step 2: replace NFETs with PFETs to build pulldown circuits

Step 3: Combine the pullup circuit (Step 1) with pulldown circuit (Step 2), whose output again connect to a CMOS inverter, and finally connect to F

My scheme:  
![](lab1.png)

## Lab 2 Adder
$S = A \bigoplus B \bigoplus C_{IN}$  
with $XOR(A,B) = \overline{A\cdot B + \overline{A}\cdot \overline{B}} = \overline{A\cdot B + \overline{A+B}} = \overline{A\cdot B + NOR(A,B)}$  
with $NOR(A,B) = \overline{A}\cdot \overline{B}$  

$C_{OUT} = \overline{\overline{C_{OUT}}} = \overline{\overline{AB}\cdot \overline{AC_{IN}} \cdot \overline{BC_{IN}}}$  
with $NAND2(A,B) = \overline{A} + \overline{B}$  
and $NAND2(A,B,C) = \overline{A} + \overline{B} + \overline{C}$

+ overall fa scheme:
![](lab2-fa.png)

+ xor2 scheme:
![](lab2-xor2.png)

+ nor2 scheme:
![](lab2-nor2.png)

+ nand2 scheme:
![](lab2-nand2.png)

+ nand3 scheme:  
(if implemented by combination of nand2, there would have 8 MOSFETS, worse than below)
![](lab2-nand3.png)

## Lab 4 ALU

#### ALU:
![](lab4-alu.png)

#### BOOL:
![](lab4-bool.png)

#### ARITH:
![](lab4-arith.png)

with **adder32** which is:

+ series of FA implemented in Lab 2:
+ and the OR logic that test whether all the bits of s are zero
![](lab4-adder32.png)

#### CMP:
![](lab4-cmp.png)

#### SHIFT:
![](lab4-shift.png)

## Lab 5 Assembly Language
```cpp
STEP1:
        CMOVE(0,swapped) //Load 0 to swapped
STEP2:
        CMOVE(0,i)       //Load 0 to i
STEP3:
        ADDC(i,1,i)      //i++
		CMPLTC(i,ALEN,R2) //R2 <- (i < ALEN)
		BEQ(R2,STEP5)    //Branch to STEP5 if i==ALEN
STEP4:
        MULC(R0,4,R2)     //R2 <- Addr of i
		LD(R2,A,R3)       //R3 <- A[i]
		LD(R2,A-4,R4)     //R4 <- A[i-1]
		CMPLE(R4,R3,R5)   //R5 <- (A[i-1] <= A[i])
		BEQ(R5,swap) //if A[i-1] <= A[i] swap A[i-1] and A[i]
		BR(STEP3) //go to STEP3
		swap:
			ST(R4,A,R2)   //A[i] <- R4
			ST(R3,A-4,R2) //A[i-1] <- R3
			CMOVE(1,swapped)
		BR(STEP3) //go to STEP3

STEP5:
        CMPEQC(swapped,1,R6) //R6 <- (swapped == 1)
		BNE(R6,STEP1)
```
