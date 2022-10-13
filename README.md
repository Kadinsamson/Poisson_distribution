# Fitting Poisson  distribution
# Aim : 

To fit poisson distribution for the arrival of objects per minute from the feeder

# Software required :  

Python and Visual component tool

# Theory:

The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

![image](https://user-images.githubusercontent.com/104613195/166248326-fd042076-8b0b-40c4-8b11-1d8e8fcb74db.png)

 Conditions for Poisson Distribution:

1. An event can occur any number of times during a time period.
2. Events occur independently. I
3. The rate of occurrence is constant.
4. The probability of an event occurring is proportional to the length of the time period. 
 
# Procedure :

![image](https://user-images.githubusercontent.com/104613195/166251988-d0c53205-6080-4f7b-ae4c-398178586637.png)

# Experiment :
![image](![e2](https://user-images.githubusercontent.com/94525955/195507416-5700bb48-68f6-4e8a-bcd1-b28f7f1013ed.png)

# Program :
```
DEVELOPED BY : KADIN SAMSON L
REGISTER NUMBER : 212221230044
```
```
import numpy as np
import math
import scipy.stats

X=[0,1,2,3,4,5,6]
f=[13,25,52,68,32,16,4]
n=6
N=np.sum(f)
mean=np.inner(X,f)/N
p=mean/n
q=1-p
Pr=list(); E=list(); xi=list()
print("  X P(X=x) Obs.Fr  Ex.Fre   xi ")
print("----------------------------------")
for x in range(7):
    c=math.factorial(n)/(math.factorial(x)*math.factorial(n-x))
    Pr.append(c*p**x*q**(n-x))
    E.append(Pr[x]*N)
    xi.append((f[x]-E[x])**2/E[x])
    print("%2.2f %2.2f  %4.2f   %3.2f  %3.2f"%(x,Pr[x],f[x],E[x],xi[x]))
print("----------------------------------")
cal_chi2=np.sum(xi)
print("Calculated value of Chi square is %4.2f"%cal_chi2)
tab_chi2=scipy.stats.chi2.ppf(1-.01, df=n)
print("Table value of Chi square at 1  level is %4.2f"%tab_chi2)
if cal_chi2<tab_chi2:
    print("The given data can be fitted in binomial distribution at 1% LOS")
else:
    print("The given data cannot be fitted in binomial distribution at 1% LOS")
```
# Output :
![E2 1](https://user-images.githubusercontent.com/94525955/195507263-c17bbe34-02e0-4761-9726-9d6b0b6f9cfa.png)


# Results : 
Thus Poisson distribution for the arrival of objects per minute from the feeder is fitted successfully.
 
