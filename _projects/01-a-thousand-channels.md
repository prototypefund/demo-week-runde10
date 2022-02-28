---
layout: project
title: "A Thousand Channels"
image: /assets/images/project_images/a-thousand-channels/header.jpg
authors:
  - author: A Thousand Channels
    link: https://www.a-thousand-channels.xyz/
brief: "Wir bauen eine digitale Plattform für queere Geschichten im urbanen Raum."
summary: "A 1000 channels ist ein Softwareprojekt, in dem wir seit September 2021 eine queere Mappingplattform entwickeln, mit der queere Narrationen leicht zugänglich auf einer Karte visualisiert und veröffentlicht werden können."
---

## A Thousand Channels – eine queere 🏳️‍🌈 Mapping 🌎 Plattform 🎁

![Screenshot eines Whiteboards zur Ideenfindung des Projekts](/assets/images/project_images/a-thousand-channels/original.png)

### Ein digitales Angebot um queere Geschichten zu kartieren 🧶

Seit September 2021 entwickeln wir eine Mappingplattform, mit der queere Narrationen leicht zugänglich auf einer Karte visualisiert und veröffentlicht werden können.

Die vielfältigen sozialen und politischen Aktivitäten queerer Menschen sind meist flüchtig, temporär und kein selbstverständlicher Teil des öffentlichen Bildes einer Stadt. Mit _[A 1000 Channels](https://www.a-thousand-channels.xyz/)_ ist eine Plattform entstanden, die queeren Akteur\*innen, Gruppen, Projekten eine Möglichkeit bietet, von diesen Räumen und Ereignissen zu berichten und sie sichtbar zu machen.

Wir haben dabei versucht, den Prozess des Mappings aus einer queeren Perspektive zu betrachten. Grundlage war die Idee, die Darstellung einer Navigations- oder Straßenkarte zu vermeiden, sondern sie in einer reduzierten Form zu gestalten, so daß sie den Fokus auf das Zusammenspiel von bestimmten Orten und den Menschen, die diese beschreiben, setzt.

So gibt es mit unserer Plattform die Möglichkeit, Beziehungen – Relations – zwischen Orten zu visualisieren und so Bewegungen, Verdichtungen und andere, manchmal nur temporäre und subjektive Beziehungen darstellbar zu machen. Auch die Anreicherungen eines Ortes durch verschiedene Perspektiven – wir haben sie Annotations genannt – soll die Vielschichtigkeit in der Wahrnehmung von Orten und Ereignissen wiedergeben.

![Animation eines Prototypen für die Visualisierung von Beziehung zwischen Orten](/assets/images/project_images/a-thousand-channels/original.gif)

Mit unserer Plattform wollen wir einen Werkzeugkasten anbieten, der auch ohne besonderes technisches Wissen angewendet werden kann. Als Ergebnis des Mappings gibt es einen Webclient, um die Karte öffentlich nutzen zu können. Ein weiterer Fokus war die Implementierung von Funktionen zum Schutz der Privatsphäre. Eine Map-to-go Funktion erlaubt die Veröffentlichung des Mappings auf der eigenen Website.

Wir sind sehr happy, dass wir im Entwicklungsprozess [erste Mappings](https://www.a-thousand-channels.xyz/#references) integrieren konnten. Dabei wurden unsere "Baustelle" für das Kartieren queerer Themen eingesetzt, entwickelte Features erprobt und neue Bedürfnisse formuliert, während wir mit dem Feedback aus diesen Anwendungen unser Projekt verbessern und weiterentwickeln konnten.

Unseren [Design- und Entwicklungsprozess haben wir in einem Are.na-Channel](https://www.are.na/a-thousand-channels/project-progress) dokumentiert.

![Scribble für ds Userinterface des Webclients](/assets/images/project_images/a-thousand-channels/a1000c-client-scribble.jpg)


### Ein Baukasten 🔧

Das Bild vom Baukasten ist sicherlich schon häufig bemüht worden, trotzdem scheint es uns auch hier zu passen. Wir stellen verschiedene Tools - eben Funktionen, Werkzeuge, Bausteine - zur Verfügung, die genutzt werden können. Nicht alle Optionen sind notwendig: Wichtig ist uns mehr, was erzählt werden soll und was dafür gebraucht wird – oder um im Konjunktiv zu sprechen: gebraucht werden könnte.
In diesem Sinn verstehen wir den Baukasten als ein Angebot, aus dem genommen und geschöpft werden kann.

### Backend 💻

Wir haben für das Projekt das ORTE Backend eingesetzt und an die Bedürfnisse, die in unserem Konzept und dann bei den Betatests und Probeanwendungen formuliert wurden, angepasst. Dabei haben wir die Software um Export- und Datenschutzfunktionen erweitert und die Möglichkeit geschaffen, Beziehungen zwischen Orten und Ereignissen zu visualisieren und Orte mit Medien und Anmerkungen zu verknüpfen.

In einem begleitenden Wiki werden grundlegende Schritte der Benutzung erklärt.

Die technische Entwicklung haben wir durch Tools wie Rspec, Capybara, Cypress, Rubocop begleitet und stabilisiert.

<video src="/assets/images/project_images/a-thousand-channels/orte.mp4" autoplay controls muted loop width=800></video>

### Webclient 📱

Die fertige Karte kann über ein einfaches Frontend betrachtet und veröffentlicht werden. Wir haben dazu einen Webclient konzipiert und designt, der die Karte schnell, einfach und intuitiv benutzbar macht. Dabei hilft ein innovatives UI-Design. Über verschiedene Optionen – etwa Hintergrundbild und -farbe, Auswahl einer Hintergrundkarte – können die Produzent*innen der Karte das Aussehen des Clients bestimmen. <br>
Das Ergebnis ist mobile-first, die Views lassen sich durch Swipes, Tastatur oder Mausklicks ansteuern.

![Mockup für die Navigation des Webclients](/assets/images/project_images/a-thousand-channels/a1000c--client-mockup-navigation.jpg)

### Datenschutz 🤭

Wir haben mehrere Datenschutz-Funktionen in das Backend implementiert, u.a. eine Rasterfunktion, die die Verfremdung von Bilder erlaubt, die automatische Entfernung von Metadaten aus Bildern sowie eine experimentelle Funktion zur Verschleierung von Geodaten (etwa um die Lokalisierung von sensiblen Orten zu erschweren).

![Screenshot mit der Option die Privacy-Features zu aktivieren](/assets/images/project_images/a-thousand-channels/a1000c--backend-privacy-features.jpg)

### Map to go 👜

Für die User*innen wollen wir eine strukturelle Abhängigkeit vermeiden, die bei der Benutzung einer Plattform im Internet (oder eines "Software-as-a-service") entsteht. Daher machen wir am Ende eines Mappingprozesses mit unserer Plattform das Angebot, die Karte "mitzunehmen".

Dieses Feature haben wir Map-to-go genannt: Die eigene Karte kann niedrigschwellig als statische Website exportiert und auf dem eigenen Webspace veröffentlicht werden. (Und für technisch Versierte steht eine einfache JSON-Schnittstelle zu Verfügung, um einen eigenen Client zu erstellen und mit den Daten aus der Karte zu füttern).

### Alles zusammen 📚

Unser Wunsch war, das die Plattform intuitiv zu benutzen ist, Spaß macht und respektvoll und sensibel auf die Ansprüche der Nutzer*innen – auch hinsichtlich des Datenschutzes – eingeht. Wir hoffen, dass wir diesem Anspruch in den letzten Monaten der Projektentwicklung nachkommen konnten.

Den Weg vom ersten Eintrag auf einer neuen Karte bis zum fertigen Webclient haben wir möglichst einfach gehalten.

Die Plattform bietet aber auch Möglichkeiten, eine Karte zu erstellen und zu gestalten, die die jeweils besonderen Narrationen visuell aufgreift und umsetzt, etwa durch einen Fork (also eine Kopie zur eigenen Anpassung) unseres Webclients oder die Nutzung der Daten-Schnittstelle (via JSON).

Anders gesagt: Ohne viele Vorkenntnisse kann eine Karte erstellt werden; mit mehr technischen Skills oder dem Interesse, sich diese anzueignen, ist es aber auch möglich – weiterhin schnell und einfach, wie wir hoffen – tiefer in die individuelle Gestaltung der Karte einzutauchen.

![Ein Smartphone auf einem Stativ, dahinter die Bühne auf der ein Stopptrick-Video entsteht](/assets/images/project_images/a-thousand-channels/animationmobild-1.jpg)

### Background 🏙

Kurz zu den verwendeten Technologien und Programmen, die Freie und Open Source Software sind :)

- QGIS, ein desktopbasiertes Geografisches Informationssystem zur Erzeugung der Kartenhintergründe
- Leaflet, ein Javascript-basiertes Framework zur Erstellung der Webkarten
- Inkscape für die Erstellung oder Bearbeitung von Icons und Grafiken
- Ruby on Rails + Foundation für das Backend, Tests mit RSpec + Capybara
- NuxtJS und TailwindCSS für den Client, Tests mit Cypress.io

<sub>Wie die allermeisten web-basierten Karten so basieren auch unsere auf der Mercator-Projektion. Aus unserer Sicht stellt sie eine problematische und vermeidenswerte Form der Projektion dar. Mit ihr wird der globale Norden stark vergrößert dargestellt; diese Verzerrungen unterstützen eine eurozentristische Sicht auf die Welt.<br />
Wir konnten in dem von uns verwendeten Technologie-Stack von der Erzeugung der Kartenhintergründe bis zur Webkarte (noch) nicht auf eine Projektion umstellen, die dieses Problem vermeidet, dieser Aspekt steht aber auf unserer TODO Liste.</sub>

### Wie weiter? (Ein Ausblick) 🚀

Wir holen jetzt einmal tief Luft und basteln bestimmt noch an ein paar Ecken weiter. Gleichzeitig suchen wir weitere Initiativen, die Interesse haben, unsere Plattform für ihre queeren Mappings auszuprobieren. Auf diese Kooperationen freuen wir uns und sind gespannt auf die Ergebnisse.

Wir werden versuchen, unser Projekt zu verstetigen, damit die Plattform auch längerfristig erhalten und ausgebaut werden kann.

Daher würden wir uns sehr über praktische Mithilfe, Feedback oder auch finanzielle Unterstützung freuen, die uns hilft, das Projekt nachhaltig zu entwickeln.

![AthousandchannelsHintergrund](/assets/images/project_images/a-thousand-channels/AthousandchannelsHintergrund.jpg)

### Danke! 🎊

Besonderen Dank für Begleitung, Unterstützung und Feedback: Pau* Schwer, Uxía Iglesias, Abdulghaffar Tammaa, Nina Siessegger, Ngọc Triệu von Simply Secure, Thomas Tröster, Sebastian Fuchs, Garabatos Atelier, die Arbeitsgruppe "Queer narratives, mapped", city/data/explosion, Marie Gutbub und dem Prototype Fund sowie unsere Ansprechpersonen beim DLR Projektträger.

Wir bedanken uns für die Förderung unseres Projekts beim Bundesministerium für Forschung und Bildung (BMBF).

### Links: 🔌

- Unser Website: [https://www.a-thousand-channels.xyz/](https://www.a-thousand-channels.xyz/)
- Democlient: [https://a-thousand-channels.github.io/a1000c-map-client/](https://a-thousand-channels.github.io/a1000c-map-client/)
- Making of: [https://www.are.na/a-thousand-channels](https://www.are.na/a-thousand-channels)
