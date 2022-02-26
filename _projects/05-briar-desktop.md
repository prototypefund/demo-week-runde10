---
layout: project
title: "Briar Desktop"
image: /assets/images/project_images/briar-desktop/header.jpg
authors:
  - author: Mo Zielinski
    link: 
  - author: Sebastian Kürten
    link: 
  - author: Mikolai Gütschow
    link: 
  - author: Nico Alt
    link: 
brief: "Wir entwickeln eine plattformunabhängige Desktopversion für Briar."
summary: "Briar Desktop ist die Desktop-Version (für Linux, Windows, macOS) des bisher nur für Android verfügbaren Messengers „Briar“."
---

## Demo Week Team Briar Desktop

### Briar Desktop: Was ist das und warum machen wir das?

Briar Desktop ist die Desktop-Version (für Linux, Windows, macOS) des bisher nur für Android verfügbaren Messengers „Briar“. Briar versucht im Gegensatz zu den meisten anderen Messenger-Apps auch Metadaten zu schützen und dabei so autonom wie möglich zu arbeiten. Da die Kommunikation direkt von Gerät zu Gerät abläuft, können Nachrichten auch in Gebieten versandt werden, die mit Überwachung, Zensur oder Internetproblemen zu kämpfen haben. Bei einer vorhandenen Internetverbindung wird das Tor-Netzwerk benutzt. Fällt das Internet jedoch aus, können Nachrichten weiterhin über das lokale WLAN, Bluetooth oder sogar über SD-Karten und USB-Sticks versandt werden. Briar ermöglicht es somit Menschenrechtsaktivist\*innen und Journalist\*innen, aber auch ganz normalen Bürger\*innen, unter widrigsten Umständen sicher zu kommunizieren, ohne dabei technisches Vorwissen besitzen zu müssen.

Die Desktop-Version des Messengers erweitert die Partizipationsmöglichkeiten abseits der mobilen Nutzung und trägt dadurch weiter zu einer unabhängigen Kommunikation bei. Android-Geräte sind im Allgemeinen nicht für ihre Sicherheit bekannt, weshalb großer Bedarf für eine Desktop-Version bestand. Auch die derzeit existierenden Anforderungen der Briar App, wie der hohe Akku- und Datenverbrauch, fallen bei einer Desktop-Version nicht so stark ins Gewicht. Die Möglichkeit von Gruppen-Chats in Briar Desktop lässt Briar zudem zu einer Alternative zu bestehenden Lösungen wie Mattermost und Rocket.Chat werden. Desktop-Versionen sind auch bei kommerziellen Messengern heutzutage üblich, so wussten wir, dass die Briar Community sich ebenfalls danach sehnte. Wir fanden die Tatsache großartig an einem bereits bestehenden Open-Source-Projekt arbeiten zu können, eine engagierte Community im Rücken zu haben und letztlich ein Projekt zu erweitern, das auf seinem Gebiet einen so wichtigen Beitrag leistet.

