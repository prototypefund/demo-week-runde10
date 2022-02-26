---
layout: project
title: "fingerfunke"
image: /assets/images/project_images/fingerfunke/header.jpg
authors:
  - author: Katharina Brauner
    link: 
  - author: Tim Lindenau
    link: 
  - author: Robin Naumann
    link: 
  - author: Clara Simon
    link: 
  - author: Aniella Tiedje
    link:  
brief: "Wir vernetzen gehörlose, schwerhörige und hörende Menschen."
summary: "fingerfunke ist eine Community-App für Gebärdensprachler*innen."
---

<div class="iframe-container">
    <iframe src="https://www.youtube-nocookie.com/embed/w_r1zKVNIc4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

## Die Geschichte

Mit einer simplen Idee, die in einem Gespräch zwischen Freundinnen entstand, die eine taub, die andere hörend, begann unser Projekt in einem Kreuzberger Café in Berlin. Ohne IT-Hintergrund nur mit einer Vision fing die Reise an. Über viele unterstützende Projekte, Hand-zu-Hand- und Mund-zu-Mund-Propaganda, einem Hackathon und dem Prototype Fund sind wir zu einem Team aus fünf Leuten gewachsen, die nun einen ersten Prototypen entwickelt haben.

## Die Idee

Bisher fehlen städteübergreifende und übersichtliche Plattformen, die Angebote und Veranstaltungen in Deutscher Gebärdensprache anzeigen. Mit der Funktion, selbstständig Gruppen und Veranstaltungen zu gründen, bietet fingerfunke die Möglichkeit, sich unkompliziert mit Signer*innen aus der Umgebung zu vernetzen und die eigene Freizeit selbstbestimmt zu gestalten.

## Unser Ansatz

Wir arbeiten möglichst eng mit der Community zusammen und arbeiten an Lösungen für ein Problem, das uns durch persönliche Erfahrung bekannt ist. Alle relevanten Funktionen sollen auf möglichst intuitive Weise implementiert werden. In Abgrenzung zu anderen Vernetzungsplattformen ist die Darstellung der Inhalte zum Großteil videobasiert und entspricht damit den visuellen Ansprüchen von Signer*innen. Mit mehreren User-Umfragen haben wir das Design und die Funktionen der App getestet und lassen das Feedback in die nächsten Versionen einfließen.  

## Der Prozess

Da die meisten Teammitglieder in verschiedenen Städten wohnen, fand unsere Kommunikation von Beginn an online statt. Im ganzen Förderzeitraum konnten wir uns auch wegen der Pandemie nur zwei Mal in Berlin treffen, was uns aber jedes Mal einen Motivationsschub gab. Die Online-Treffen haben funktioniert, haben uns aber auch viel Kraft und Durchhaltevermögen gekostet. Hinzu kam die Herausforderung, in einem gemischten Team mit gebärdensprachkompetenten und nicht-gebärdenden Menschen zusammenzuarbeiten. Wir nutzten dabei meistens die Untertitelfunktion bei Skype oder es wurde gedolmetscht. Wir arbeiteten in verschiedenen Gruppen parallel an der Öffentlichkeitsarbeit, der Evaluierung der App-Funktionen und der technischen Entwicklung. Für uns alle war das eine neue, herausfordernde Erfahrung. Als junges Team haben wir bisher nichts dergleichen gestemmt und dabei wahnsinnig viel über Teambuilding und Kommunikation gelernt, auch dank zwei Coachings, die wir durch das Funding genießen durften.

## Tech

Wir möchten möglichst viele Menschen aus der Zielgruppe mit fingerfunke erreichen, deshalb war von Beginn an klar, dass die App sowohl für iOS als auch Android verfügbar sein muss. Aus diesem Grund verwenden wir die Programmiersprache Flutter. Im Backend setzen wir auf den Service Firebase von Google, was für unsere Zwecke ausreicht und die Komplexität enorm reduziert. Wir sind ein junges Team aus Studierenden, weshalb es bei der Entwicklung einige Herausforderungen für uns gab. Eine der größten war, die Videofunktion zu integrieren. Videos effizient für eine große Anzahl an Nutzer\*innen zur Verfügung zu stellen, war komplizierter als gedacht. Bevor das Video abrufbar ist, muss es encodiert werden, um zum einen die Datenmenge zu reduzieren aber auch, um es in verschiedenen Qualitätsstandards, abhängig von der verfügbaren Datenrate, streambar zu machen. Auch wenn wir für die Mammutaufgabe des Encodierens den externen Service MUX verwenden, bleibt die Aufgabe weiterhin komplex. Es wird eine Asynchronität eingeführt zwischen dem Hochladen eines Videos und dem Zeitpunkt, zu dem es fertig encondiert und abrufbar ist. Im jetzigen Prototypen können bereits Events erstellt und Videos aufgenommen werden. Außerdem kann man bei Events zusagen und sie speichern.

![fingerfunke](/assets/images/project_images/fingerfunke/FingerfunkeBild.gif)

![Screenshot der App](/assets/images/project_images/fingerfunke/app_screenshots.gif)

## Ausblick

Für uns endet die jetzige Runde mit dem Prototype Fund und wir sind alle motiviert, weiterzuarbeiten. Geplant sind eine Kalenderfunktion für Veranstaltungen, die mit dem privaten Kalender synchronisiert werden, sowie eine Karte für die Angabe des Standortes. Wir wollen in diesem Jahr noch einige weitere Funktionen implementieren und mit der Zielgruppe testen. Auch am Design arbeiten wir weiter an visuell ansprechenden Screens. Der Plan ist, die App noch dieses Jahr zu veröffentlichen!

Vielen Dank an den Prototype Fund, das BMBF, das DLR und die super Betreuung von Patricia und Marie! Zudem sind wir sehr dankbar für die Unterstützung der Coaches!

Folgt uns auf [Instagram](https://www.instagram.com/fingerfunke)!

Website: [fingerfunke.app](https://fingerfunke.app)

Kontakt: [info@fingerfunke.app](mailto:info@fingerfunke.app)

