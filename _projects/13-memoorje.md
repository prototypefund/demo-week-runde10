---
layout: project
title: "memoorje"
image: /assets/images/project_images/memoorje/header.png
authors:
  - author: Konrad
    link:
  - author: Robert
    link:
  - author: Steffen
    link:
brief: "Wir ermöglichen sicheren, selbstverwalteten digitalen Nachlass für alle."
summary: ""
---

Die digitale Welt ist aus unserem Alltag nicht mehr wegzudenken: Von der Kommunikation bis hin zum Kaufverhalten beeinflussen Digitalisierung und Vernetzung der Gesellschaft zunehmend unser Leben. Doch was passiert mit den zahlreichen Zugängen und sensiblen Daten im Krankheits- oder Todesfall und vor allem, wer kümmert sich darum? Viele Abonnements und Konten laufen über Monate hinweg weiter, denn nicht alles endet mit dem Tod.

Die Regelung des digitalen Nachlasses wird somit immer notwendiger, insbesondere wenn verhindert werden soll, dass sensible Daten in die falschen Hände geraten. Nachlässe und Testamente sind allerdings etwas, das man sich leisten können muss. Der Gang zu Notar\*innen und Anwält\*innen ist nicht nur kostspielig, sondern oftmals auch mit administrativem Aufwand und rechtlichen Hürden verbunden. Memoorje wurde auf den Weg gebracht, damit jede\*r von uns das Recht auf einen selbstverwalteten Nachlass wahrnehmen kann.

## Live-Demo

Du kannst memoorje auf [demo.memoorje.org](https://demo.memoorje.org/) testen. Demnächst gehen wir auch in den Produktivbetrieb.

## Funktionsweise

Mit der Software memoorje wird eine Website bereitstellt, auf der Du Deinen digitalen Nachlass selbstbestimmt und unkompliziert über Computer oder Smartphone in drei Schritten organisieren kannst.

### Schritt 1 

Die persönlichen Daten werden in einer oder mehreren digitalen Kapseln angelegt – ganz gleich, ob es sich hierbei um Fotos, Passwörter oder einen Abschiedsbrief handelt. Jeder Mensch weiß am besten, was für die Nachwelt ein Trost oder eine Hilfe sein kann. Dabei muss der Nachlass nicht auf eine Kapsel beschränkt werden.

### Schritt 2 

Es wird festgelegt, wer den Inhalt der digitalen Kapsel erhalten soll. Egal ob Familie, Freund\*innen oder Geschäftspartner\*innen, die Kapseln können je nach Inhalt unterschiedliche Empfänger\*innen haben.

### Schritt 3 

Zuletzt muss noch entschieden werden, wer die Kapsel nach dem Ableben freigeben darf. Um auch hier den Inhalt der Kapsel möglichst gut zu schützen, wird ein Verfahren eingesetzt, bei dem der Zugangsschlüssel in mehrere Teilschlüssel aufgeteilt wird. Jeder eingetragenen Person wird nur ein Teilschlüssel übergeben. Wie viele Personen einen Teilschlüssel erhalten sollen und wie viele Personen letztendlich notwendig sind, um die Kapsel zu öffnen, kann beliebig festgelegt werden. Somit kann das Schloss einer Kapsel – wenn man möchte – auch mit nur einem halben Schlüssel geöffnet werden.

## Aktueller Stand des Projekts

Dank der Förderung durch den Prototype Fund konnte die anfängliche Entwicklung der Software durchgeführt und fast alle notwendigen Features implementiert werden. Memoorje wird mit einem Django-Backend und einem Vue-basiertem Frontend realisiert und ist nunmehr Freie- und Open-Source-Software, so dass Entwickler\*innen den Quellcode ändern und an ihre Bedürfnisse anpassen können. Selbstbestimmtes Hosting in Eigenregie ist ebenfalls möglich. Zudem werden wir memoorje als Service selbst betreiben.

## FAQs

### Warum memoorje? 

Es gibt aktuell einige kommerzielle Dienste, die die grundsätzliche Verwaltung eines digitalen Nachlasses anbieten. Diese Dienste sind jedoch kostenpflichtig, keine Freie Software und zudem ist unklar, ob die Daten verschlüsselt sind oder wer Zugriff auf die Daten hat.

### Kostet memoorje etwas? 

Memoorje wird kostenlos nutzbar sein, da das digitale Erbe ein öffentlicher Dienst sein sollte. Um die zukünftige Softwareentwicklung zu finanzieren und die Server am Laufen zu halten, sin wir auf Spenden angewiesen.

### Wie sicher ist die Software? 

Alle Daten werden bereits in Deinem Browser verschlüsselt und so auf dem memoorje-Server gespeichert. Selbst wenn wir es wollten, könnten wir den Inhalt nicht sehen.

### Können mehrere digitale Kapseln angelegt werden? 

Ja, je nach Projekt, Verwandtschaftsgrad oder Beziehung können unterschiedliche Kapseln mit Inhalten gefüllt werden. So können an Geschäftspartner\*innen beispielsweise andere Inhalte weitergegeben werden als an Familienmitglieder.

### Wie wird eine Kapsel nach dem Tod geöffnet? 

Für jede Kapsel werden Teilschlüssel an verschiedene Personen übertragen. Jede Person erhält einen Teilschlüssel. Nach dem Tod muss eine bestimmte Anzahl von Teilschlüsseln zusammengesetzt werden, damit der Inhalt der Kapsel an die Empfänger\*innen weitergegeben werden kann.

### Kann eine Kapsel bereits vor dem Tod durch die Inhaber\*innen der einzelnen Teilschlüssel geöffnet werden? 

Nein. Die Teilschlüssel sind für sich genommen unbrauchbar, denn erst memoorje fügt sie zusammen. Sobald der erste Teilschlüssel an memoorje übertragen wurde, beginnt außerdem eine Widerspruchsfrist. Dies verhindert eine versehentliche, aber auch eine vorsätzliche Freigabe der Kapselinhalte. Dennoch sollten nur vertrauenswürdige Personen als Teilschlüssel-Inhaber\*innen ausgewählt werden.

### Sind Inhaber\*innen der Teilschlüssel auch gleichzeitig Empfänger\*innen der Inhalte? 

Die Inhaber\*innen der Teilschlüssel sind nicht zwingend auch die Empfänger\*innen der Inhalte. Es besteht auch hier eine freie Wahl der Personen. So können beispielsweise mehrere Teilschlüssel-Inhaber\*innen ausgewählt werden, aber eine ganz andere Person empfängt letztendlich den Inhalt der Kapsel.

## Danksagung

Vielen Dank an das BMBF, das unsere Förderung ermöglicht hat und die Teams des DLR und des PrototypeFund für die freundliche, engagierte und allgemein großartige Unterstützung durch Feedback, Erinnerungen, 1:1 Gespräche, Ermutigungen und allerlei Tipps. Ohne euch wären wir nicht da, wo wir sind <3.
