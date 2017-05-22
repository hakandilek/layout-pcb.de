---
layout: post
title:  "Leitungslängen Anpassung"
date:   2017-04-11 08:00
categories: Leitungslaenge-Anpassung
permalink: /posts/Leitungslaenge
---

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/0.Laenge_uebersicht.png) 

# Leitungslängen Anpassung 
*Längen Anpassung auf der Platine* 



## Übersicht

* Wie schnell bewegt sich das Signal auf der Platine? 
* Was ist die Kritische Leitungslänge? 
* Wann ist die Leitungslängen Anpassung nötig? 
* Was für Nachteile hat die Leitungslängen Anpassung? 
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

## Leitungslängen Anpassung

* Ausbreitungsgeschwindigkeit ist für Leiterplattenmaterial mit einem Er ist 15cm/ns. Die Signalverzögerung   0,07ns/cm

* Für synchrones Schalten müssen alle Leitungen im Idealfall die selbe Gesamtlänge zwischen Treiber und den Empfänger haben.

* Entsprechend   0,07ns/cm sind bei ns-Impulsen Wegunterschiede im cm-Bereich noch zulässig.

* Z.B. AT91SAM9261S hat minimale Anstieg zeit ca. 4ns
 --> Lkrit = 5cm/ns .tr --> Lkirt= 5cm/ns . 4ns = 20cm = 200mm
 
 Die Leitungslängen differenz bis zum 100mm bei dieser Takt würde man nichts anpassen.

* Nacteile zur Leitungslängen Anpassen:
- Weniger GND-Fläche
- Komplexität der Leiterplatte wird ersteigt.
- Verschlechterung bei EMV
- Erhöhte Gefahr bei der Leitungskopplung (übersprechen)
- Mehr benötigte Platz zur Routing

## Leitungslängen Anpassung bei Altium

* Zwischen Sender und Empfänger meisetn liegen Serien Wiederstände oder Andere Bauteile.

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/3.xSignal.png) 

* Meisten verteil sich das Signal Y-Förmig.


![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/4.YForm.png)


z.B. Die Leitungen zwischen Mikrokontroller und DDR Rams

* Design --> xSignals --> Run xSignals Wizard

Select the source component (Signal Quelle = Mikrokontroller)

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/5.DDR_Signal.png)

Alle Signale zum diesen Familie werden gewählt.

Select Destination Components (Signal Ziel = DDR-Rams)

Danach berechnet Altim automatisch die Signale zwischen Mikrokontroller und DDR Bausteine in einer Tabelle. 

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/6.xSignal_routes.png)

so definiert man die Leitungsgruppe im PCB mit Altium. Dann kann man die Längen unter einer Gruppe anpassen.

### Wichtige Parameters beim High Speed Signalen

* Hier sind 5 Goldene Regeln gültig


1. Single Ended oder Differential pair Impedance

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/7.Anpaasung_Altium.png)

2. Leitungslängen Anpassung zwischen Differential Signalen

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/8.Diff_Signal_Anpassung.png)



* Die Space soll direkt am Anfang seien.
* Wenn mehr als 2 Space Nötig ist, soll man ein einziges Gröseres Space direkt am Anfang vorsehen.

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/9.Diff_Signal_3Space.png)


* unten wird ein schlechtes Beispiel dargestellt.

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/10.Diff_Sig_Bad.png)


* unten wird ein gutes Beispiel dargestellt.

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/11.Diff_Sig_good.png)

* Design Rule für Differentiall Signale definieren.

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/12.Diff_Sig_Rules.png)

3. Abstände zwischen Leitungen (Crosstalk)

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/13.crosstalk.png)

Schlecht: 

Weil das Signal kann überspringen.

Gut: 
Winkel : 45°; 
Abstand zwischen Leitungen minimal = 3x Leitung Dicke
Ideal = 5x Leitung Dicke

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-04-10/14.Ideal_Routing.png)

4. Gleiche Signalgrouppe werden zusammen geführt.

5. Man soll maximal 5Leitungen Parallel durchführen dann soll ein GND Signal mit geführt werden.










