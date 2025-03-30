# Hamming-Shannon_fano
 ### Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.
 ## Aim:
 To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.
 ## Tools Required:
 + python IDE with Numpy and Scipy.
 
 ## Program:
 ~~~
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
 
 for k in range (n):
     Avg1 = p[k] * lk[k]
     L = L + Avg1
 
 for k in range (n):
     e = p[k] * math.log(1 / p[k], 2)
     hs = hs + e
 hs = round(hs,3)
 
 eff = hs / L
 eff = round(eff,3)
 
 red =  round(1 - eff,3) 
 
 var = 0
 for k in range(n):
     var1 = p[k] * (lk[k]-L)**2
     var = var + var1
 var = round(var,3)
 print()
 print(f"Average Codeword Length is : {L}")
 print(f"Entropy is : {hs}")
 print(f"Efficiency is : {eff*100} %")
 print(f"Redudancy is : {red}")
 print(f"Variance is : {var}")
 ~~~
 ## Calculation:
 ![Screenshot 2025-03-30 225204](https://github.com/user-attachments/assets/828c05ec-c4ee-4c71-91b2-8e77fd121e01)
![WhatsApp Image 2025-03-30 at 22 29 22_74b5d707](https://github.com/user-attachments/assets/06abd339-494d-4245-ba5a-49b00d637383)
![WhatsApp Image 2025-03-30 at 22 29 22_9fd2b1dc](https://github.com/user-attachments/assets/fdd88b1f-7eaa-4881-a51e-ed6c89aa9431)
![WhatsApp Image 2025-03-30 at 22 29 23_ef38d058](https://github.com/user-attachments/assets/3d81ff34-ca0f-408b-8365-681e9e2ff472)

 ## Results:
 For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25
 
 Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484
 
