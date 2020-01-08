Stringin parsiminen lohkoihin tapa1:
Parsitaan perästä päin, otetaan 30 merkkiä

```
mystring="mokkatrukki----mycoolmessagelolmomlookatme---"
message=""
c=30 // messagecount
if c>0 then c-- r=mystring---mystring message=r+message goto 4 end
```

Toinen tapa on tehdä niin sijoitetaan stringiin joku oma merkki kuten `|`
jonka vastaan tullessa ilmoitetaan tietyn viestin loppuvan. Ongelma on, jos viestissä on | merkki.

```
mystring="mokkatrukki|mycoolmessagelolmomlookatme"
message=""
r=mystring---mystring if r!="|" then  message=r+message goto 3 end
```

Lista käyttäen binaarilukua tarkistaakseen mikä slot on tyhjä. Sekä lukee firstin ja tyhentää arvonsa listalta

`p` = operator 1=post / 0=read
`v` = value
`k` = binary decimal, which tell if list has empty slots like `001001`
`memstart`= line where memoryslots start
`f` = how many memoryslots have
`t` = temp k
`s` = integer to tell which line is right
```
p=1 v="pieru" k=0 memstart=7 f=9
t=k s=0
o=t%2 if (f!=s and o==p) then t=(t-o)/2 s++ goto 3 end
if f==s then goto 20 end
r=s l=p ke=k%2^r k-=(k%2^(r+1)) k+=ke+l*2^r
goto s+memstart
if p then m0=v else v=m0 end goto 2
if p then m1=v else v=m1 end goto 2
if p then m2=v else v=m2 end goto 2
if p then m3=v else v=m3 end goto 2
if p then m4=v else v=m4 end goto 2
if p then m5=v else v=m5 end goto 2
if p then m6=v else v=m6 end goto 2
if p then m7=v else v=m7 end goto 2
if p then m8=v else v=m8 end goto 2
```
Käydään läpi ensimmäinen tyhjä slot tai ensimmäinen täysi slot. Riippuu `p`:stä:
```
o=t%2 if (f!=s and o==p) then t=(t-o)/2 s++ goto 3 end
```
heitetään pois jos on täynnä:
```
if f==s then goto 20 end
```
Tallennetaan binaarimuotoisesti käyttäen riviä:
```
r=s l=p ke=k%2^r k-=(k%2^(r+1)) k+=ke+l*2^r
```
esim:
```
k=31 //11111
// change to 10111
// r=how many bit to left
// l= 1 or 0
r=3 l=0 ke=k%2^r k-=(k%2^(r+1)) k+=ke+l*2^r

answer=k //10111 = 23
```

```
p=1 v=0 k=0 memstart=7 f=9
t=k s=0 v++
o=t%2 if (f!=s and o==p) then t=(t-o)/2 s++ goto 3 end
if f==s then goto 19 end
r=s l=p ke=k%2^r k-=(k%2^(r+1)) k+=ke+l*2^r
goto s+memstart
if p then m0=v else v=m0 m0="" end goto 2
if p then m1=v else v=m1 m1="" end goto 2
if p then m2=v else v=m2 m2="" end goto 2
if p then m3=v else v=m3 m3="" end goto 2
if p then m4=v else v=m4 m4="" end goto 2
if p then m5=v else v=m5 m5="" end goto 2
if p then m6=v else v=m6 m6="" end goto 2
if p then m7=v else v=m7 m7="" end goto 2
if p then m8=v else v=m8 m8="" end goto 2



if p then p=0 else p=1 end
list=m0+m1+m2+m3+m4+m5+m6+m7+m8 goto 2
```

optimointia:
```
p=1 t=469762047 s=0
halft=t%2^15 if halft==32767 then t=(t-halft)/2^15 s=15 end
o=t%2 if o==p then t=(t-o)/2 s++ goto 2 end

vastaus=s
```


Etsimistä:

```
k=11 p=0 q=10 memstart=17 f=4 m0="kissa" m1="koira" m3="pieru"
t=k s=0  
o=t%2 if (f!=s and o==p) then t=(t-o)/2 s++ goto 3 end
if f==s then goto 19 end
r=s l=p ke=k%2^r k-=(k%2^(r+1)) k+=ke+l*2^r
goto s+memstart



if v=="koira" then goto 12 else goto 2 end

vastaus="loysi koiran rivilta: "+(s+memstart) goto 12




if p then m0=v else v=m0 end goto q
if p then m1=v else v=m1 end goto q
if p then m2=v else v=m2 end goto q
if p then m3=v else v=m3 end goto q
```

