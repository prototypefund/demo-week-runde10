---
layout: project
title: "Boxtribute-api-plus"
image: /assets/images/project_images/boxtribute/header.png
authors:
  - author: Philipp Metzner
    link: https://boxtribute.org
brief: "Wir ermöglichen eine würdevolle Versorgung von Bedürftigen in Notsituationen."
summary: "Unsere Partnerorganisationen können über eine Schnittstelle auf ihre Daten zugreifen und einfacher Waren untereinander austauschen."
---

Aufgrund von Krieg und Verfolgung gibt es allein im Mittelmeerraum, in den Balkanstaaten und im Nahen Osten Millionen von Hilfsbedürftigen in humanitären Notsituationen, die auf Unterstützung bei Unterkunft, Ernährung und Wasser, sanitären Einrichtungen und Hygiene angewiesen sind.

In den Hotspots der europäischen Flüchtlingskrise füllen kleinere, oft lokale Organisationen Lücken in der Grundversorgung und Verteilung. Internationale Organisationen haben bereits einen Großteil der operativen Arbeit an lokale Organisationen übergeben, doch die Zusammenarbeit zwischen den verschiedenen Akteur\*innen wird oft durch die instabile Lage vor Ort und fehlende gemeinsame Standards erschwert. Vor allem der Informationsaustausch zwischen den Organisationen ist ein Kernproblem in der humanitären Hilfe, welches die Wirksamkeit der Hilfe vor Ort einschränkt. Auf Beschaffung, Transport, Lagerung und Verteilung von Hilfsgüter entfallen schätzungsweise 60 bis 80 Prozent der Gesamtkosten von humanitären Aktivitäten.

## Eine simple digitale Lösung

boxtribute ist eine Web-Anwendung, die es humanitären Organisationen ermöglicht, eine nachhaltige und würdevolle Versorgung von Bedürftigen in Notsituationen zu organisieren. 13 lokale Organisationen nutzen bereits unsere App in Geflüchteten-Camps und an Warensammelstellen in ganz Europa.

<video src="/assets/images/project_images/boxtribute/boxtribute-intro.mp4" autoplay controls muted loop width=800></video>

## Neue Features für verbesserte Koordination

Wir wollen zusätzliche Features für boxtribute entwickeln, um die Koordinierung unserer Nutzer\*innen und den Austausch von Informationen zu verbessern: Zwischen den Organisationen untereinander “im Feld”, zwischen denjenigen “im Feld” und in Spenderländern wie Deutschland und durch die Abfrage der Hilfsgüter-Datenbank. Hierzu gehört unter anderem die Entwicklung einer Schnittstelle im Backend unserer existierenden boxtribute Web-App.

Die aktuelle Version der Web-App ermöglicht es nur den Entwickler\*innen, Hilfsgüter manuell zwischen Organisationen zu verschieben. Unser Ziel ist es aber, dass Organisationen selbständig Hilfsgüter untereinander transferieren und Informationen über ihre Bestände miteinander teilen können.

Hierzu bauen wir ein Python-Flask-Backend mit einer GraphQL API auf. Diese Schnittstelle ermöglicht es unseren Nutzer\*innen außerdem auf ihre eigenen Daten in der MySQL-Datenbank zuzugreifen. Daten über Hilfsempfänger\*innen und Warenbestand können nun von unseren Partnerorganisationen flexibel und selbständig ausgewertet werden.

## Wo stehen wir jetzt?

Das Gerüst des neuen Backends steht, inklusive ausgereifter Test-Umgebung. Mit einer strikten und genauen Authorisation stellen wir sicher, dass verschiedene Nutzergruppen nur im Rahmen ihrer jeweiligen Berechtigungen mit den Daten interagieren. Das Veröffentlichen der GraphQL API ist momentan im Gange, und unsere Partner-Organisation Hermine e.V. wird die Schnittstelle testen.

