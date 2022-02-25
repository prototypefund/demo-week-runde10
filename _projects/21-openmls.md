---
layout: project
title: "OpenMLS"
image: /assets/images/project_images/openmls/header.png
authors:
  - author: Raphael Robert
    link: https://twitter.com/raphaelrobert
brief: "Wir implementieren die MLS-Bibliothek für sichere Kommunikation."
summary: "OpenMLS ist eine quelloffene Implementierung des MLS-Protokolls in Rust."
---

![Tree](/assets/images/project_images/openmls/tree.png)

## Einleitung

In den 90er Jahren wurde der Begriff "Ende-zu-Ende-Verschlüsselung" zum ersten Mal durch die PGP E-Mailverschlüsselung geprägt. Das Internet stand noch ganz am Anfang, aber es wurde schnell klar, dass Verschlüsselung eine immer größere Rolle im zivilen Bereich spielen würde (bis dahin war sie vornehmlich dem militärischen Bereich vorbehalten).

Zunächst hatte die Transportverschlüsselung größere Erfolge zu verbuchen. Dabei ging es darum, dass Daten geschützt sind, wenn sie von einem Computer zu einem Server versendet werden oder andersherum. Diese Art der Verschlüsselung ist mittlerweile so etabliert, dass sie mehrheitlich für den Versand von Daten angewendet wird.

In Situationen, in denen man aber die Daten auch dann noch schützen will, wenn sie auf dem Server zwischengelagert werden (und dieser die Daten als solche inhaltlich nicht verarbeiten soll), ist Transportverschlüsselung nicht ausreichend. An der Stelle bietet die Ende-zu-Ende-Verschlüsselung angepassteren Schutz, da das benötigte Schlüsselmaterial, um die Daten zu entschlüsseln, dem Server erst gar nicht zu Verfügung gestellt wird. Messenger sind der typische Anwendungsfall, bei dem Nutzer\*innen die Erwartung haben, dass der Betreiber des Messengerdienstes den Inhalt der Nachrichten nicht mitlesen kann. Es gibt aber auch andere Szenarien, bei denen man Daten, die zwischen zwei Geräten transitieren, durchgängig verschlüsseln möchte. Beispiele dafür sind das Internet-of-Things, Synchronisierung von Geräten über die Cloud bei Passwortmanagern oder Datei-Sharing-Diensten.

Weil Ende-zu-Ende-Verschlüsselung zum einen technologisch komplexer ist als Transportverschlüsselung, zum anderen aber auch nicht in allen Fällen benötigt wird, ist das Angebot an Protokollen und Implementierungen vergleichsweise überschaubar. Das ist der Punkt, an dem wir ansetzen wollen.

## Was ist eigentlich MLS?

Die Internet Engineering Task Force ist eine Community, die sich mit Standards zur technischen Weiterentwicklung des Internets befasst und aus verschiedenen Arbeitsgruppen besteht.

Eine solche Arbeitsgruppe hat sich 2018 als Messaging Layer Security (MLS) zusammengefunden, um einen industrieweiten Standard für ein Ende-zu-Ende-verschlüsseltes Protokoll zu erarbeiten. Wir haben diese Arbeitsgruppe mitgegründet und tragen regelmäßig zu der Protokollspezifikation bei.

Aber der Reihe nach: Es bestand der Wunsch bei einigen der großen Technologieunternehmen wie Mozilla, Cisco, Facebook, Google, Twitter und auch bei nicht ganz so großen wie Wire und Wickr, einen gemeinsamen Standard zu haben, der gut dokumentiert, frei verfügbar ist und für den es auch Implementierungen gibt. Gleichzeitig sollte das Protokoll nicht nur von Software-Ingenieur\*innen entworfen, sondern in enger Kooperation mit der akademischen Gemeinschaft erarbeitet werden, so wie es kurz vorher auch erfolgreich für die Standardisierung von TLS 1.3 geschehen war. Daher kamen interessierte Partner\*innen von der University of Oxford INRIA Paris, Aalto University, CISPA Helmholtz-Zentrum, Naval Postgraduate School und andere von Anfang an mit dazu.

Ein weiterer Wunsch bestand darin, ein möglichst effizientes Protokoll für Verschlüsselung in Gruppen zu haben. Existierende Protokolle sind grundsätzlich für die Verschlüsselung zwischen genau zwei Endpunkten vorgesehen. Für die Verschlüsselung in Gruppen werden entweder viele dieser 1:1-Verbindungen kombiniert, worunter die Effizienz dann leidet. Oder es werden Abstriche bei den Sicherheitsgarantien gemacht, insbesondere in deren Granularität. Der Ansatz von MLS ist es, auch in größeren Gruppen noch effizient zu sein, ohne aber die Sicherheitsgarantien signifikant zu schwächen. So werden Nachrichten nicht mehr individuell für alle Teilnehmer\*innen einer Gruppe verschlüsselt, sondern nur noch einmal. Um die Sicherheitsgarantien einzuhalten, muss regelmäßig das Schlüsselmaterial aufgefrischt werden, was bei MLS aber typischerweise mit nur logarithmischem Aufwand geschieht und nicht linear wie bei Protokollen, die aus 1:1-Verbindungen bestehen.

