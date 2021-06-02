# 33188 CAPTEUR DE PRESSION DIFFÉRENTIEL AU FORMAT GROVE

CAPTEUR DE PRESSION DIFFÉRENTIEL AU FORMAT GROVE [33188](https://www.pierron.fr/capteur-de-pression-dans-un-liquide.html)

![33188](/img/L-33188.png)

# Installation :
Créer un nouveau répertoire nommé "Pierron_33188" dans le dossier "libraries" de votre dossier Arduino.
Y placer tous les fichiers.
Ou
télécharger le dépôt en ZIP et dans l'IDE Arduino : Croquis / inclure bibliothèque / ajouter la bibliothèque ZIP.

# Usage :
Pour utiliser la librairie dans votre propre projet, importez-la avec  *Sketch > Import Library*.

# RESSOURCES À TÉLÉCHARGER :

Ressource utilisation : [NOTICE](https://github.com/pierron-asco-celda/33188-CAPTEUR-PRESSION/blob/main/src/Pierron-33188-Datasheet.pdf)

# Schémas :

![SCH-33188](/img/SCH-33188.png)

![BRD-33188](/img/BRD-33188.png)

# Exemple :
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
## À propos :

PIERRON ASCO-CELDA (https://www.pierron.fr/).