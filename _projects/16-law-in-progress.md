---
layout: project
title: "Law in Progress"
image: /assets/images/project_images/law-in-progress/header.png
authors:
  - author: Tobias Sterbak
    link: https://tobiassterbak.com
  - author: Noa Tamir
    link: https://twitter.com/noatamir
brief: "Wir machen Gesetzesänderungen transparent."
summary: "Das Online-Tool 'Law in Progress' macht Gesetzentwürfe und deren Konsequenzen für bestehende Gesetze durch automatische Erstellung einer Synopse sichtbar und nachvollziehbar."
---

![lip_logo_1](/assets/images/project_images/law-in-progress/lip_logo_1.png)

## Was sind Änderungsgesetze und warum könnten sie besser sein?

Die Nachvollziehbarkeit des Gesetzgebungsprozesses ist für eine Demokratie essentiell.  Wenn ein Gesetz nicht völlig neu erlassen wird, sondern Änderungen an einem bestehenden Gesetz gemacht werden, ist das Gesetz ein sogenanntes Änderungsgesetz. Dieses besteht aus einer Liste von Änderungsbefehlen, die sich auf ein oder mehrere bereits bestehende Gesetze beziehen und nur relativ dazu zu verstehen sind. Entwürfe für Änderungen von Gesetzen sind für Nichtjurist\*innen dadurch nur schwer lesbar und selbst für geübte Jurist\*innen eine Herausforderung.

![screenshot_aenderungsgesetz](/assets/images/project_images/law-in-progress/screenshot_aenderungsgesetz.png)

Die Berichterstattung und Herstellung einer öffentlichen Debatte über Gesetzentwürfe wird aufgrund des Umfangs der erforderlichen Forschungs- und Analysetätigkeit erschwert.

## Was tut Law in Progress?

Mit der Web-App von Law in Progress wollen wir den Zugang zu Gesetzesänderungsvorhaben erleichtern. Dafür machen wir Gesetzentwürfe und deren Auswirkungen auf bestehende Gesetze durch automatische Erstellung einer Synopse sichtbar und nachvollziehbar. Textänderungen werden durch Gegenüberstellungen und Hervorhebungen kenntlich gemacht und jede Änderung dem jeweils zugrundeliegenden Änderungsbefehl zugeordnet. Nutzer\*innen können entsprechende Entwürfe von Änderungsgesetzen über eine Uploadmaske hochladen und erhalten dann eine interaktive, konfigurierbare Synopse.

![law_in_progress_how_to](/assets/images/project_images/law-in-progress/law_in_progress_how_to.gif)

## Law in Progress von innen

Das Backend von Law in Progress ist vollständig in Python geschrieben. Für die Web-App nutzen wir fastAPI mit jinja Templates. Das Frontend wurde mit dem css-Framework bulma gestaltet. Akutell ist die Law in Progress Web-App bei heroku gehostet. Für den Zugang zu bestehenden Gesetzen nutzen wir die API von [rechtsinformationsportal.de](https://github.com/tech4germany/rechtsinfo_api), einem Tech4Germany-Projekt, von der wir aktuelle Gesetze in einem strukturierten Format beziehen können.

Zum Verarbeiten und Anwenden der Änderungsbefehle aus dem Änderungsgesetz, parsen wir zunächst das Änderungsgesetz und überführen jeden Änderungsbefehl in eine standardisierte Datenstruktur. Diese enthält Informationen über die Art und Weise der Änderung sowie über die Stelle der Änderung. Dann beziehen wir die Texte der betroffenen Gesetze aus der Datenbank von rechtsinformationsportal.de und überführen diese in eine Baum-Datenstruktur. In dieser Datenstruktur nehmen wir nun die Änderungen vor und setzen anschließend den Text wieder zusammen. Zuletzt erstellen wir dann aus der Gegenüberstellung von altem und neuem Text die Synopse ("diff"). Diese wird dann für das Web-Tool mit Hervorhebungen als HTML erzeugt.

![law-in-progress-flowchart](/assets/images/project_images/law-in-progress/law-in-progress-flowchart.png)

## Wie es mit Law in Progress weitergeht

Kurz nach Start des Projekts wurde aus dem aktuellen Koalitionsvertrag von 2021 klar, dass die Politik das Problem ebenfalls angehen will. So sollen in Zukunft Änderungsgesetze zusammen mit Synopsen veröffentlicht werden. Über diese Wahrnehmung des Problems und diese Pläne zur Lösung freuen wir uns. Im Optimalfall wird unser Projekt somit in Zukunft überflüssig sein. Allerdings ist die Art und Maschinenlesbarkeit der Veröffentlichung sowie auch der Zeitplan für die Umsetzung bisher noch unklar. Zudem ist auch nicht klar, zu welchem Zeitpunkt im Gesetzgebungsprozess die Synopse veröffentlicht werden soll. Wir gehen also davon aus, dass weiterhin Bedarf für die systematische, maschinelle Verarbeitung von Änderungsgesetzen und leicht zugängliche Synopsen besteht.

Wir sehen bereits, dass auch einzelne Komponenten der Software jenseits der Erstellung von Synopsen für sich allein schon nützlich sein können. Aktuell bietet der Aufbau des Tools nur den Zugang über das Web-Frontend und über ein Skript. Dort steht jeweils nur der Ende-zu-Ende-Prozess von Änderungsgesetz zu geänderter Gesetzesversion zur Verfügung. In nächsten Schritten soll das Backend modularer als Pythonpackage strukturiert werden und darüber zum Beispiel direkten Zugang zum Parsen von Änderungsgesetzen und Anwenden von Änderungsbefehlen auf bestehende Gesetze bieten. Damit wird das Tool interessanter und nützlicher für Forschende und Datenjournalist\*innen mit Programmiererfahrung.

Aktuell ist die Web-App Law in Progress als beta-Version online verfügbar und wird auch nach Ende des Förderzeitraums weiter betrieben und entwickelt. Teile der Komplexität von Änderungsgesetzen werden aktuell noch nicht ausreichend abgebildet, was eine Weiterentwicklung nötig macht. Auch im Bereich UI und Design sind Verbesserungen notwendig. Darüberhinaus sind wir immer auf der Suche nach weiteren Anwendungsfällen für das Projekt. Solltest du also zur Entwicklung beitragen wollen und/oder die Software verwenden wollen, wende dich gerne per [E-Mail](mailto: hello@lawinprogress.de) an uns.

Wir bedanken uns herzlich beim Bundesministerium für Bildung und Forschung sowie beim Projektträger DLR und dem Prototype Fund.

## Links

- Source code unter MIT Lizenz: [https://gitlab.com/nototast/lawinprogress/](https://gitlab.com/nototast/lawinprogress/)
- Demo: [app.lawinprogress.de](http://app.lawinprogress.de)
- Website: [lawinprogress.de](https://lawinprogress.de)
