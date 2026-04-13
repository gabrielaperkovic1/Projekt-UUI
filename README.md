# Ispitivanje utjecaja različitih arhitektura neuronske mreže na kvalitetu modela klasifikacije slika u dubokom učenju

_Ovaj projekt uspoređuje performanse različitih konvolucijskih neuronskih mreža (MobileNetV2 i EfficientNetB1) na CIFAR-10 skupu podataka. Cilj je ispitati utjecaj promjene rezolucije i metoda skaliranja podataka na konačnu točnost modela. Sva rješenja izrađena su u Visual Studio Code okruženju._


## **Upute za pokretanje**

**MobileNetV2**

- Verzija Pythona: 3.12.9

- Glavni program: main.py

Upute za konfiguraciju:
- Za testiranje na izvornoj rezoluciji (32x32):  Pokrenuti main.py.
  
- Za testiranje s povećanom rezolucijom (96x96):
  1. U datoteci main.py odkomentirati linije 14 i 15:
   
     `x_treniranje = tf.image.resize(x_treniranje, [96,96])`
     
     `x_testiranje = tf.image.resize(x_testiranje, [96,96])`
  2. U liniji 32 promijeniti parametar `input_shape=(32,32,3)` u `input_shape=(96,96,3)`.

____

**EfficientNetB1**
- Verzija Pythona: 3.12.4

- Za rad s parametrima s laboratorijskioh vježbi: Pokrenuti EfficientNet255.py.
- Za rad s optimiziranim skaliranjem podataka: Pokrenuti EfficientNet.py.

____

**Napomene**

- Verzije Pythona: Zbog usklađivanja biblioteka i stabilnosti rada, korištene su verzije 3.12.x umjesto 3.14.0.
- Rezultati: Detaljan ispis epoha i točnosti modela vidljiv je u terminalu nakon pokretanja skripti.

____

**Struktura datoteka**

- main.py: Implementacija MobileNetV2 arhitekture.
- EfficientNet.py: EfficientNetB1 uz korištenje namjenske `preprocess_input` funkcije.
- EfficientNet255.py: EfficientNetB1 uz ručno skaliranje podataka (/255).



Projekt izrađen u sklopu kolegija Uvod u umjetnu inteligenciju (UUI).
