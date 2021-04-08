# YOGESWARAN-POORMEKAH-YOGESWARAN-POORMEKAH-TP3-Methode-de-Newton

"""YOGESWARAN POORMEKAH 1PT2

LAHRECH Abdel Ghani
Aéro 1 — Analyse numérique (MA123, 2020-2021)
TP 3 — Méthode de Newton"""


###QUESTION 1###
print('='*10,"QUESTION 1",'='*10)
from math import cos
from math import sin
from math import tan
from math import exp
from math import log


def Newton(f,fder,x0,epsilon,Nitermax):
    n = 1
    xold = x0
    xnew = xold-(f(xold)/fder(xold))
    erreur = abs(xnew-xold)
    while erreur >=epsilon and n<Nitermax:
        xold=xnew
        xnew = xold-(f(xold)/fder(xold))
        n+= 1        # n=n+1
        erreur = abs(xnew-xold)
        xold = xnew
        print(xnew,n,(xnew-xold)) 
    print("Pour",f,"Le nombre d'itérations est de", n)
    print("|xn - xn-1| est inférieur à",epsilon," et |xn - xn-1|=", erreur,".")
    print("La suite tend vers",xnew)
    return xnew
    
    

###QUESTION 2###
print('='*10,"QUESTION 2",'='*10)

"===fonction 1==="
def f(x):
    return x**4 + 3*x - 9
def fder(x):
    return 4*(x)**3+3
    
"===fonction 2==="
def g1(x):
    return x-3*cos(x)+2
def g1der(x):
    return 1+3*sin(x)

"===fonction 3==="
def h(x):
    return x*exp(x)-7
def hder(x):
    return exp(x)+x*exp(x)
    
"===fonction 4==="
def i(x):
    return exp(x)-x-10
def ider(x):
    return exp(x)-1

"===fonction 5==="
def j(x):
    return 2*tan(x)-x-5
def jder(x):
    return (2/(cos(x)**2))-1

"===fonction 6==="
def k(x):
    return exp(x)-x**2-3
def kder(x):
    return exp(x)-2*x

"===fonction 7==="
def l(x):
    return 3*x+4*log(x)-7 
def lder(x):
    return 3+(4/x)
    
"===fonction 8==="
def m(x):
    return x**4-(2*x)**2+4*x-17 
def mder(x):
    return 4*(x**3-x+1)

"===fonction 9==="
def n(x):
    return exp(x)-2*sin(x) - 7
def nder(x):
    return exp(x)-2*cos(x)

"===fonction 10==="
def o(x):
    return log(x**2+4)*exp(x)-10
def oder(x):
    return exp(x)*(((2*x)/(x**2+4))+log(x**2+4))



print("---fonction 1---")
Newton(f,fder, (3/2), 10**-10,10**4)
Newton(f,fder, (-1) , 10**-10,10**4)
print("\n")

print("---fonction 2---")
Newton(g1,g1der, 0, 10**-10,10**4)
print("\n")

print("---fonction 3---")
Newton(h,hder, 1, 10**-10,10**4)
print("\n")

print("---fonction 4---")
Newton(i,ider, 1, 10**-10,10**4)
print("\n")

print("---fonction 5---")
Newton(j,jder, 1, 10**-10,10**4)
print("\n")


print("---fonction 6---")
Newton(k,kder, 1, 10**-10,10**4)
print("\n")

print("---fonction 7---")
Newton(l,lder, 1, 10**-10,10**4)
print("\n")

print("---fonction 8---")
Newton(m,mder, 0, 10**-10,10**4)
print("\n")

print("---fonction 9---")
Newton(n,nder, 0, 10**-10,10**4)
print("\n")

print("---fonction 10---")
Newton(o,oder, 0, 10**-10,10**4)
print("\n")



    
    