Die Erweiterung des Backends und der bestehenden Datenbank für den Box-Transfer wurde geplant und umgesetzt. Die Entwicklung eines entsprechenden Frontends ist außerhalb des Projektrahmens. Leider fanden sich keine sonstigen Kapazitäten im Team, so dass das geplante Testen des Features durch eine Partnerorganisation noch nicht stattfinden konnte.

## Die Projektarbeit

boxtribute ist eine NGO, in der sich verschiedene Teams um Funding, Öffentlichkeitsarbeit, User-Support, und Software-Entwicklung kümmern. Die meisten Team-Mitglieder arbeiten auf ehrenamtlicher Basis, ein gemeinsames Büro gibt es nicht. Ich hatte das Glück, als Einzelperson ein halbes Jahr lang mit einer halben Stelle über den Prototype Fund gefördert zu werden. Zu boxtribute bin ich im Frühjahr 2020 gestoßen.

Während des Projektzeitraums hatte ich meistens Austausch mit einem weiteren Senior-Entwickler und unserer Produktmanagerin. Werktags trafen wir uns mindestens einmal, um uns kurz über laufende Aufgaben zu synchronisieren und mögliche Blockaden zu bearbeiten. Bei Bedarf hielten wir längere Treffen ab, um Use-Cases, Anforderungen, Software-Architektur etc. zu besprechen. Wir führen Protokoll bei unseren Meetings und definieren im Ausgang konkrete Aufgaben für die Teilnehmenden. Unsere Kommunikation läuft über Slack ab (Channel ermöglichen eine gute Abgrenzung der Aufgabengebiete). Im Detail werden Aufgaben in [trello](https://trello.com/b/2Dn4bpqD/boxtribute-product-development) verteilt. Im Software-Entwicklungsprozess folgen wir dem Konzept von test-driven development (TDD).

Bereits seit Anfang 2021 veranstaltet das Entwicklungsteam ein monatliches Team-Wochenende. Das gibt den ehrenamtlichen und angestellten Mitgliedern, die sich ja unterschiedlich intensiv mit der Software auseinandersetzen, die Möglichkeit, sich über die Fortschritte auszutauschen und Aufgaben synchron zu bewältigen. Genauso nehmen wir uns die Zeit zum gegenseitigen Kennenlernen und Team-Building. Ich schätze es sehr, neben dem eher technischen täglichen Austausch auch persönliche Verbindungen im Team zu fördern.

## Unser Stack

Die momentan genutzte Version 1 der boxtribute-Webanwendung ist eine PHP-App mit einer MySQL-Datenbank.

### Anforderungen

Für die Datenschnittstelle und Version 2 sind die Anforderungen an den Tech-Stack:
- Kompatibilität mit der bestehenden Datenbank.
- Sicherheit: Nutzer\*innen können nur auf authorisierte Ressourcen zugreifen. Dadurch ist maximaler Schutz von personenbezogenen Daten (der Hilfsempfänger\*innen) gewährleistet.
- Wartbarkeit und Skalierbarkeit: Durch eine moderne, modulare Architektur, kompakte Dokumentation, sowie ausführliche Tests soll die Komplexität der Software gering gehalten und Erweiterungen (auch durch Neumitglieder) ermöglicht werden.

### Technologien

![Tech-Stack](/assets/images/project_images/boxtribute/tech-stack.png)

Wir verwenden `flask`, da es ein populäres Web-Framework für Projekte von der Größenordnung von boxtribute ist. Unser GraphQL-Server ist `ariadne`, was sich hervorragend mit `peewee` integriert, das wir zur Abstraktion von Datenmodellen verwenden. Das aktuelle GraphQL-Schema kann [hier](https://github.com/boxwise/boxtribute/tree/master/back/boxtribute_server/graph_ql) eingesehen werden.

Jede Anfrage von authentifizierten Nutzer\*innen enthält Informationen über ihre Organisationszugehörigkeit und ihre Berechtigungen. Dieses JSON Web Token (JWT) wird beim Login in die App durch den Service `Auth0` bereitgestellt. Dank dieser Plattform müssen wir keine eigene Lösung zum Management von Nutzer\*innen entwickeln.

## Box-Transfer

Wir betrachten zwei fiktive Organisationen, Spenden ohne Grenzen und BoxAid, die bereits boxtribute nutzen. Spenden ohne Grenzen (SoG) sammelt in Deutschland gespendete Hilfsgüter, wie z.B. Kleidung, Zelte, Medizin, oder andere Bedarfsgegenstände. In einem Warenlager sind diese Güter aufbewahrt. Über ein Netzwerk erfährt SoG, dass BoxAid in Griechenland großen Bedarf an Bekleidung und Unterkünften hat, da der Winter vor der Tür steht. Auf boxtribute stellt SoG eine Anfrage, um mit BoxAid eine Vereinbarung für den Transfer von Hilfsgütern zu schließen. Sie koordinieren sich, wie lange die Vereinbarung gültig ist (wobei Kündigung von beiden Seiten jederzeit möglich ist) und welche ihrer Standorte involviert sein können (es ist möglich, dass z.B. BoxAid an mehreren Standorten in Griechenland operiert, gleichzeitig jedoch nur ausgewählte Standorte Teil einer Kooperation werden sollen). Wenn BoxAid die Anfrage für die Vereinbarung angenommen hat, kann SoG damit beginnen, eine Sendung von Hilfsgütern vorzubereiten. Dazu werden alle benötigten Boxen gescannt und auf Paletten gesammelt. Falls eine Box digital versehentlich zu einer Sendung hinzugefügt wurde, kann sie einfach wieder in den Warenbestand zurückgeführt werden.  Eine Spedition transportiert die Sendung nach Griechenland. BoxAid stellt beim Empfang zunächst fest, ob alle Boxen, wie im System angegeben, angekommen sind. Ggf. klären sie mit SoG, ob fehlende Boxen noch in Deutschland stehen oder auf dem Transportweg verloren gegangen sind. Die Hauptaufgabe für BoxAid ist allerdings das Überführen der Waren in ihr eigenes Lager: Weil jede Organisation ihre eigenen Produktbezeichnungen verwenden kann, muss BoxAid die Produkte aus der Sendung ihren eigenen zuordnen. Beispielsweise enthält eine Box Mäntel mit der (von SoG zugeteilten) Produktbezeichnung 'Wintermäntel'. Da BoxAid auf Englisch operiert und allgemeinere Bezeichnungen verwendet, ordnen die Mitarbeitenden die Box der Bezeichnung 'coats' zu (falls noch nicht vorhanden, wird die Bezeichnung zunächst erstellt). Sind alle Boxen auf die Lagerräume von BoxAid verteilt, ist die Sendung abgeschlossen.

## Ausblick

Wie oben bereits angedeutet, ist einige Arbeit am Frontend vonnöten, um die erweiterte Funktionalität des Backends den Nutzer\*innen zur Verfügung zu stellen. Hast du Erfahrung mit React und Lust, dich bei uns einzubringen ;-)? Im gleichen Zuge wollen wir die bestehende erste Version unserer App (in PHP) vollständig auf den neuen Stack migrieren.

Erfreulicherweise bleiben wir auch dem Prototype Fund erhalten (oder umgekehrt). Ab März 2022 werden zwei Mitglieder von uns User-Research betreiben, um die Anforderungen für mobile Verteilungen von Hilfsgütern abzustecken.

## Outro

Ich bin sehr dankbar, die Gelegenheit gehabt zu haben, mich hauptberuflich auf die Arbeit an einem so sinnigen, wertvollen Open-Source-Projekt wie boxtribute fokussieren zu können. In den letzten sechs Monaten konnte ich einiges über Projektplanung, Design, Team-Arbeit und neue Technologien lernen. Ein herzliches Dankeschön an das Bundesministerium für Bildung und Forschung für die finanzielle Förderung und den Prototype Fund für die begleitende Unterstützung! Unsere Software konnte einen großen Entwicklungsschritt machen.

## Links

- [Website](https://boxtribute.org)
- [GitHub](https://github.com/boxwise/boxtribute)
- [Instagram](https://www.instagram.com/boxtribute_ngo/)