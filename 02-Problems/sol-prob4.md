## Prob 4 Gate and Boolean logic
### 1  
A). Truth table  

| A   | B   | H   |
| --- | --- | --- |
| 0   | 0   | 1   |
| 0   | 1   | 1   |
| 1   | 0   | 0   |
| 1   | 1   | 1   |

B). Sum_of_Products = $\overline{A} \cdot \overline{B} +B$

C).  
$t_{CD}$ = $t_{CD-NR2}$ + $t_{CD-NR2}$ + $t_{CD-ND2}$ = 5 + 5 + 5 = 15ps  
$t_{PD}$ = $t_{PD-AN2}$ + $t_{PD-NR2}$ + $t_{PD-ND2}$= 50 + 30 + 30 = 110ps  
$t_{R}$ = rise time of gate that drives output = $t_{R-ND2}$ = 11ps  

### 2
A). F = $\overline{A} \cdot B$ + $A \cdot \overline{C} \cdot D$ + $A \cdot \overline{B} \cdot C$

B).
C0 = 0, C1 = 1, C2 = 1, C3 = 0 so that F = $\overline{A} \cdot B$ + $\overline{B} \cdot A$  

C). Yes because 2 inputs have 4 combinations, and there are exactly 4 select values from C0 to C3 (two select lines)  

D).   
(a) = $\overline{A} \cdot B + \overline{B} + C$  
(b) = $\overline{A} \cdot C + \overline{B} \cdot C$  
(c) = $\overline{A} \cdot C + B \cdot \overline{C}$  
(d) = $\overline{A} \cdot B$ + $A \cdot \overline{C} \cdot D$ + $A \cdot \overline{B} \cdot C$  

E). easy...

F). For 5-inputs the truth table has $2^5 = 32$ rows, and each row has 2 possible outputs, so total outputs $2^{32}$  

### 3
A). 3-input has a truth table of 8 rows. The output is to indicate the place of the 1st "1" that appears in the input, thus the output is 0, 1, 2 or 3.  
E.g. for the input "000" the output is 0 because there is no "1" in the input; for the input "110" the output is 3 because there the 1st "1" appear in the place with highest priority order  

| A   | B   | C   | O1  | O2  |
| --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 0   | 0   |
| 0   | 0   | 1   | 0   | 1   |
| 0   | 1   | 0   | 1   | 0   |
| 0   | 1   | 1   | 1   | 0   |
| 1   | 0   | 0   | 1   | 1   |
| 1   | 0   | 1   | 1   | 1   |
| 1   | 1   | 0   | 1   | 1   |
| 1   | 1   | 1   | 1   | 1   |

B).  
$O1 = A + B$  
$O2 = A  +\overline{B} \cdot C$

### 7 FPGA
A). Here we would have three independent functions X=f(F1,F2,F3,F4), Z=g(G1,G2,G3,G4) and Y=c(C1,C2,C3) --(or other combination among C1-C4)  
So to ignore the F1-F4 and G1-G4 inputs to Y, it is necessary to set  MA=1, MB=1.  
And then select C1, C2, C3 by MC=0, MD=1, ME=2.

B). F1-F4 and G1-G4 are connected to same 4-inputs, and they are input to Y. So it is necessary that MA=0, MB=0.  
And then select one among C1-C4 (e.g. C1) by selecting proper ME (e.g. ME=0 for C1).  
MC and MD do not matter because the inputs would be ignored by MA and MB.

C).  
MA=0 (let pass F1-F4 4 inputs)  
MB=1 (ignore G1-G4 and let pass one of C1-C4 controlled by MD)  
MD=0 (select C1)  
ME=1 (select C2)  
MC do not matter.

D).  
MA=MB=0  
ME=1
