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
