---
layout: project
title: "Face the Facts"
image: /assets/images/project_images/face-the-facts/header.png
authors:
  - author: Victor Bellu
    link: 
  - author: Oliver Köditz
    link: 
  - author: Richard Krümmel
    link: 
brief: "Wir machen alle wichtigen Infos über Politiker:innen direkt am Wahlplakat abrufbar."
summary: "Mit der App Face the Facts müssen User einfach nur ihre Handykamera auf ein Wahlplakat richten und bekomme alle wichtigen Infos von über Kandiderende direkt angezeigt."
---

# Face the Facts - Wähl' nicht irgendwen!

![](/assets/images/project_images/face-the-facts/Bild 2.png)

## Democracy deserves the best

Wenn wir uns die Welt anschauen, sehen wir Klimawandel, Digitalisierung, Extremismus, Armut und Krieg. Deswegen brauchen wir die besten Politiker:innen, die wir bekommen können.
Es reicht nicht mehr aus, nur nach Parteien und ihren Versprechen zu wählen - wir müssen uns auch viel genauer anschauen, wer denn am Ende wirklich in Parlamenten sitzt und uns regiert und repräsentiert. Welche Positionen haben diese Leute? Welche Kompetenzen bringen sie mit und vielleicht am wichtigsten: Wer oder was beeinflusst sie?

Um genau das für Wähler:innen so einfach wie möglich zu machen, haben wir Face the Facts entwickelt.
Face the Facts ist eine App, die alle wichtigen Informationen über  Kandidaten:innen direkt am Wahlplakat abrufbar macht.
User müssen einfach nur ihre Handykamera auf ein Plakat richten und erhalten eine Übersicht von politischen Positionen, Schwerpunkten, Lebenslauf, Abstimmungsverhalten und Nebentätigkeiten der Politiker:in.
So können sich Wähler:innen eine umfassende Meinung über die Person bilden und schlussendlich die besten Kandidat:innen wählen.


## MVP zur Bundestagswahl

Eine erste Version der App mit diesen Features haben wir bereits pünktlich im September zur Bundestagswahl in die Appstores gebracht.
Nach einem viralen reddit-Post sind ein paar Zeitungen, Newsseiten und sogar der Youtuber RobBubble auf uns aufmerksam geworden. Am Ende konnten wir uns über mehr als 10.000 Downloads freuen.

![](/assets/images/project_images/face-the-facts/Bild 3.png)

Technisch betrachtet war das Ganze im wahrsten Sinne des Wortes ein MVP, zusammengehalten von metaphorischen Ducktape und besten Hoffnungen:
Das Scan-Feature basiert nicht etwa auf einer Gesichts-, sondern  auf einer einfachen Texterkennung von Google Firebase und läuft lokal auf dem Handy.
Schließlich sind auf jedem Wahlplakat auch immer Name und Partei einer Kandidat:in erkennbar und besonders bei unbekannteren Politiker:innen ist es schwierig, genug Daten für eine Gesichtserkennung zu sammeln.

Die App selber ist in React Native programmiert, damit wir nur eine gemeinsame Code-Base für Android und iOS pflegen müssen.
Die meisten der benötigten Daten konnten wir glücklicherweise über die API von Abgeordnetenwatch abrufen.
Weil diese API aber noch in der Alphaversion war und ständig verändert wurde, mussten wir de facto die komplette Datenbank downloaden und als JSON-Datei direkt in der App hinterlegen.
Ein Vorteil dessen war, dass wir erstens keine Daten von unseren Usern erheben müssen, was uns sehr wichtig ist und die ganze App (mit Ausnahme der Profilbilder der Politiker:innen) komplett offline funktioniert hat.

Das Schwierigste an der Entwicklung war aber nicht unbedingt die technische Umsetzung der Idee sondern die Verfügbarkeit von Daten über Politiker:innen allgemein - und sie so aufzubereiten, dass jede:r sie leicht verstehen kann.

Deshalb haben wir uns beim Design viel Zeit genommen, die komplexen Prozesse visuell so darzustellen, dass es Spaß macht sich damit zu beschäftigen.
Wichtig war uns dabei, dass wir keine Daten kuratieren, sondern nur aus anderen Quellen aggregieren.

Alles, was in der App zu sehen ist, sind Fakten.

Für die Arbeit im Prototype Fund konnten wir deshalb auf einem großen Vorwissen zum Thema und Problem aufbauen und haben gleichzeitig das Userfeedback durch den Launch einarbeiten können.


