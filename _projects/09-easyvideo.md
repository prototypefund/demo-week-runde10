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

# Easyvideo: Wir ermöglichen Streaming, Aufnahme und Export für Open-Source-Videolösungen

Unser Team organisiert seit Jahren Meetups, Konferenzen und veranstaltet Seminare an Universitäten. Nicht erst seit Corona benutzen wir dafür auch Online-Videotools, wie BigBlueButton oder Jitsi. Leider fehlen populären Open-Source-Videolösungen Streamingoptionen und Exportfunktionen von Aufnahmen ganz wie bei BigBlueButton oder Aufnahmen sind nur mit proprietären Anbietern möglich, z.B. Jitsi mit Youtube und Dropbox. Für die freie Dokumentation von Events und Lehrveranstaltungen ist das ein Problem. Während Corona wurden Tools wie OBS populär, die Aufnahmen direkt auf dem Computer ermöglichen. Zudem gab es Hacks, die von verschiedenen Entwicklern ins Netz gestellt wurden und einzelne Funktionen anboten, oft jedoch nicht für eine größere Nutzergruppe weiterentwickelt wurden. Unser Ziel für das Projekt ist es nun auf Grundlage der Arbeit in der Open-Source-Community Videoexportfunktionen für die zwei bekanntesten Lösungen BigBlueButton und Jitsi zu entwickeln.


## Warum Open Source

Unser Team hat einen internationalen Background und aus eigenen Erfahrungen heraus wissen wir wie große Clouddienste z.B. in einigen asiatischen Ländern Bürgerinnen einschränken und kontrollieren können. Aufgrund dieser Erfahrung vertrauen wir unabhängigen freien Open-Source-Lösungen einfach mehr. Unsere Meinung ist, dass gerade Lehrende und Studierende die Vorzüge freier Open Source-Software in Anspruch nehmen können sollen und daher ist es unser Ziel insbesondere Bildungseinrichtungen in die Lage zu versetzen Open Source-Lösungen wie offene Videolösungen zu nutzen oder von lokalen Open-Source-Firmen Unterstützung zu erhalten. Auch um die digitale technologische Unabhängigkeit (Souveränität) von proprietären Videodiensten und lokalen Cloudanbietern zu erhalten, benötigen wir Open-Source-Videodienste, die mit proprietären Anbietern konkurrieren können.


## Das Ziel

Das ultimative Ziel unseres Projekts ist es, dass alle Menschen freie Open-Source-Videosysteme nutzen können, die einfach dokumentiert werden können mit Hilfe von Export- und Streamingfunktionen. Dafür wollen wir Plugins oder Erweiterungen zur Verfügung zu stellen - um Veranstaltungen aufnehmen und streamen zu können. Insbesondere wollen wir den Videoexport auf den eigenen Rechner, Streaming zu Peertube und gängigen Medienkanälen, und die Speicherung auf Nextcloud, FTP und Git implementieren.


## Die ersten Schritte

Die momentan weithin meistgenutztesten Open-Source-Online-Videolösungen sind BigBlueButton und Jitsi. Unser Ziel war, dass eine möglichst große Nutzergruppe unsere Entwicklungen nutzen kann und daher konzentrierten wir uns zuerst auf BBB und Jitsi. Mittels Benutzeroberfläche sollten Endnutzerinnen den Video-Export nutzen können.


## Herausforderungen

Die erste Herausforderung war sich einen Überblick über bestehende Ansätze von CodeprojektenVideo-Export-Funktionen zu verschaffen. Es gibt eine Vielzahl von Ansätzen und Technologien die an unterschiedlichen Orten im Netz veröffentlicht wurden. Unser Ansatz war, dass wir, wenn möglich nichts neu entwickeln wollten, was es woanders vielleicht schon (besser) gibt. 

Die zweite Herausforderung war, dass wir uns mit einer Vielzahl von Technologien, Frameworks und Bibliothekenabhängigkeiten a) bei BBB und Jitsi auseinandersetzen müssen und b) bei Lösungen, die wir anbinden wollen, z.B. Nextcloud. Jede Lösung hat ihren eigenen Technologiestack und Architektur und für ein gutes Verständnis benötigt man Zeit. Die technischen Fragen der Umsetzung beinhalten auch die Frage, wie eine Lösung für Exportfunktionalitäten implementiert werden soll und welche technischer Ansatz der langfristig wahrscheinlich vielversprechendste ist. 

Bei der dritten Herausforderung geht es um die Frage der Community und des Entwicklerteam. Würde ein Pull Request mit einer neuen Videoexportfunktion bei den Hauptentwicklern einer Video-Online-Lösung akzeptiert werden? Wie stehen die Chancen? Welche technischen “Best Practices” existieren? Ist eine Funktion eventuell “Out of Scope”? Was ist innerhalb der Zeit im Prototypefund möglich und realistisch?


## Implementierung Export aus BBB

