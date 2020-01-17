isoscreen:
```
xf=".........................."
xh="..........." xh1="..........|" xh2="........|||"
xs1="+--+" xs2="|##|" xh3="......|||||" xh4="..||||||||"xh5="||||||||||"
a=xf b=xf c=xf d=xf e=xf f=xf g=xh+xs1+xh h=xh+xs2+xh i=xh+xs1+xh j=xf k=xf l=xf

h=xh+xs2+xh1
h=xh+xs2+xh2
h=xh+xs2+xh3
h=xh+xs2+xh4
h=xh+xs2+xh5
```
ash
```
range=12
if range>0 then goto 3 else goto 10 end
x=12 s="" t=x-range l=x-t 
if x>0 then x-- if l>0 then s+="." l-- else s+="|" end goto 4 end
range--
goto 2

```