## Face the Facts 2.0: Ein Dashboard für die Demokratie

Nach der Wahl ist bekanntlich vor der Wahl, aber die wirklich interessanten Dinge passieren dann, wenn es an die echte parlamentarische Arbeit geht.

Und genau dann ist es besonders wichtig hinzuschauen, wofür die einzelnen Politiker:Innen stimmen, welche Nebentätigkeiten plötzlich hinzukommen und ob sie ihren Positionen aus dem Wahlkampf treu bleiben.

Deshalb haben wir die Zeit im Prototype Fund dafür genutzt, die Wahl-App Face the Facts zu einem tagesaktuellen Information Hub für Politik auszubauen: Einem Dashboard für die Demokratie.

Dieser Leitgedanke hat sich besonders in zwei neuen Featureideen widergespiegelt:
Zum einen im Follow-Feature, das es Usern ermöglicht Politiker:innen in der App zu folgen und regelmäßige Updates über deren Arbeit im Parlament zu erhalten; zum anderen im Dashboard, das die aktuellen Vorgänge im Bundestag für die User übersichtlich aufbereitet.

![](/assets/images/project_images/face-the-facts/Bild 4.png)

Während das Follow-Feature Usern in einem Live-Ticker die letzten Aktivitäten von ausgewählten Politiker:innen wie z. B. gehaltene Reden, neueste Abstimmungen oder gemeldete Nebentätigkeiten auflistet, gibt die Bundestagsübersicht einen holistischen Überblick auf das aktuelle politische Tagesgeschehen im Bundestag, dargestellt als Summe der Reden, Abstimmungen oder Nebentätigkeiten von individuellen Politiker:innen.
So bekommen User ein besseres Gefühl für den Politikbetrieb und können einzelne Politiker:innen individuell nach ihren Entscheidungen beurteilen.

Gleichzeitig hat uns dieser Ansatz erlaubt, mit „Artikeln" und „Reden" zwei neue Features für die Profile von Politiker:innen zu integrieren, die sich viele User gewünscht hatten.
Besonders Reden waren ein Format, nach dem wir oft in Usertests gefragt wurden, weil viele es hilfreich fanden, die Person einmal selbst reden zu hören und nicht nur über sie zu lesen.
Anders als beim Bundestagsdashbaord oder Follow-Feature war im Profil der Fokus, die einzelnen Elemente insgesamt als Übersicht für die Politiker:in aufzubereiten, sodass man sich im Idealfall schnell ein Bild über jemanden machen kann.

![](/assets/images/project_images/face-the-facts/Bild 5.png)

Das hat schlussendlich auch dazu geführt, dass wir einige ältere Designs noch mal ändern mussten, damit sie visuell mehr dem Anspruch der App als Information Hub entsprechen.\
Neben kleinen Anpassungen bei der Navigation und beim Profil sind diese Änderungen besonders sichtbar bei den Abstimmungsdetails, die Ergebnisse und Abstimmungsverhalten  jetzt deutlich übersichtlicher darstellen.

![](/assets/images/project_images/face-the-facts/Bild 6.png)

## The Beginning of Backend

All diese neuen Features wären aber unmöglich mit einem JSON-File als Backend umzusetzen gewesen.

Überhaupt war diese technische Umsetzung für die Bundestagswahl nur ausreichend, weil wir ausschließlich Politiker:innen im File hatten, die zu einer der Landtagswahlen oder den Bundestagswahlen angetreten sind.

Wegen der Sitzungspausen gab es kaum neue Daten, deshalb brauchten wir auch keine skalierbare Möglichkeit, die Daten zu updaten.\
Mit Blick auf die neuen Featureideen und aber auch allgemeine Skalierbarkeit war das Set-Up jedoch unvereinbar.\

Deshalb haben wir direkt am Anfang des Prototype Fund mit der Arbeit an einem echten Backend begonnen.
Als Vorlage haben wir dafür die Struktur von Abgeordnetenwatch benutzt und sie auf unsere Features angepasst, wie z. B. Biografien von Politiker:innen.\
Programmiert wurde das Ganze schließlich in SQL und damit die meisten Daten von der App auf einen externen Server verschoben.

![](/assets/images/project_images/face-the-facts/Bild 7.png)

Ein Großteil der Daten speist sich dabei durch externe APIs, die in regelmäßigen Abständen gecalled werden.
So werden z.B. Informationen wie Abstimmungsverhalten oder Nebentätigkeiten durch die Abgeordnetenwatch API geupdatet, Reden bekommen wir von Open Parlament TV und Artikel werden vom Prototype Fund Projekt Politrack aggregiert.