Bei der Implementierung des Exports von Videos und Präsentationen auf BBB heraus gab es zunächst die Frage, sollen wir die Funktionalität direkt in BigBlueButton integrieren oder als externes Tool zur Verfügung stellen? Hintergrund: Um eine Codeänderung in ein etabliertes Projekt zu bekommen gibt es oft einen längeren Prozess, der garantiert, dass die Änderungen den Ansprüchen der Hauptentwickler genügen und im Scope sind, also “reinpassen”. Das beinhaltet auch oft eine längere Diskussion. Da wir für das Projekt eine beschränkte Zeit hatten und sicherstellen wollten, dass Nutzern möglichst bald ein Video-Export-Tool für BBB zur Verfügung steht, haben wir uns für eine externe Lösung entschieden, die nicht direkt in BBB integriert ist. Ein zusätzlicher Grund war, dass wir uns nicht über Interessenskoflikte der Firma hinter BBB im Klaren waren, denn die Firma stellt selbst kommerzielle BBB-Dienste zur Verfügung, die zusätzliche Funktionalitäten enthalten (u.a. auch Videofunktionalitäten), die in der Open-Source-Software nicht enthalten sind.

Das Ziel unseres BBB-Tools ist es, den Export von Videos und Präsentationen aus BigBlueButton-Instanzen zu ermöglichen. Der BBB-Videoexporter muss nicht auf dem BBB-Server selbst installiert werden, sondern kann auf externen Servern als separates Tool betrieben werden. Die Applikation kann man auf dem eigenen Computer mit einem lokalen Server installieren oder online zum Laufen bringen. Es gibt zwei Möglichkeiten Videos und Präsentationen von BBB zu exportieren a) über die Befehlszeilenschnittstelle (Commandline) oder b) über ein Webinterface in einem Browser. Sobald man die Installation des Tools abgeschlossen hat, kann man die Video-URLs von aufgenommenen BBB-Sessions in das Webformular vom BBB-Exporter kopieren und den Export starten. Als erstes unterstützen wir den Export aller BBB-Daten inklusive aufgenommener Videos, Präsentationsdaten und Chat. Momentan arbeiten wir zudem noch am automatisiertem Zusammenfügen dieser Daten in ein Videofile. Bisher war es nicht möglich aufgenommene Veranstaltungen von BigBlueButton zu exportieren und zum Beispiel auf eine eigene Webinstanz hochzuladen. Das ist mit unserem Tool nun möglich. Eine Webapp zum Testen bieten wir auf [bve.easyvideo.cc](http://bve.easyvideo.cc) an.

![Proximity based interaction in Chatmosphere](/assets/images/project_images/easyvideo/easyvideo_bbbexporter.png)


## Implementierung Export aus Jitsi nach Nextcloud

Bei der Implementierung eines Exports ohne die Nutzung proprietärer Dienste haben wir uns für die Unterstützung von Nextcloud entschieden. 

Ein Vorteil war, dass Jitsi bereits über eine Exportfunktionalität für proprietäre Dienste verfügt an der wir uns orientieren konnten. Eine Herausforderung, die wir bei der Implementierung feststellen mussten, waren Schwierigkeiten in bezug auf den Austausch zwischen Jitsi und Nextcloud. Wir konnten auf Seiten von Jitsi die Funktionalität zum Exportieren von Videos erfolgreich implementieren und auf einem lokalen Rechner zum Laufen bringen.

Während der Projektentwicklung haben sich jedoch technische Beschränkungen gezeigt, die auf Seiten des Nextcloud-Projekts existieren. Es fehlt die Möglichkeit einen beschränkten Zugriff auf eine gesicherte Verbindung mittels OAuth-Token zu geben. Hierbei benötigt man für die Verbindung im Browser auch sogenannte CORS header, womit die Authentifizierung und das Empfangen in Webapplikationen möglich ist. Diese sendet Nextcloud momentan noch nicht. Unser Ziel ist es in den kommenden Monaten mit der Nextcloud-Community zusammen zu arbeiten, um das zu lösen und Jitsi anbinden zu können. 


## Ausblick

Wir haben die Möglichkeiten der verbesserten Unterstützung des Open-Source-Videoexports bei BBB und Jisti mit unserer Prototyp-Entwicklung aufgezeigt und umgesetzt. Es ist nun möglich Videos und Präsentationen einfach aus BigBlueButton zu exportieren und wir konnten einen prototypischen Export von Jitsivideos auf Nextcloud zeigen.

Bei der Entwicklung haben wir Nutzerfeedback für Verbesserungen erhalten, die wir in Zukunft angehen wollen. Erstens bei BBB wollen wir mit dem Projektteam die direkte Integration unseres Projekts diskutieren, um die Benutzerfreundlichkeit zu erhöhen. Zudem wollen wir hier neben den Webformaten, weitere Exportformate unterstützen. Zweitens bei Jitsi sind für das Funktionieren des Videoexports zusätzliche Änderungen beim Counterpart Nextcloud notwendig. Danach können wir mit den Jitsi-Entwicklern kooperieren um Änderungen in das Hauptprojekt einzupflegen. Drittens gibt es noch viele weitere Open-Source-Videoprojekte, die von Exportmöglichkeiten profitieren würden, wie zum Beispiel Jangouts, an denen wir gerne arbeiten würden. Wir freuen uns auf eine spannende Zukunft und viele Mitstreiter!

Ohne die großartige Unterstützung des Teams vom Prototype Fund, vom BMBF und DLR wäre die Entwicklung nicht möglich gewesen. Die Förderung war eine tolle Möglichkeit an dem Projekt zu arbeiten. Vielen Dank allen die das Projekt möglich gemacht haben!


## Links

* [Easyvideo Test app](http://bve.easyvideo.cc)
* [GitHub](https://github.com/easyvideo) 
* [Jitsi](https://meet.jit.si) 
* [BigBlueButton](https://bigbluebutton.org) 
