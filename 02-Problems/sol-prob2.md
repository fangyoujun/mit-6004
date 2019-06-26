## Prob 2 Digital Abstraction
### 1 Buffer
A). No because the minimum measured output voltage is 0.5V

B). 0.5V so that obey $V_{OUT} <= V_{OL}$

C).   
$V_{OL} = 0.5V$  
$V_{IL} = 1.0V$  
$V_{IH} = 3.5V$  
$V_{OH} = 4V$

D). $V_{OL-MAX} = 1V$

E). Larger noise margin $\rightarrow$ smaller $V_{OL}$  

### 2 Inverter madness
A).
No because the gain is NOT greater than 1

B).   
For A:   
$V_{OL} = 1.0V$  
$V_{IL} = 3.5V$  
$V_{IH} = 5.0V$  
$V_{OH} = 6V$

For B: no values because the gain is NOT greater than 1

For C: same as B

For D:  
$V_{OL} = 0.5V$  
$V_{IL} = 1.0V$  
$V_{IH} = 4.5V$  
$V_{OH} = 6V$

### 3 Static discipline
A). Valid inputs lead to valid outputs, so if $V_{IN} >= V_{IH}$, then we must have $V_{OUT} >= V_{OH}$. Now it is $V_{OUT} < V_{OL}$, so $V_{IN} < V_{IH}$.
Note that it is not necessary that $V_{IN} < V_{IL}$, because valid output does not imply valid input.

B). $V_{IN} < V_{IH}$

### 4 Ternary Logic
A).  

| 0V  | 1V  | 2V   | 3V  | 4V  | 5V  | 6V  | 7V   | 8V   | 9V  | 10V |
| --- | --- | ---- | --- | --- | --- | --- | ---- | ---- | --- | --- |
| "0" | N.M | F.Z. | N.M | "1" | "1" | N.M | F.Z. | N.M. | "2" | "2" |

N.M. = Noise margin  
F.Z. = Forbidden zone

B). (three platforms)

C). No because such characteristic only used for binary not for ternary.

D). $I = log_{2}(\frac{1}{1/3}) = 1.58 \text{ bits}$

E).  
Three ternary wires: $3^3 = 27$  
$I = log_{2}(\frac{1}{1/27}) = 4.754 \text{ bits}$   
At least 5 wires in binary to carry the same amount of Information

F).  
Three ternary wires: $4.754/0.01=475.4 \text{ bits/s}$  
Three binary wires: $3/0.01 = 300 \text{ bits/s}$

### 5 Barracks Logic

### 6 Z-module

### 7 Combinational construction rules
A).  

| x   | y   | z   |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 0   |
| 1   | 0   | 0   |
| 1   | 1   | 1   |

B).  
Component A: true only if two inputs are both true or both false  
Component B: true only if two inputs are both true  
Circuit: same as B  

C). $t_{PD} = 5 \text{ ns}$

### 8 2-input & 2-output
A). Yes because it has two inputs and two outputs, a functional specification and timing specificiation.

B). X is logical complement of A and Y is undetermined as it's cyclic

C). No
