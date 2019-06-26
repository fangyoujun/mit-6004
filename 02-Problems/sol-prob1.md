## Prob 1 Basics of Information
### 1 Measuring Information
A).
$I(selection) = log_{2}(\frac{1}{3/8})=1.41 \text{ bit}$  

B).
$I(\text{ 1st card flipped over})=log_{2}(\frac{1}{1/52})=5.7 \text{ bit}$  
$I(\text{ 5th card flipped over})=log_{2}(\frac{1}{1/48})=5.58 \text{ bit}$
$I(\text{ last card flipped over})=log_{2}(\frac{1}{1})=0 \text{ bit}$

C). $I(X) =log_{2}(\frac{1}{2^{(N-3)}/2^N}) = 3 \text{ bits}$

D). $I(X) = log_{2}({\frac{1}{8/2^8}}) = 5 \text{ bits}$

### 2 Variable length encoding & compression
A).Choose (A)

B).ABAEC

C).Tree#1 because Tree#1 has less bit for A (higher probability so less information) and more bits for B,C,D,E.

D).Same as Tree#1 or just swap B-C and D-E

E).

| species | proba | encoding |
| ------- | ----- | -------- |
| boss    | 1/2   | 0        |
| Spec1   | 1/30  | 10000    |
| Spec2   | 1/30  | 10001    |
| Spec3   | 1/30  | 10100    |
| Spec4   | 1/30  | 10101    |
| Spec5   | 1/30  | 10110    |
| Spec6   | 1/30  | 10111    |
| Spec7   | 1/30  | 11000    |
| Spec8   | 1/30  | 11001    |
| Spec9   | 1/30  | 11010    |
| Spec10  | 1/30  | 11001    |
| Spec11  | 1/30  | 11100    |
| Spec12  | 1/30  | 11101    |
| Spec13  | 1/30  | 11110    |
| Spec14  | 1/30  | 11111    |
| Spec15  | 1/30  | 1001     |


$\rightarrow \text{ len_bit} = (1)(1/2) + (5)(1/30)(14)+(4)(1/30)=2.9 \text{ bits}$

F).
$\text{avg_bits} = \sum_{sum=2}^{12}p_{sum}\times i_{sum}=3.274 \text{ bits}$
$\text{avg_bits_1000} = 3274 \text{ bits}$

G).

| sum | proba | encoding |
| --- | ----- | -------- |
| 2   | 1/36  | 000000   |
| 12  | 1/36  | 000001   |
| 3   | 2/36  | 000010   |
| 11  | 2/36  | 000011   |
| 4   | 3/36  | 00010    |
| 10  | 3/36  | 00011    |
| 5   | 4/36  | 0010     |
| 9   | 4/36  | 0011     |
| 6   | 5/36  | 010      |
| 8   | 5/36  | 011      |
| 7   | 6/36  | 1        |

$\rightarrow \text{ len_bit} = (6)(1/36)(2)+(6)(2/36)(2)+(5)(3/36)(2)+(4)(4/36)(2)+(3)(5/36)(2)+(1)(6/36)=3.722 \text{ bits}$
$\rightarrow \text{ len_bit_1000} = 3722\text{ bits}$

### 3 Variable-length Encoding
A).Suppose the number of letters in the message is N. Then the number of bits of info:  
$I = log_{2}(\frac{1}{0.15}) = 2.73 \text{ bits}$

B). The fixed length is 3, so Hamming distance should = 3. Add a parity bit to the original code so that the total number of 1 bits in the new code is even. Then for check, if the number of 1s in the code is even, NO single-bit error occurred; otherwise occurred.

C).

| letter | proba | encoding |
| ------ | ----- | -------- |
| A      | 0.15  | 000      |
| E      | 0.4   | 1        |
| I      | 0.15  | 001      |
| O      | 0.15  | 010      |
| U      | 0.15  | 011      |
$\rightarrow \text{ len_bit} = 4\times 0.15\times3 + 1\times0.4=2.19\text{ bits}$

### 4 Modular arithemic & 2's Complement
A). $2^{32}$

B).  
zero:  00000000 00000000 00000000 00000000  
most+: 01111111 11111111 11111111 11111111; $2^{31}-1$   
most-: 10000000 00000000 00000000 00000000;
$-2^{31}$  

C).  
37(10): 0x25  
32768(10): 0x8000  
bin:0xDEADBEEF

D).  
13+10 = 001101 + 001010 = 010111 = 23  
15-18 = 001111 - 010010 = 001111 + (~010010+1) = 001111 + 101110 = 111101 = -3  
27-6 = 011011 - 000110 = 011011 + (~000110+1) = 011011 + 111010 = 010101 = 21  
-6-15 = (~000110 + 1) + (~001111+1)= 101011 = -21  
31+12 = 011111+001100=101011 = -21  

### 5 Error Detection and correction
A). (1) and (3) because the number of 1s is odd.

B).  
(1):  
0011  
0110  
0011  
011  
(2):  
1100  
0000  
0101  
100  
(3):  
000  
101  
10  
(4):  
0110  
1001  
0110  
100  

C).Error happens to two parity bits, one in row and one in column check bit. As a result, the corresponding data position will be wrongly detected as error and changed from correct value to incorrect one. E.g:  
The original correct message is:  
1100  
0000  
0101  
100  
Then error happens to the check bit of first row and first column:
1101  
0000  
0101  
000  
In such case, ECC will treat the first data of the first row and first column as error, so correct it to:
0101  
0000  
0101  
000  
which is totally different from original one.

D). Smallest Hamming distance = 2

E). 1-bit error because the number of 1s is even

F). $2^4 = 16$ values

### 6 Hamming single-error-correcting-code
A). For the binary representation of an index, from left to right, if the i-th (i started at 0) place of the binary representation is 1, then the index should be included in parity p_i. E.g index 3 = 00011, the 0th and 1th place are 1, so 3 should be included in p0 and p1.

B). Index of 13
