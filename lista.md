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
