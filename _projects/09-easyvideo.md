---
layout: project
title: "Easyvideo"
image: /assets/images/project_images/easyvideo/header.jpg
authors:
  - author: Hong Phuc Dang
    link:
  - author: Nangialei Safi
    link:
  - author: Mario Behling
    link:
brief: "Wir ermöglichen Streaming, Aufnahme und Export für Open Source-Videolösungen."
summary: "Mit Easyvideo entwickeln wir Plugins für Server, und Skripte, um Aufnahme- und Export-Funktionen in BBB und Jitsi nachzurüsten und den Endnutzer\\*innen zur Verfügung zu stellen."
---

## Unsere Motivation

Unser Team organisiert seit Jahren Meetups, Konferenzen und veranstaltet Seminare an Universitäten. Nicht erst seit der Corona-Pandemie benutzen wir dafür auch Online-Videotools, wie BigBlueButton oder Jitsi. Leider fehlen populären Open-Source-Videolösungen Streamingoptionen und Exportfunktionen von Aufnahmen ganz wie bei BigBlueButton oder Aufnahmen sind nur mit proprietären Anbietern möglich, z. B. bei Jitsi mit Youtube und Dropbox. Für die freie Dokumentation von Events und Lehrveranstaltungen ist das ein Problem. Während der Corona-Pandemie wurden Tools wie OBS populär, die Aufnahmen direkt auf dem Computer ermöglichen. Zudem gab es Hacks, die von verschiedenen Entwickler\*innen ins Netz gestellt wurden und einzelne Funktionen anboten, oft jedoch nicht für eine größere Nutzer\*innengruppe weiterentwickelt wurden. Unser Ziel für das Projekt ist es nun, auf Grundlage der Arbeit in der Open-Source-Community Videoexportfunktionen für die zwei bekanntesten Lösungen BigBlueButton und Jitsi zu entwickeln.

## Warum Open Source

Unser Team hat einen internationalen Background und aus eigenen Erfahrungen heraus wissen wir, wie große Clouddienste z. B. in einigen asiatischen Ländern Bürger\*innen einschränken und kontrollieren können. Aufgrund dieser Erfahrung vertrauen wir unabhängigen freien Open-Source-Lösungen einfach mehr. Unsere Meinung ist, dass gerade Lehrende und Studierende die Vorzüge freier Open-Source-Software in Anspruch nehmen können sollen. Deswegen ist es unser Ziel, insbesondere Bildungseinrichtungen in die Lage zu versetzen Open-Source-Lösungen wie offene Videolösungen zu nutzen oder von lokalen Open-Source-Firmen Unterstützung zu erhalten. Auch um die digitale technologische Unabhängigkeit (Souveränität) von proprietären Videodiensten und lokalen Cloudanbietern zu erhalten, benötigen wir Open-Source-Videodienste, die mit proprietären Anbietern konkurrieren können.

## Das große Ziel (Vision und Mission)

Das ultimative Ziel unseres Projekts ist es, dass alle Menschen freie Open-Source-Videosysteme nutzen können, die einfach dokumentiert werden können mit Hilfe von Export- und Streamingfunktionen. Dafür wollen wir Plugins oder Erweiterungen zur Verfügung zu stellen - um Veranstaltungen aufnehmen und streamen zu können. Insbesondere wollen wir den Videoexport auf den eigenen Rechner, Streaming zu Peertube und gängigen Medienkanälen, und die Speicherung auf Nextcloud, FTP und Git implementieren.

## Die ersten Schritte

Die momentan weithin meistgenutzten Open-Source-Online-Videolösungen sind BigBlueButton und Jitsi. Unser Ziel war, dass eine möglichst große Nutzer\*innengruppe unsere Entwicklungen nutzen kann und daher konzentrierten wir uns zuerst auf BBB und Jitsi. Mittels Benutzer\*innenoberfläche sollten Endnutzer\*innen den Video-Export nutzen können.

## Herausforderungen

Die erste Herausforderung war, sich einen Überblick über bestehende Ansätze von Codeprojekten für Video-Export-Funktionen zu verschaffen. Es gibt eine Vielzahl von Ansätzen und Technologien, die an unterschiedlichen Orten im Netz veröffentlicht wurden. Unser Ansatz war, dass wir wenn möglich nichts neu entwickeln wollten, das es woanders vielleicht schon (besser) gibt.

Die zweite Herausforderung war, dass wir uns mit einer Vielzahl von Technologien, Frameworks und Bibliothekenabhängigkeiten a) bei BBB und Jitsi auseinandersetzen müssen und b) bei Lösungen, die wir anbinden wollen, z. B. Nextcloud. Jede Lösung hat ihren eigenen Technologiestack und Architektur und für ein gutes Verständnis benötigt man Zeit. Die technischen Fragen der Umsetzung beinhalten auch die Frage, wie eine Lösung für Exportfunktionalitäten implementiert werden soll und welche technischer Ansatz der langfristig wahrscheinlich vielversprechendste ist.

