# 33188 CAPTEUR DE PRESSION DIFFERENTIEL AU FORMAT GROVE

CAPTEUR DE PRESSION DIFFERENTIEL AU FORMAT GROVE [33188](https://www.pierron.fr/capteur-de-pression-dans-un-liquide.html)

![33188](/Img/33188.png)

# Installation
Créer un nouveau repertoire nommé "Pierron_33188" dans le dossier "libraries" de votre dossier Arduino.
Y placer tous les fichiers.
Ou
Télécharger le dépot en ZIP et dans l'IDE Arduino : Croquis / Inclure bibliothèque / Ajouter la bibliothèque ZIP

# Usage
Pour utiliser la librairie dans votre propre projet, importer la avec  *Sketch > Import Library*.

# Schémas :

![SCH-33188](/Img/SCH-33188.png)

![BRD-33188](/Img/BRD-33188.png)

# Exemples :
### Arduino / C++
```cpp
// Baud rate 9600

#include "Pierron_33188.h"

Pierron_33188 capteur = new Pierron_33188();

void setup(){
  Serial.begin(9600);
  Serial.println("Calibration du capteur.\nAppuyer sur une touche pour continuer.");
  while (Serial.available() == 0) {
    // Wait for User to Input Data
  }
  capteur.calibre();
}

void loop(){
  float p = capteur.read();
  Serial.print("Pression : ");
  Serial.print(p);
  Serial.println(" hPa");
  delay(1000);
}
```
## A propos

PIERRON ASCO-CELDA (https://www.pierron.fr/)