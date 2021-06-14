# 33132-Haut-parleur Amplificateur GROVE

Haut-parleur Amplificateur GROVE [33132](https://www.pierron.fr/interface-arduino-uno-5969.html)

<div style="text-align: justify">Module amplificateur compatible Grove permettant de générer différents sons en fonction de la fréquence d'entrée. Le volume ajustable via un potentiomètre. Ce module se raccorde sur une sortie digitale du Base Shield via un câble 4 conducteurs.</div>

Caractéristiques techniques :
- Alimentation : 5 V
- Gain : 46 dB
- Fréquence maxi : 20 kHz

![L-33132](/img/L-33132.jpg)

# Usage :
Pour l’utilisation de ce module référez-vous aux indications présentes sur le circuit imprimé GROVE.

# Schémas :

![SCH-33132](/img/SCH-33132.jpg)
![BRD-33132](/img/BRD-33132.jpg)

# Complément sur la programmation :

Si vous souhaitez modifier l’intensité du son émis par le haut-parleur, référez-vous à l’image ci-dessous :

![C-33132](/img/C-33132.jpg)

# RESSOURCES À TÉLÉCHARGER :

Ressource utilisation : [LM386](https://github.com/pierron-asco-celda/33132-Haut-parleur_Amplificateur_GROVE/blob/main/src/Datasheet_LM386.pdf)

# Exemple :
### Arduino / C++
```cpp
/*
    ** Haut-parleur module Grove **
       PIN 7 Module shield GROVE
       Haut-parleur notes fréquence basse. 
*/

#define SPEAKER 7

int BassTab[] = {1911, 1702, 1516, 1431, 1275, 1136, 1012};

void setup() {
  pinInit();
}
void loop() {
  for (int note_index = 0; note_index < 7; note_index++)
  {
    sound(note_index);
    delay(500);
  }
}
void pinInit() {
  pinMode(SPEAKER, OUTPUT);
  digitalWrite(SPEAKER, LOW);
}
void sound(uint8_t note_index) {
  for (int i = 0; i < 100; i++)
  {
    digitalWrite(SPEAKER, HIGH);
    delayMicroseconds(BassTab[note_index]);
    digitalWrite(SPEAKER, LOW);
    delayMicroseconds(BassTab[note_index]);
  }
}
```
## À propos :

PIERRON ASCO-CELDA (https://www.pierron.fr).
