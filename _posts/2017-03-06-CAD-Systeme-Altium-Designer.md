---
layout: post
title:  "CAD Systeme - Altium Designer"
date:   2017-03-06 08:00
categories: altium-designer CAD-systeme
permalink: /posts/altium-designer
---

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-03-06/0.AltiumDesigner.png)
# CAD Systeme - Altium Designer
*Einführung und Designtips*

*Msc. Dipl. -Ing. Kemal Tokay*


## Templates

 * Die Templates werden über Preferences  System  New Document Defaults eingestellt.
 * PCB Project und Free Documents sollen verlinkt werden.

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-03-06/1.Templates.png)

## Libraries

 * Die Libraries werden Preferences  Data Management  Installed Libraries gewählt.
 * Durch viele lokale Libraries und Libraries am Server arbeitet Altium Langsamer. Daher können sie deaktiviert werden, wenn man sie gerade nicht braucht oder es wird empfohlen SVN zu nutzen und die Kopie lokal abzuspeichern.

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-03-06/2.Libraries.png)

## Schematic Template

 * In einem Schematic Template können die Texte Automatisch, Local oder Global geändert werden.
   * **Automatischen Wert:** z.B. DrawnDate 
 wenn man die Seite speichert, bekommt das aktuelle Datum automatisch.
   * **Local Werte:** Z.B DrawnName, Checked –Date  und –Name, Module
 Rechte Maus Taste  Options  Document Parameters.
   * **Global Werte:** z.B. Project, Component und DrawingNumber
 Project Options  Parameters

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-03-06/3.SchematicTemplate.png)

  * Wenn man die Parameters in mehreren Seiten auf Einmal ändern will
    *  Tools  Parameter Manager

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-03-06/3.SchematicTemplate2.png)

  * Wenn die Parameters geändert wird, wird danach bestätigt.  
    * Accept Changes (Create ECO)  Execute Changes  Close

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-03-06/3.SchematicTemplate3.png)

 ## Workspace Panels

  * Unten auf der Rechteseite des Editors.
  * Die Menus unter diese Panels, könnte beliebig ein- und aus- geblendet werden.

![](https://hakandilek.github.io/layout-pcb.de/static/img/2017-03-06/4.WorkspacePanels.png)
