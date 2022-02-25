---
layout: project
title: "Cover-REST"
image: /assets/images/project_images/cover-rest/header.jpg
authors:
  - author: Linus Behrens
    link: 
  - author: Thorsten Behrens
    link:
  - author: Urs Svante Schubert
    link: 
brief: "Wir automatisieren das Finden von Features im Quellcode."
summary: "Du willst ein Feature implementieren, weisst aber nicht wo sich der Code versteckt? Cover-REST hilft Dir, die relevanten Stellen aus Millionen Zeilen Quelltext zu finden."
---

<div class="iframe-container">
    <iframe src="https://www.youtube-nocookie.com/embed/vDa7Vd_HnOg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

COVER-REST ist ein Projekt, welches das Auffinden von Codestellen vereinfachen will - gleichsam wie eine Karten-App fürs Handy, aber zur Navigation im Quelltext.

Wir nutzen dafür sogenannte Coverage-Analysen - das sind Aufzeichnungen des Programmflusses beim Verarbeiten von Testdaten.

Damit finden wir heraus, an welchen Stellen das Programm "vorbei kommt", z. B. beim Laden eines bestimmten Dokumentes.

Machen wir das zweimal - einmal mit Daten, welche ein bestimmtes Feature enthalten (z. B. fettgedruckten Text), und einmal ohne - dann können wir die Differenz berechnen, und haben das Feature im Programm-Quelltext gefunden!

Unser erster Demo-Anwendungsfall hierfür ist das LibreOffice-Projekt, welches mit insgesamt über 10 Millionen Zeilen Code dringend modernes Kartenmaterial benötigt.