Aus dieser Arbeitsgruppe entstand dann im Verlauf der vergangenen Jahre das [MLS Protokoll Dokument](https://datatracker.ietf.org/doc/draft-ietf-mls-protocol/). Der Standardisierungsprozess befindet sich zum Zeitpunkt des Schreibens in der letzten Phase und wird nach dem sog. Last Call als Standard vorgeschlagen. Neben den technischen Dokumenten, gibt es auch eine [Einführung in MLS](https://www.youtube.com/watch?v=zrjmpyc8YrE) als Vortrag, der bei der Black Hat USA 2019 gehalten wurde.

## Was ist OpenMLS?

Neben dem Erarbeiten einer Spezifikation, gehört zu dem IETF Prozess dazu, dass auch frühzeitig an Implementierungen gearbeitet wird - nach dem Motto "rough consensus and working code".

OpenMLS entstand zunächst als Proof-of-Concept-Implementierung, um sicher zu stellen, dass die Konzepte aus der Spezifikation auch implementierbar waren. Erkenntnisse aus der Implementierung sind dann auch in die Spezifikation zurückgeflossen und haben diese praxistauglicher gemacht.

Diese Proof-of-Concept-Implementierung wurde dann erweitert, hin zu einer Implementierung, die als Baustein in konkreten Produkten und Projekten eingesetzt werden kann. Die Codebasis ist [quelloffen unter der MIT Lizenz veröffentlicht](https:////github.com/openmls/openmls).

## Programmiersprache

Für den gesamten Code kommt die Programmiersprache Rust zum Einsatz. Diese noch recht neue Sprache zeichnet sich insbesondere durch zwei Eigenschaften aus: Sie ist "memory safe" und vermeidet dadurch fehlerhafte Speicherzugriffe und sie kann recht einfach für viele Plattformen kompiliert werden. Ersteres ist insbesondere wichtig im Bereich der kritischen Sicherheitskomponenten eines Systems. Ein sehr großer Teil der Sicherheitslücken, die in bestehender Software gefunden werden, ist auf fehlerhafte Speicherzugriffe zurückzuführen (buffer overflows, use-after-free etc.). Diese Klasse an Sicherheitslücken kann durch den Einsatz von Rust im Prinzip vollständig eliminiert werden. Ferner ist die einfache Kompilierbarkeit auf vielen Plattformen wichtig, damit eine Softwarebibliothek möglichst unproblematisch auf Android, iOS, Windows, Linux, macOS und im Browser verwendet werden kann.

## Designprinzipien

Das MLS Protokoll hat den Anspruch, möglichst viele Szenarien abzudecken und mit den Anforderungen möglichst vieler Produkte kompatibel zu sein. Dadurch ist eine gewisse Komplexität entstanden, die dazu führen könnte, dass der Einsatz von MLS zu einer Hürde werden könnte.

Als Protokollautoren wollten wir unsere Kenntnisse anwenden, um die Programmierschnittstelle (API) der Bibliothek so zu gestalten, dass Benutzer\*innen der Bibliothek diese Komplexität nicht so sehr zu spüren bekommen. Die Herausforderung bestand also darin, sich das Design der API dahingehend zu überlegen, dass Benutzer\*innen klar definierte und einfach verständliche Operationen ausführen können und bei diesen sinnvolle Rückgabewerte (oder ggf. Fehlermeldungen) bekommen.

Darüber hinaus wollten wir neben der Dokumentation der einzelnen Funktionen und Datentypen den Benutzer\*innen auch einen [Leitfaden in Form eines Handbuchs](https://openmls.tech/book) zu Verfügung stellen.

## Derzeitiger Stand und Ausblick

Zum Zeitpunkt des Schreibens ist OpenMLS in Version 0.4 veröffentlicht. Das API-Design hat eine gewisse konzeptionelle Stabilität erreicht und wird in Folgeversionen wahrscheinlich iterativ angepasst, nicht aber immer wieder neu erfunden. Die gängigen Funktionen des MLS Protokolls sind nutzbar, sodass man Gruppen erstellen, Teilnehmer\*innen hinzufügen und entfernen und natürlich Nachrichten ver- und entschlüsseln kann.

Im derzeitigen Stand kann OpenMLS bereits verwendet werden für die experimentelle Integration in bestehende und neue Projekte. [Erste Versuche laufen bereits bei dem sicheren Messenger Wire](https://thestack.technology/messaging-layer-security-is-coming-of-age/), sowie bei der [dezentralen und sicheren Datenbank p2panda](https://p2panda.org/). Weitere Projekte sind geplant, sobald die Spezifikation des Protokolls sich stabilisiert hat.

Ziel des Projekts ist es, dass bei entsprechendem Bedarf die Bibliothek weiterentwickelt, an Änderungen der Spezifikation angepasst und die Sicherheit und Robustheit durch mehr Testing, Refactoring und Pflege des Codes erhöht wird.

### Links

Webseite: [openmls.tech](https://openmls.tech)

Quellcode: [github.com/openmls/openmls](https://github.com/openmls/openmls)

---

Wir bedanken uns beim Bundesministerium für Bildung und Forschung, dem Deutschen Zentrum für Luft- und Raumfahrt und dem Prototype Fund für die Unterstützung!
