---
layout: project
title: "Cover-REST"
image: /assets/images/project_images/cover-rest/header.jpg
authors:
  - author: Cover-REST Projekt
    link: https://cover-rest.gitlab.io/
  - author: Thorsten Behrens
    link: https://de.linkedin.com/in/thorsten-behrens-4b100417
  - author: Urs Svante Schubert
    link: https://www.linkedin.com/in/svante-schubert-2913232/
  - author: Linus Behrens
    link: https://github.com/Lin2D2
brief: "Wir automatisieren das Finden von Features im Quellcode."
summary: "Du willst ein Feature implementieren, weisst aber nicht wo sich der Code versteckt? Cover-REST hilft Dir, die relevanten Stellen aus Millionen Zeilen Quelltext zu finden."
---

<div class="iframe-container">
    <iframe src="https://www.youtube-nocookie.com/embed/vDa7Vd_HnOg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

## Cover-REST ermöglicht das einfache Auffinden von Code in großen Projekten

COVER-REST ist ein Projekt, welches das Auffinden von Codestellen vereinfachen will - gleichsam wie eine Karten-App fürs Handy, aber zur Navigation im Quelltext.

Wir nutzen dafür sogenannte Coverage-Analysen - das sind Aufzeichnungen des Programmflusses beim Verarbeiten von Testdaten.

Damit finden wir heraus, an welchen Stellen das Programm "vorbei kommt", z. B. beim Laden eines bestimmten Dokumentes.

Machen wir das zweimal - einmal mit Daten, welche ein bestimmtes Feature enthalten (z. B. fettgedruckten Text), und einmal ohne - dann können wir die Differenz berechnen, und haben das Feature im Programm-Quelltext gefunden!

Unser erster Demo-Anwendungsfall hierfür ist das LibreOffice-Projekt, welches mit insgesamt über 10 Millionen Zeilen Code dringend modernes Kartenmaterial benötigt.


## Von der Idee zum Prototypen

Über die Projektlaufzeit haben wir in mehreren Iterationsschritten und
nach Sichtung von bestehenden Lösungen einen Prototypen basierend auf
der [Jenkins-CI-Plattform](https://www.jenkins.io/) aufgesetzt.

Damit konnten wir mit vertretbarem Aufwand unsere Annahmen validieren,
und gleichzeitig für das LibreOffice-Projekt eine konkrete
Implementierung schaffen (da LibreOffice ohnehin [Jenkins als CI](https://ci.libreoffice.org/)
verwendet).

Bisher erreicht haben wir:
* die automatische Generierung von Feature-Testdateien mit dem [OFD Toolkit](https://github.com/tdf/odftoolkit/tree/coverage/odfdom/src/test/resources/test-input)
* die Generierung von Coverage-Analysen in Python, Java und C++, sowie
  die Konversion in ein einheitliches Dateiformat
* die Differenzberechnung der Coverage aus orthogonalen Einzelfeatures
* die Visualisierung des Ergebnis-Diffs im Rahmen der Jenkins-CodeCoverage-API


## Links

* [Projekt-Homepage](https://cover-rest.gitlab.io/)
* [Demo-Instanz](https://coverrest.allotropia.de/) für das LibreOffice-Projekt
* [Präsentation](https://fosdem.org/2022/schedule/event/lotech_improvedcoverage/) „Improved coverage analysis for LibreOffice's CI“ auf der FOSDEM 2022
* [Code-Repos](https://gitlab.com/cover-rest)


## Danksagung

Wir danken dem Prototype Fund für die Förderung, welche uns erst
ermöglicht hat, mit dem notwendigen Fokus an diesem Projekt zu
arbeiten. Wir hoffen, damit in Zukunft vielen Entwicklern das Leben zu erleichtern!

Soundtrack Video:

> Brush Strokes by texasradiofish (c) copyright 2022  
> Licensed under a Creative Commons Attribution Noncommercial (3.0) license. http://dig.ccmixter.org/files/texasradiofish/64682  
> Ft: billraydrums  