Bei der dritten Herausforderung geht es um die Frage der Community und des Entwickler\*innenteams. Würde ein Pull Request mit einer neuen Videoexportfunktion bei den Hauptentwickler\*innen einer Video-Online-Lösung akzeptiert werden? Wie stehen die Chancen? Welche technischen “Best Practices” existieren? Ist eine Funktion eventuell “Out of Scope”? Was ist innerhalb der Zeit im Prototype Fund möglich und realistisch?

## Implementierung Export aus BBB

Bei der Implementierung des Exports von Videos und Präsentationen auf BBB heraus gab es zunächst die Frage, ob wir die Funktionalität direkt in BigBlueButton integrieren oder als externes Tool zur Verfügung stellen sollen. Um eine Codeänderung in ein etabliertes Projekt zu integrieren, gibt es oft einen längeren Prozess, der garantiert, dass die Änderungen den Ansprüchen der Hauptentwickler\*innen genügen und im Scope sind, also “reinpassen”. Das beinhaltet auch oft eine längere Diskussion. Da wir für das Projekt eine beschränkte Zeit hatten und sicherstellen wollten, dass Nutzer\*innen möglichst bald ein Video-Export-Tool für BBB zur Verfügung steht, haben wir uns für eine externe Lösung entschieden, die nicht direkt in BBB integriert ist. Ein zusätzlicher Grund war, dass wir uns nicht über Interessenkonflikte der Firma hinter BBB im Klaren waren, denn die Firma stellt selbst kommerzielle BBB-Dienste zur Verfügung, die zusätzliche Funktionalitäten enthalten (u. a. auch Videofunktionalitäten), die in der Open-Source-Software nicht enthalten sind.

