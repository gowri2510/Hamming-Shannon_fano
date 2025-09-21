# Huffman-Shannon_fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:
# Program:
```
#Huffman and Shannon-Fano coding
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
# Calculation:
`
<img width="1029" height="658" alt="{A14CE554-CA95-4025-804A-5B8C79B72C95}" src="https://github.com/user-attachments/assets/d8dc89bb-d1ca-4e6e-8760-2f0b608ecb71" />
<img width="2392" height="4076" alt="image" src="https://github.com/user-attachments/assets/c9a51fe5-0af9-4e88-a375-94ad5be0a4f0" />
<img width="2624" height="3876" alt="image" src="https://github.com/user-attachments/assets/78810f90-8b65-4a0b-be09-b682fca25c41" />

```
# Output
```
<img width="891" height="674" alt="{B0EB7B70-B017-4C88-912C-C53F9057DAE4}" src="https://github.com/user-attachments/assets/4d42a6b7-365c-4165-aa1e-9a86a0377abf" />

``` 
# Results:
```
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25 Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484
```
