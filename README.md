# yolol-stuff
Ohjeita ja muistiinpanoja

# Aluksen kulma suhteessa laskeutumisalustaan
Rangefinderin avulla voidaan laskea aluksen kulma suhteessa laskeuduttavalle pinnalle. Tarvitaan 2 rangefinderiä, ja tieto rangefinderien välisestä etäisyydestä toisiinsa.

tan(a)= (pitempi-rangefinder-matka - lyhempi-rangefinder-matka)/aluksen-rangefindereiden-valinen-matka
esim1:
```
aluksenpituus=10
rangefinderpera=12
rangefinderkeula=15
//HOX: keulan pitää olla suurempi kuin perän että toimii
kulma=ATAN((rangefinderkeula-rangefinderpera)/aluksenpituus)

```

laskettu automaattisesti esim2:
```
aluksenpituus=10
rfpera=15 //rangefinderpera
rfkeula=12 //rangefinderkeula

if rfpera<rfkeula then rferotus=rfkeula-rfpera else rferotus=rfpera-rfkeula end
kulma=ATAN(rferotus/aluksenpituus)

```
