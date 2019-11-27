# binaari-funktiot
Koska starbasessa numerot ovat "64-bit fixed-point decimals" tämä tarkoittaa että voidaan säilöä arvoja numeroihin bitin avulla:
207125762626206225 = `1011011111110110111100100010100001001010101011101000010001`

Sijoitetaan 4bittiset numerot:
```
numerot:
15 = 1111
8 = 1000
3 = 0011
```
sijoitetaan peräkkäin 15 8 3:
```
111110000011 = 3971
```
Tämä voidaan tehdä laskemalla:
ajatellaan luvut slotteina slot1|slot2|slot3
```
slot3|slot2|slot1
1111 |1000 |0011
```
15 pitää siirtää 8 bittiä
8 pitää siirtää 4 bittiä
3 ei tarvitse siirtää
```
slot3shift=2^8 
slot2shift=2^4
slot3=slot3shift*15          // 111100000000
slot2=slot2shift*8           //     10000000
slot1=3                      //         0011
list=slot1+slot2+slot3       // 111110000011
```
slot1:
otetaan 4 viimeisintä bittiä jakojäännöksellä
```
list=3971
slot2shift=2^4
slot1= list%slot2shift

```


slot2:
otetaan 8 viimeisintä bittiä jakojäännöksellä, jonka jälkeen pitää vielä ottaa slot1 pois ja poistaa ylimääräiset bitit jakamalla
```
list=3971
slot3shift=2^8
slot2shift=2^4
slot1= list%slot2shift
slot2= list%slot3shift              // 10000011
slot2= slot2-slot1                  // 10000000
slot2=slot2/slot2shift              // 1000
```
slot3 poistetaan 8 viimeisintä bittiä
```
slot3shift=2^8 
list=3971
slot3=list-list%slot3shift      //111100000000
slot3= slot3/slot3shift         //1111
```

Pienimuoto jossa luvut laitetaan yhteen ja puretaan toisiin muuttujiin:
```
l3=15 l2=8 l1=3 s3=2^8 s2=2^4 k=l1+l2*s2+l3*s3

n3=(k-k%s3)/s3 n1=k%s2 n2=(k%s3-n1)/s2
```
