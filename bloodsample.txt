import math as m
import matplotlib.pyplot as pl
l1=[20,10,5,25,40,50]
bs=int(input("Enter the no. of blood samples"))
f=1
for i in l1:
    if bs%i:
       f=0
if (f==0):
   print("Blood sample size is not multiple of a pool size")
else:
   l2=[]
   for i in l1:
       l2.append((i+1-i*m.pow(0.9,i))*(bs/i))
   print("Pool Size\tExpected number of tests");
   for i in range(0,6):
       print(l1[i],"\t\t",l2[i])       
   pl.bar(l1,l2,width=2)
   pl.xlabel("Pool Size")
   pl.ylabel("Expected no. of tests")
   pl.show()