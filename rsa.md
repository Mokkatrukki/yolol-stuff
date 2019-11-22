gcd:n laskeminen:

a ja b ovat arvoja joihin voi sijoittaa:

```
a=48 b=18 d=0
if (0==a%2 and 0==b%2) then a/=2 b/=2 d+=1 goto 2 end
if a!=b then if 0==a%2 then a/=2 goto 3 end else goto 6 end
if 0==b%2 then b/=2 else if a>b then a=(a-b)/2 else b=(b-a)/2 end end goto 3

g= a vastaus="g= "+g+" b= "+b+" d="+d
```

privatekeyn laskeminen:
```
p=11 q=3 n=p*q phi=(p-1)*(q-1) e=3
if (1%phi)==(d*e)%phi then goto 4 else d++  goto 2 end

answer="publickey("+n+","+e+")"+"privatekey("+n+","+d+")"
```

härveli:
```
p=11 q=3 e=3 n=p*q phi=(p-1)*(q-1) t=1
a=e b=p-1 d=0 s=2//s=Startline
if (0==a%2 and 0==b%2) then a/=2 b/=2 d+=1 goto s+1 end
if a!=b then if 0==a%2 then a/=2 goto s+2 end else goto s+4 end
if 0==b%2 then b/=2 else if a>b then a=(a-b)/2 else b=(b-a)/2 end end goto s+2
if a!=1 then answer="error: p="+p goto 6 end
a=e b=q-1 d=0 s=7//s=Startline
if (0==a%2 and 0==b%2) then a/=2 b/=2 d+=1 goto s+1 end
if a!=b then if 0==a%2 then a/=2 goto s+2 end else goto s+4 end
if 0==b%2 then b/=2 else if a>b then a=(a-b)/2 else b=(b-a)/2 end end goto s+2
if a!=1 then answer="error: q="+q goto 11 end
a=36 b=phi d=0 s=12//s=Startline
if (0==a%2 and 0==b%2) then a/=2 b/=2 d+=1 goto s+1 end
if a!=b then if 0==a%2 then a/=2 goto s+2 end else goto s+4 end
if 0==b%2 then b/=2 else if a>b then a=(a-b)/2 else b=(b-a)/2 end end goto s+2
if a!=1 then answer="error: phi="+phi goto 16 end
if (1%phi)==(t*e)%phi then goto 18 else t++  goto 17 end
answer="publickey("+n+","+e+")"+"privatekey("+n+","+t+")" goto 18


```