Das Ziel unseres BBB-Tools ist es, den Export von Videos und Präsentationen aus BigBlueButton-Instanzen zu ermöglichen. Der BBB-Videoexporter muss nicht auf dem BBB-Server selbst installiert werden, sondern kann auf externen Servern als separates Tool betrieben werden. Die Applikation kann man auf dem eigenen Computer mit einem lokalen Server installieren oder online zum Laufen bringen. Es gibt zwei Möglichkeiten Videos und Präsentationen von BBB zu exportieren a) über die Befehlszeilenschnittstelle (Commandline) oder b) über ein Webinterface in einem Browser. Sobald man die Installation des Tools abgeschlossen hat, kann man die Video-URLs von aufgenommenen BBB-Sessions in das Webformular vom BBB-Exporter kopieren und den Export starten. Als erstes unterstützen wir den Export aller BBB-Daten inklusive aufgenommener Videos, Präsentationsdaten und Chat. Momentan arbeiten wir zudem noch am automatisiertem Zusammenfügen dieser Daten in ein Videofile. Bisher war es nicht möglich aufgenommene Veranstaltungen von BigBlueButton zu exportieren und zum Beispiel auf eine eigene Webinstanz hochzuladen. Das ist mit unserem Tool nun möglich. Eine Website zum Testen bieten wir auf [https://easyvideo.cc](https://easyvideo.cc) an.

## Implementierung Export aus Jitsi nach Nextcloud

Bei der Implementierung eines Exports ohne die Nutzung proprietärer Dienste haben wir uns für die Unterstützung von Nextcloud entschieden. Ein Vorteil war, dass Jitsi bereits über die Exportfunktionalität verfügt. Leider ist die Funktionalität nicht abstrahiert implementiert. Dies bedeutet, dass man die Funktion für jeden einzelnen Dienst separat implementieren muss. Ein Vorteil war, dass es bereits eine Beispielimplementierung für existierende proprietäre Dienste gab.

Eine Herausforderung, die wir bei der Implementierung feststellten, waren Bedenken in Bezug auf Sicherheitsanforderungen, die wir auch bis zum Ende des Projekts nicht komplett ausräumen konnten. Zum Testen haben wir eine Installation auf [https://meet.easyvideo.cc](https://meet.easyvideo.cc) aufgesetzt.

Folgend eine Beschreibung des allgemeinen Upload-Prozesses und notwendiger Änderungenen für technisch Interessierte:

1. Technische Implementierung beim Vorgang des Hochladens

- Frontend erhält Aktualisierungstoken, Zugriffstoken, OAuth-Client-ID
- jibri schreibt Aufnahme in $recordingdir
- Das Frontend schreibt metadata.json in $recordingdir, das das Aktualisierungstoken, das Zugriffstoken und die OAuth-Client-ID enthält
- Am Ende der Aufzeichnung wird jitsi_uploader.sh aufgerufen, es liest Zugriffstoken/Aktualisierungstoken/Client-ID aus der Metadatendatei
- Für Dropbox exportiert jitsi_uploader.sh Zugriffstoken, Aktualisierungstoken, OAuth-Client-ID in die Umgebung und startet den Dropbox-Uploader

2. Schritte zum Verbinden von NextCloud mit Jitsi

- auf Nextcloud-Instanz Jitsi-Oauth-Client hinzufügen (siehe zum Beispiel [https://docs.moodle.org/311/en/OAuth_2_Nextcloud_service](https://docs.moodle.org/311/en/OAuth_2_Nextcloud_service))
- (bei der Registrierung des Nextcloud-Kontos in Jitsi)
  - INPUT-URL der nextcloud-Instanz
  - Der Server verbindet sich mit der Nextcloud-Instanz
  - Umleitung für Anmeldung/Authentifizierung
  - jitsi erhält Token

3. Weitere Notwendigkeiten bei der Implementierung

- UI im Frontend zu:
  - fragen Sie nach der Nextcloud-URL
  - auf Konnektivität prüfen
  - Weiterleitung zur Authentifizierung
  - Token erhalten (alles ähnlich Dropbox, benötigt aber eine zusätzliche Frage für die URL des Servers)
  - Tokens usw. in die Metadatendatei schreiben
- Jitsi-upload-integrations:nextcloud_uploader.sh: muss geschrieben werden (möglicherweise in der Nähe des Dropbox-Uploaders)
- Jitsi-upload-integrations:jitsi_uploader akzeptiert Nextcloud als Anbieter

Nextcloud und Sicherheitsbedenken: Soweit es unser Verständnis ist, hat Nextcloud keine OAuth-Token mit Bereich, sodass jedes generierte OAuth-Token vollständigen Zugriff auf die Nextcloud-Instanz hat. Folglich sollte niemand eine Nextcloud-Instanz mit einem nicht vertrauenswürdigen Jitsi-Server verbinden, da auf alle NextCloud-Benutzer\*innenkonten Lese-/Schreibzugriff möglich ist.

Siehe:

> Security considerations

> Nextcloud OAuth2 implementation currently does not support scoped access.
> This means that every token has full access to the complete account including
> read and write permission to the stored files. It is essential to store the OAuth2
> tokens in a safe way!
> Aber leider scheint Nextcloud momentan noch keine Änderungen in dieser Hinsicht und unser Ziel ist es in Zukunft mit dem Projekt an einer Umsetzung zu arbeiten. Siehe auch [https://github.com/nextcloud/server/issues/26233](https://github.com/nextcloud/server/issues/26233)

## Ausblick

Wir haben die Möglichkeiten des Videpexports in beiden Projekten erweitert. Es ist nun möglich, Videos und Präsentationen einfach aus BigBlueButton zu exportieren und Videos aus Jitsi auf Nextcloud zu speichern. In den kommenden Tagen (hoffentlich nicht Wochen oder Monaten) werden wir mit der Jitsi-Community arbeiten, um unsere Änderungen einzupflegen.

Wir haben die Möglichkeiten der verbesserten Unterstützung des Open-Source-Videoexports mit unserer Prototyp-Entwicklung aufgezeigt und umgesetzt, jedoch haben wir unser Ziel viele weitere Open-Source-Anbieter einzubinden noch nicht erreicht. Es gibt also noch viel zu tun, um den Videoexport und Streaming besser und einfacher zu machen.

Konkret würde bei BigBlueButton auch die direkte Integration unseres Projekts die Usability für Nutzer\*innen ungemein erhöhen. Bei Jitsi würde eine Änderung der Softwarearchitektur und eine Abstraktion der Export- und Streamingfunktionalität dazu führen, dass in Zukunft weitere Open-Source-Anbieter mit weit weniger Codeänderungen hinzugefügt werden können, als dies momentan der Fall ist. Und, es gibt noch andere Open-Source-Videoprojekte, die von erweiterten Exportmöglichkeiten profitieren würden wie zum Beispiel Hangouts.

Abschließend können wir sogar feststellen, dass es selbst auf der Ebene der Endnutzer\*innensoftware - den Browsern - noch viele Möglichkeiten der Optimierung im Hinblick auf Videofunktionalitäten gibt. Auf dieses Thema konnten wir in dieser Präsentation gar nicht eingehen, aber viele kennen die Schwierigkeiten bei Videolösungen mit dem ein oder anderen Browser. Eine Kollaboration mit Browserentwicklern könnte auch im Hinblick auf Videoexport und Streaming Verbesserungen bringen.

Das Thema wird uns weiter beschäftigen und es gibt auch immer wieder neue Tools wie Chatmosphere, wo man ebenfalls über den Export von Meetings nachdenken muss und wie dies aussehen kann. Wir freuen uns auf eine spannende Zukunft und viele Mitstreiter\*innen!

Herzlichen Dank an das BMBF für die Förderung sowie an das DLR für die Unterstützung!

## Links

- Easyvideo [https://easyvideo.cc](https://easyvideo.cc)
- GitHub [https://github.com/easyvideo](https://github.com/easyvideo)
- Jitsi [https://meet.jit.si](https://meet.jit.si)
- BigBlueButton [https://bigbluebutton.org](https://bigbluebutton.org)