Weitere Informationen zu Briar, der Motivation der Entwickler\*innen am Projekt zu arbeiten und Aussichten für die Zukunft sind in unserem [Interview mit dem Prototype Fund](https://prototypefund.de/briar-desktop-interview) zu finden.

### Was hat uns Zeit (und Nerven) gekostet?

Für den Förderzeitraum hatten wir uns viel vorgenommen, alles geschafft haben wir am Ende nicht. Dies lag zum einen an einer Neupriorisierung von „möglichst viel umsetzen“ zu „einen Schwerpunkt möglichst gut umsetzen“ (Don’t „move fast and break things“!). Dieser Schwerpunkt war für uns die folgende Kernfunktion: Private Chats. Zum anderen gab es ein paar kleine Stolpersteine, die sich uns in den Weg legten.

In der Anfangszeit hatten wir mit dem brandneuen UI-Framework Compose for Desktop zu kämpfen, welches wir verstehen lernen mussten, um produktiv damit umzugehen. Das war unter anderem herausfordernd, weil wir kaum auf Best-Practice-Beispiele zurückgreifen konnten — die es noch immer nicht gibt. Motiviert, wie wir dennoch waren, versuchten wir uns an der Windows-Umsetzung und der zunächst grundlegenden Funktionalität, eine stabile Tor-Verbindung herzustellen. Als Nicht-Windowsnutzer\*innen mussten wir feststellen, dass sich dieses DOS-System teilweise doch ganz anders verhält als unsere gewohnte UNIX-Umgebung, weshalb Änderungen an Code-Teilen nötig wurden, die wir vorher gar nicht auf dem Schirm hatten. Schließlich haben wir es aber doch geschafft, zumindest auf unseren Entwicklungsgeräten Briar Desktop auch auf Windows und macOS zum Laufen zu bekommen, womit wir unser Ziel ("Wir entwickeln eine plattformunabhängige Desktopversion für Briar") erreicht haben, wenn auch die Unterstützung für Plattformen neben Linux noch nicht für die Öffentlichkeit bereit ist. Hier steht noch Arbeit an, die in Zukunft angegangen werden muss.

Bei unserer Arbeit standen wir stets im engen Kontakt mit dem Briar-Core-Team, so ergab sich die Notwendigkeit, dass wir an einigen Stellen auch den Core Code verbesserten und sich dadurch längere Review-Zyklen entwickelten. Dieses Engagement würden wir dennoch als Win-Win für beide Seiten verbuchen. Zu guter Letzt haben unsere regelmäßigen Code-Reviews viel Zeit in Anspruch genommen, jedoch gewährleistete dieses Verfahren auch eine bessere Code-Qualität.

### Die Zusammenarbeit mit der Community

Die Community, die sich um Briar in den letzten Jahren gebildet hat, ist wundervoll. Alle EntwicklerInnen von Briar Desktop haben vorher schon bei anderen Projekten Freier Software mitgearbeitet und alle sind sich einig, dass Briar in diesem Kontext etwas Besonderes ist. Es passiert immer wieder, dass Menschen einfach so aus dem Nichts auftauchen und ihre Hilfe anbieten — zum einen, indem sie nachfragen, was es zu tun gibt; zum anderen aber auch proaktiv, indem sie Missstände erkennen und einfach selbst beheben.

Ohne diese Community würde Briar Desktop heute wahrscheinlich ganz anders aussehen. Lange bevor unsere aktive Förderphase im September startete, begann schon jemand aus der Community mit der Entwicklung eines allerersten Prototypen auf Basis des UI Frameworks Compose. "Veni, vidi, vici", könnte man sagen, denn das Design, welches das Community-Mitglied damals entwarf, wird heute genauso in Briar Desktop verwendet. Während der gesamten Förderphase unterstützte er uns in der Entwicklung und fragte nach, was es zu tun gab. Oftmals entwickelte er dann übers Wochenende einen kleinen Prototypen für die entsprechende Funktionalität, sodass wir zu Wochenbeginn direkt eine solide Grundlage hatte, um die Funktionalität in Windeseile implementieren zu können. An dieser Stelle nochmal vielen Dank an dich, Paul, für deine Unterstützung in den letzten Monaten!

Auf dem Mastodon-Account eines Community-Mitglieds wurden zudem immer wieder Screenshots aus Entwicklungs-Chats und GitLab-Issues "geleakt", die auf große Resonanz im Fediverse trafen. So hatte das Briar Team von Anfang an Feedback zu Briar Desktop. Der erste Release im Januar wurde entsprechend ein voller Erfolg, dessen Ankündigung es bis auf Platz 1 der Hacker News schaffte. Dort wurde die Ankündigung nämlich von der Community erneut veröffentlicht und ausführlich kommentiert, ohne Mitwirken des engeren Briar Teams.

Die Communitymitglieder im Fediverse sind aber nicht die einzigen, die auf glühenden Kohlen sitzen, wenn es Neuigkeiten zu Briar Desktop gibt. Auf jeden Fall erwähnt werden müssen auch die vielen Übersetzer\*innen aus der ganzen Welt (von der NGO Localization Lab organisiert), die Briar Desktop bereits in 25 Sprachen übersetzt haben. Ziemlich zuverlässig trudelten schon einige Stunden nach dem Hochladen neuer Texte die ersten Übersetzungen ein. Vor dem Release neuer Briar Desktop Versionen kommt es zu einem regelrechten Sprint, mit neuen Übersetzungen der Community im Minutentakt.

### Nächste Schritte

Durch die Förderung des Prototype Fund sind auf jeden Fall einige Sachen ins Rollen gekommen und die Community um Briar hat sich direkt auf das Desktop-Programm gestürzt, das schon so lange sehnsüchtig erwartet wurde. Auch wenn die bisherigen Features von Briar Desktop (Private Chats auf Linux via Internet und lokalem LAN) bereits sehenswert sind, so besteht doch großes Interesse an einer Weiterentwicklung von Briar Desktop.

Am größten ist das Interesse hierbei an privaten Gruppen und Foren, den zwei Spielarten von Gruppen-Chats in Briar. Da es bei Briar keine zentralen Server gibt und das ständige Online-Sein sowohl auf den Akkuverbrauch als auch auf das Datenvolumen geht, stellt Briar Desktop hier eine tolle Möglichkeit dar, Gruppen-Chats in Briar auch auf Android-Geräten einfacher benutzbar zu machen. Durch die dauerhafte Internet- und Stromverbindung könnte Briar Desktop so zuverlässiger online sein und Nachrichten in Gruppen-Chats sammeln und weiterverteilen. Briar Desktop wird mit diesen Gruppen-Chats auch zu einer ernsthaften Alternative zu anderen Chat-Lösungen wie Mattermost, Matrix, Rocket Chat und Slack. Zumindest das Briar-Team plant langfristig einen Großteil seiner internen Kommunikation über Briar selbst abzuwickeln, was als "Dogfooding" ein großer Motivationspunkt für die Weiterentwicklung an Briar ist.

Zu erwähnen ist aber auch das Interesse an Briar auf anderen Plattformen neben Linux. Es ist nun einmal so, dass Linux nur einen Marktanteil von ca. 2% hat, auch wenn dieser Anteil in der Zielgruppe von Briar sicherlich etwas höher liegt. Briar will aber keine Programme im leeren Infosec-Labor entwickeln, sondern die Nutzer\*innen auf den Plattformen unterstützen, auf denen sie unterwegs sind. Deshalb wurde die Entwicklung von Briar vor über 10 Jahren auf Android und in Java gestartet und deshalb werden wir Briar Desktop in Zukunft auch auf Windows und macOS anbieten.

Um all diese interessanten Funktionalitäten in Briar einzubauen, haben wir uns bereits und werden uns auch in Zukunft um Anschlussförderung bewerben. Dank dem Prototype Fund haben wir nun eine solide Basis, auf die zukünftig aufgebaut werden kann.

### Tutorial für Briar Desktop

Im Folgenden beschreiben wir Schritt für Schritt, wie du Briar Desktop ausprobieren und nutzen kannst. Bisher sind noch nicht alle Funktionalitäten der Android-App enthalten: der Desktop Client kann bisher nur über die Internetverbindung (via Tor) oder das lokale Netzwerk (LAN/WLAN) kommunizieren, Bluetooth wird noch nicht unterstützt. Auch sind bisher nur Einzelchats möglich (Gruppenchats, Foren und Blogs werden in der nächsten Entwicklungsphase umgesetzt).

#### Download und Installation

Auf [https://desktop.briarproject.org](https://desktop.briarproject.org) findest du die verfügbaren Downloaddateien für deine Betriebssystemversion.

Für Linux: Wähle die passende Datei für dein System aus den vier Downloaddateien aus.

Für Windows und macOS: noch nicht veröffentlicht. Auch hier müssen wir in der nächsten Entwicklungsphase nochmal ran. Aber die gute Nachricht ist, wir haben auf beiden System bereits erfolgreich getestet.

#### Account erstellen

Beim Start von Briar Desktop nach der ersten Installation hast du die Möglichkeit einen Account zu erstellen.

Der Benutzername kann frei gewählt werden. Bitte beachte: Diesen Namen sehen andere Kontakte und er kann nicht nachträglich geändert werden.

![1](/assets/images/project_images/briar-desktop/1.png)

Das Passwort sollte mindestens 8 Zeichen lang und komplex genug sein.

![2](/assets/images/project_images/briar-desktop/2.png)

**Hinweis**: Die Account-Informationen werden verschlüsselt und nur auf deinem Gerät gespeichert. Falls du dein Passwort vergessen solltest, ist ein Zugriff auf deinen Account nicht mehr möglich. Niemand kann deinen Account wiederherstellen.

#### Kontakte hinzufügen

Über das blaue Symbol mit dem Pluszeichen kannst du neue Kontakte hinzufügen. Bis diese bestätigt wurden, sind sie als “Ausstehende Kontakte” in der Kontaktliste gekennzeichnet.

![3](/assets/images/project_images/briar-desktop/3.png)

Für die erste Kontaktaufnahme haben du und dein Kontakt 48 Stunden Zeit, eure persönlichen Briar-Links auszutauschen. Dabei musst du deinen Briar-Link an den gewünschten Kontakt schicken und dein Kontakt muss dir seinen/ihren Briar-Link schicken.

![4](/assets/images/project_images/briar-desktop/4.png)

Trage den Briar-Link deines neuen Kontakts ein und gib dem Kontakt einen Namen. Der Kontaktaustausch wird erfolgreich ausgeführt, wenn ihr beide zeitgleich online seid (innerhalb der 48 Stunden).

**Hinweis**: Kommt die Kontaktaufnahme innerhalb von 48 Stunden nicht zustande, müsst ihr es nochmal aufs Neue versuchen. Du und dein gewünschter Kontakt müssen sich gegenseitig löschen und ihr beginnt erneut mit dem Austausch der Briar-Links.

#### Nachrichten verschicken

Sobald der Kontakt erfolgreich hinzugefügt wurde, könnt ihr miteinander chatten. Die Nachrichten werden dabei nur zwischen diesen beiden Geräten ausgetauscht.

Wähle den Kontakt, mit dem du chatten möchtest. Ihr müsst beide online sein, damit eure Nachrichten übertragen werden. Wenn ein Kontakt online ist, wird der Punkt neben dem Kontakt grün.

Aktuell können Textnachrichten und Bilder (JPEG und PNG) versendet werden.

![5](/assets/images/project_images/briar-desktop/5.png)

#### Kontakte einander vorstellen

Wenn du in deiner Kontaktliste eine Person ausgewählt hast, kannst du oben rechts im Menü des Kontakts mit “Kontaktempfehlung abgeben” eine Kontaktvorstellung machen. Dabei kannst du den ausgewählten Kontakt einer anderen Person aus deiner Kontaktliste vorstellen.

![6](/assets/images/project_images/briar-desktop/6.png)

**Hinweis**: Wenn du Kontakte einander vorstellst, dann müssen beide nicht mehr ihre Briar-Links austauschen. Durch dich wird der Kontakt sofort hergestellt, sobald beide online sind und die Einladung akzeptieren. Hierbei gibt es nicht das 48-Stunden-Limit, das beim direkten Link-Austausch gilt.

### Links

* Download: [https://desktop.briarproject.org](https://desktop.briarproject.org)
* Präsentation „Diving deep into Briar“ beim XMPP Meetup Berlin: [https://www.youtube.com/watch?v=sKuljekMzTc](https://www.youtube.com/watch?v=sKuljekMzTc)
* Briar-Community: [https://matrix.to/#/#briar:matrix.org](https://matrix.to/#/#briar:matrix.org)
* Code: [https://code.briarproject.org/briar/briar-desktop](https://code.briarproject.org/briar/briar-desktop)

### Wir sagen Danke!

Die Förderung durch den Prototype Fund hat dieses fantastische Projekt ermöglicht. Wir danken daher dem BMBF für dieses wertvolle Programm, dem DLR für die unkomplizierte Zusammenarbeit, dem Prototype Fund Team für die geschmeidige Organisation sowie Team + Community von Briar für ihr Engagement!

