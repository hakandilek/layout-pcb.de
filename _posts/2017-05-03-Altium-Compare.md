---
layout: post
title:  "Altium PCB Version Compare"
date:   2017-05-03 08:00
categories: Altium-designer Compare Function
permalink: /posts/altium-Compare
---

# Altium Designer Compare Function / Revisionen Vergleichen
*Zwei PCB-Revisionen werden durch diese Funktion vergliechen*



<!--more-->

 * In Altium Designer kann man das Layout von zwei Leiterplatten vergleichen. sodass man die Änderungen im Überblick sieht und kontrolliert, dass nicht aus versehen etwas verschoben wurde.

## 1. Storage Manager auswählen

![](https://hakandilek.github.io/layout-pcb.de/static/img/compare/1_compare_pcb.png)


Im Storage Manager kann man seine Leiterplatte unter Project files auswählen (1). Danach kann man im Abschnitt Timeline die beiden Versionen (mit Strg/Ctrl) markieren, die verglichen werden sollen (2). Mit der rechten Maustaste auf eine der beiden Versionen kann man Compare (3) aktivieren.

![](https://hakandilek.github.io/layout-pcb.de/static/img/compare/2_Differences.png)


Die Dateien werden nun vom SVN Server geladen und im aktiven Fenster wie unten nebeneinander angezeigt. 

![](https://hakandilek.github.io/layout-pcb.de/static/img/compare/3_Differences.png)




## 2. Collaborate, Compare and Merge auswählen

![](https://hakandilek.github.io/layout-pcb.de/static/img/compare/4_Collaborate.png)

Am besten man aktiviert die neuste Version mithilfe der Maustaste. Im Collaborate, Compare and Merge Fenster klickt man nun auf "Click to show differences against any PCB Document". In dem Fenster stehen nun alle geöffneten PCBs zur Auswahl (2). Man wählt die richtige Version aus, um die beiden zu vergleichen. Das berechnen der Unterschiede dauert etwas. Danach erscheint folgendes Bild.



## 3. Unterschiede finden

![](https://hakandilek.github.io/layout-pcb.de/static/img/compare/4_Collaborate2.png) 
![](https://hakandilek.github.io/layout-pcb.de/static/img/compare/5_Differences.png)

  Die Difference Map wird nun farbig und zeigt Kästchen an (3). Bleiben Kästchen grau, so hat sich in dem Bereich nichts geändert. Die Größe der Kästchen kann man auch verändern (1). Klickt man auf ein bestimmtes Kästchen wird das Kästchen im PCB Viewer in beiden Versionen automatisch synchron angezeigt. Man kann sich auch in der vorher ausgewählten Version die Unterschiede anzeigen lassen (2). Die Unterschiede werden dann überlagert dargestellt. Man sollte sich alle Lagen einzeln anschauen (4), dann sieht man auch sofort in der Difference Map in welchen Bereich sich etwas verändert hat. 