Schlussendlich sind die einzigen Daten, die wir noch in der App lokal speichern, solche die wir erst gar nicht haben wollen: Userdaten.

Nach diesem Grundsatz ist auch das Follow-Feature implementiert:
Wenn der User eine:r Politiker:in im Profil folgt, ruft die App im „Folge ich"-Screen mit der ID des:der Politiker:in die Daten im Backend auf und zeigt sie dann chronologisch aufbereitet als Liveticker an.

So muss der User sich weder einloggen noch registrieren und bekommt sofort auch rückwirkend im Liveticker vergangene Reden und Abstimmungen angezeigt.
Das Wichtigste aber: All diese Daten bleiben auf dem Handy des Users. Wir erheben nichts davon.

## Feature Creep und das Leben als Aggregator

Als wir mit der neuen Version der App angefangen haben, hatten wir tausend Ideen für neue Features. Leider muss die aber auch jemand implementieren.

Einige haben wir direkt wieder verworfen, weil wir die Infos nicht aggregieren können, sondern kuratieren müssen, z. B. bei den einzelnen politischen Positionen auch relevante Abstimmungen hinzuzufügen, damit User direkt sehen ob der:die Politiker:in die Wahlversprechen hält oder nicht.\
Andere Features waren einfach nicht gut umsetzbar, weil die Daten fehlen oder nur sehr schwer zu erheben sind.\
Ein gutes Beispiel hierfür ist das Bundestags-Dashboard, das wir erst nach dem Prototype Fund implementieren werden.\
Hauptgrund ist, dass wir ursprünglich angenommen haben, dass die Anzahl der namentlichen Abstimmungen viel höher ist, als es tatsächlich der Fall ist.\
Um das Feature wirklich hilfreich zu machen, müssten wir auch nicht namentliche Abstimmungen integrieren, für die es keine guten APIs gibt und für die wir die Daten deshalb selber scrappen müssen.\

Als Aggregator sind wir leider aber auch immer abhängig von solchen „Zulieferern" und desto größer und diverser wird auch unser „Portfolio" in der Hinsicht mit jedem Feature.\
Ohne Services wie Abgeordnetenwatch, Politrack oder Open Parlament wären Face the Facts de facto nicht möglich.

![](/assets/images/project_images/face-the-facts/Bild 8.png)

Im Idealfall sollten wir aber gar nicht über Drittanbieter gehen müssen, um öffentlichen Daten skalierbar abrufen zu können.\
Stattdessen wäre es viel besser, wenn die Parlamente selbst APIs anbieten würden, die alle Informationen zur Verfügung stellen oder wenn man sich zumindest auf eine gemeinsame Formatierung der Daten von Bundestag bis Landtag einigt.

## Face the Future

Wir haben Face the Facts von Anfang an als Open-Source-Projekt aufgesetzt, damit die App  nicht nur eine Lösung für Deutschland ist, sondern überall auf der Welt eingesetzt werden kann.\
Durch die Berichterstattung während der Bundestagswahl haben wir auch erste Anfragen aus den Niederlanden, Brasilien und Frankreich.\
Haupthindernis ist dabei überall die Datenerhebung, weil es entweder überhaupt keine APIs dazu gibt oder weil die Nutzung sehr restriktiv ist, z. B. in den USA, wo die New York Times nur einzelne Calls zulässt, aber keine komplette Kopie.

In Deutschland wiederum sind wir gerade in Gesprächen mit Partner:innen, die auf unserer Arbeit aufbauen und Teile von Face the Facts für ihre Organisation adaptierten wollen, z. B. Abgeordnetenwatch, Wikimedia oder vielleicht sogar der Bundestag selbst.\
Am Ende des Tages ist es schließlich der Sinn eines Open-Source-Projektes, kopiert und weiterentwickelt zu werden.

Abschließend möchten wir uns herzlichst beim DLR und dem BMBF für die Förderung bedanken.
Außerdem wäre viel von dem Projekt nicht möglich gewesen ohne die Unterstützung der CODE University, insbesondere Peter Ruppel, aber auch von Abgeordnetenwatch und Wikimedia, die uns jederzeit mit Rat zur Seite standen und natürlich Politrack und Open Parliament TV, die Features erst möglich gemacht haben.

[Zum Download APK für Android](https://facethefacts-database.s3.eu-central-1.amazonaws.com/FaceTheFactsBeta.apk)