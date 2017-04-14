---
layout: post
title:  "Leitungslänge Anpassung"
date:   2017-04-11 08:00
categories: Altium-designer
permalink: /posts/Leitungslaenge
---

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/0.Laenge_uebersicht.png) 

# Leitungslänge Anpassung 
*Länge Anpassung auf der Platine* 

## Übersicht
* Wie schnell bewegt sich das Signal auf der Platine? 
* Was ist die Kritische Leitungslänge? 
* Wann ist die Leitungslänge Anpassung nötig? 
* Was für Nachteile hat die Leitungslänge Anpassung? 
* Wie realisieren wir es bei Altium? 

## Ausbreitungsgeschwindigkeit
* Sehr hohe aber begrenzte Geschwindigkeit.
* In Luft breiten sich Signale mit Lichtgeschwindigkeit aus. Auf der Platine sind sie langsamer. 

  (LP-Meterial) = 2.8..4,3

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/1.Er_Lagen.png) 

* Layer1 = Er = 2,8
  Layer2 = Er = 4,2
  Layer3 = Er = 3,8

* 50..70% der Lichtgeschwindigkeit. 15..21 cm/ns

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/2.Er_Lagen.png) 


## Kritische Leitungslänge
* Resonanzeffekte: auf Leitungen und Potentiallagen ⇒ Störabstrahlung  
* Impuls-Reflexionen: an Leitungsenden/ Durchkontaktierung ⇒ Fehltriggerungen
  Die beiden HF-Effekte werden ab einer kritischen Länge der Leiterbahnen wirksam.
  Die kritische Länge deutlich kleiner als die Wellenlänge λ sein. 

  * Ikrit = Cp.tr.1/3 --> tr= (risetime oder falltime)
  * Ikrit = 15 cm/ns . tr. 1/3 --> Lkrit = 5cm/ns . tr

  z.B: AT91SAM9261S hat minimale Anstieg zeit ca. 4ns
  Lkrit = 5cm/ns . tr --> Lkrit = 5cm/ns . 4ns = 20cm = 200mm Kritische Länge

 Merkmale: Bei einer Leitungslaenge von bis zu 20cm treten keine nennenswerten Reflexionen auf und eine Terminierung ist nicht Nötig.

## Leitungslänge Anpassung
* Ausbreitungsgeschwindigkeit ist für Leiterplattenmaterial mit einem Er ist 15cm/ns. Die Signalverzögerung   0,07ns/cm

* Für synchrones Schalten müssen alle Leitungen im Idealfall die selbe Gesamtlänge zwischen Treiber und den Empfänger haben.

* Entsprechend   0,07ns/cm sind bei ns-Impulsen Wegunterschiede im cm-Bereich noch zulässig.

* Z.B. AT91SAM9261S hat minimale Anstieg zeit ca. 4ns
 --> Lkrit = 5cm/ns .tr --> Lkirt= 5cm/ns . 4ns = 20cm = 200mm
 
 Die Leitungslänge differenz bis zum 100mm bei dieser Takt würde man keine Leitungs-Länge anpassen.

* Nacteile zur Leitungslänge Anpassen:
- Weniger GND-Fläche
- Komplexität der Leiterplatte wird ersteigt.
- Verschlechterung bei EMV
- Erhöhte Gefahr bei der Leitungskopplung (übersprechen)
- Mehr benötigte Platz zur Routing

## Leitungslänge Anpassung bei Altium

* Zwischen Sender und Empfänger meisetn liegen Serien Wiederstände oder Andere Bauteile.

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/3.xSignal.png) 

* Meisten verteil sich das Signal Y-Förmig.
![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/4.YForm.png)

* Design --> xSignals --> Run xSignals Wizard


to be defined.....










