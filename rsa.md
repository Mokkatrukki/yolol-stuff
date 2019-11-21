gcd:n laskeminen:

a ja b ovat arvoja joihin voi sijoittaa:

```
a=5 b=10
d=0
if (0==a%2 and 0==b%2) then a/=2 b/=2 d+=1 goto 3 end
if a!=b then if 0==a%2 then a/=2 goto 4 else goto 5 end else goto 6 end
if 0==b%2 then b/=2 else if a > b then a=(a-b)/2 else b=(b-a)/2 end end goto 4

g= a vastaus="a= "+a+" b= "+b
```
