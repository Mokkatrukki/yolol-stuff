# yolol-stuff
Ohjeita ja muistiinpanoja

# Aluksen kulma suhteessa laskeutumisalustaan
Rangefinderin avulla voidaan laskea aluksen kulma suhteessa laskeuduttavalle pinnalle. Tarvitaan 2 rangefinderiä, ja tieto rangefinderien välisestä etäisyydestä toisiinsa.

tan(a)= (pitempi-rangefinder-matka - lyhempi-rangefinder-matka)/aluksen-rangefindereiden-valinen-matka

esim jossa rangefinderpera on aina pienempi:
```
aluksenpituus=10
rangefinderpera=12
rangefinderkeula=15
//HOX: rangefinderkeulan pitää olla suurempi kuin perän että toimii
aluksenkulma=ATAN((rangefinderkeula-rangefinderpera)/aluksenpituus)

```
Laskettu toimivaksi kumman arvon tahansa olevan pidempi esim2:
```
aluksenpituus=10
rfpera=12 //rangefinderpera
rfkeula=15 //rangefinderkeula
rferotus=ABS(rfkeula-rfpera)
if rfpera<rfkeula then lyhinmatka=rfpera else lyhinmatka=rfkeula end
aluksenkulma=ATAN(rferotus/aluksenpituus)


```
Todellinen matka alustaan saadaan laskettua kulman ja  lyhyemmän arvon avulla:
COS aluksenkulma * lyhyempi-rangefinder-matka

esim jossa rangefinderpera on aina pienempi:
```
aluksenpituus=10
rangefinderpera=12
rangefinderkeula=15
//HOX: rangefinderkeulan pitää olla suurempi kuin perän että toimii
aluksenkulma=ATAN((rangefinderkeula-rangefinderpera)/aluksenpituus)
todellinenetaisyys=COS aluksenkulma * rangefinderpera

```
Laskettu toimivaksi kumman arvon tahansa olevan pidempi esim2:
```
aluksenpituus=10
rfpera=12 //rangefinderpera
rfkeula=15 //rangefinderkeula
rferotus=ABS(rfkeula-rfpera)
if rfpera<rfkeula then lyhinmatka=rfpera else lyhinmatka=rfkeula end
aluksenkulma=ATAN(rferotus/aluksenpituus)
todellinenetaisyys=COS aluksenkulma * lyhinmatka

```

#binaari-funktiot
Koska starbasessa numerot ovat "64-bit fixed-point decimals" tämä tarkoittaa että voidaan säilöä arvoja numeroihin bitin avulla:
207125762626206225 = `1011011111110110111100100010100001001010101011101000010001`
jos käytämme 4 viimeistä bittiä operaattoreihin ja ehtojen tekemiseen. eli tässä tapauksessa:
`101101111111011011110010001010000100101010101110100001 0001`  eli `0001` = 1

