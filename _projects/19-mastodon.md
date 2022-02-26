---
layout: project
title: "Mastodon"
image: /assets/images/project_images/mastodon/header.jpg
authors:
  - author: Eugen Rochko
    link: https://mastodon.social/@Gargron
brief: "Wir entwickeln eine Android-App für Mastodon"
summary: ""
---

In den letzten 6 Monaten hatte ich das Vergnügen, mit der Unterstützung des Prototype Fund an der Verbesserung von Mastodon zu arbeiten. [Mastodon](https://joinmastodon.org) ist die größte nicht-kommerzielle und dezentralisierte Alternative zu Twitter und Facebook und nimmt in der europäischen Szene stetig an Bedeutung zu. Es handelt sich um Open-Source-Software, die Nutzender unter ihren eigenen Domänennamen installieren und ausführen können, um ihr eigenes soziales Netzwerk zu erstellen. Im Gegensatz zu herkömmlicher Blogging-Software verwendet sie jedoch ein Datenaustauschprotokoll namens [ActivityPub](https://www.w3.org/TR/activitypub/), mit dem Nutzer\*innen Updates empfangen und an andere Mastodon-Server senden können. Hier sind die neuen Entwicklungen, die im Rahmen der Förderung entstanden sind.

### Bearbeiten veröffentlichter Beiträge

![Ein Beitrag, der mehrmals bearbeitet wurde](/assets/images/project_images/mastodon/image1.png)

Fehler passieren nunmal. Manchmal sieht man erst, dass etwas nicht stimmt, wenn es schon veröffentlicht wurde. Wenn man es schnell bemerkt, kann der Beitrag gelöscht und erneut veröffentlicht werden, aber wenn der Beitrag bereits Antworten oder andere Interaktionen erhalten hat, würde das die Konversation sprengen. Aus diesem Grund wird seit langem nach einer echten Bearbeitungsfunktion in Mastodon gefragt. Aber Bearbeitung birgt Risiken: Ein Beitrag, der Aufmerksamkeit mit einer Botschaft erregt hat, kann bearbeitet werden, um das Gegenteil zu sagen. Die Problematik ist also mit Vorsicht anzugehen: Die Vorgängerversionen müssen zugänglich bleiben und Änderungen müssen von denjenigen bemerkt werden, die Beiträge teilen.

Ich habe daran gearbeitet, diese Bearbeitungsfunktion in Mastodon zu implementieren. Dazu gehören zwei Dinge. Erstens muss Mastodon dazu gebracht werden, die jeweilige ActivityPub-Nachricht zum Aktualisieren eines Beitrags zu verstehen. Die Darstellung von Bearbeitungen in ActivityPub ist einfach genug. Aber Mastodon wurde ursprünglich mit der Erwartung geschrieben, dass Beiträge nur einmal erstellt und nie geändert werden. Daher musste der sehr wichtige „Hot Path“-Code geändert werden, um sowohl die Erstellung von Grund auf als auch die Aktualisierung eines zuvor bekannten Beitrages zu verarbeiten.

Beim Aktualisieren eines zuvor bekannten Beitrages muss der „Soll“-Status des Beitrags dem „Ist“-Status zugeordnet werden, und Unterschiede müssen für jede Art von interner Assoziation aufgelöst werden: Medienanhänge, Umfragen, Hashtags und Erwähnungen. Da die Historie der Bearbeitungen erhalten bleiben muss, habe ich mich entschieden, die Text- und Inhaltswarnung (d. h. den gesamten Textinhalt eines Beitrags) in einem separaten Datenbankeintrag aufzuzeichnen, während der Hauptdatenbankeintrag des Beitrags nur die neuesten Informationen enthält. Ich habe mich entschieden, nicht den genauen Zustand jeder Bearbeitung zu speichern, da der Zustand auf viele verschiedene Datenbankeinträge aufgeteilt ist. Stattdessen notiere ich bei jeder Bearbeitung nur, ob die Medienanhänge oder die Umfrage geändert wurden.

Diese Änderungen werden, sobald sie in der Datenbank gespeichert sind, über die REST-API allen zur Verfügung gestellt, die die Berechtigung zum Anzeigen des ursprünglichen Beitrags haben. Die Bearbeitung wird über die Streaming-API verteilt, sodass Personen, die den Originalbeitrag in einer mit der Streaming API verbundenen App auf ihrem Bildschirm haben, sofort die neuere Version sehen. In der Web-App wird ein bearbeiteter Beitrag durch ein Sternchen (\*) neben dem relativen Zeitstempel des Beitrags gekennzeichnet, wenn sich der Beitrag in einer Chronik befindet. Wenn der Beitrag im Detail angezeigt wird, wird der vollständige Zeitstempel der Bearbeitung angezeigt. Dieser Zeitstempel kann angeklickt werden, um ein Dropdown-Menü zu öffnen, das den Bearbeitungsverlauf lädt. Jeder Eintrag kann dann angeklickt werden, um diese bestimmte Version anzuzeigen.

Für jede\*n Benutzer\*in, die oder der den ursprünglichen Beitrag geteilt hat, wird eine neue Art von Benachrichtigung erstellt. Dies soll zwei Dinge sicherstellen: Erstens können Menschen die Freigabe rückgängig machen, wenn der Beitrag mit böswilliger Absicht aktualisiert worden ist und zweitens wird die Korrektur von mehr Menschen gesehen, wenn der Beitrag sachlich korrigiert wurde.

Der zweite Teil ist die Bearbeitung selbst. Dieser Teil passiert separat, da der erste Teil zuerst über das Mastodon-Netzwerk verfügbar gemacht werden muss. Benutzer\*innen könnten sonst Änderungen vornehmen, die von älteren Mastodon-Servern nicht verstanden und korrekt angezeigt werden.

Ich habe eine neue REST-API zum Erteilen einer Bearbeitung hinzugefügt. Die Medienanhänge, der Text, die Inhaltswarnung und die Umfrage können auf diese Weise geändert werden. Natürlich ist auch alles betroffen, was im Text enthalten ist, wie z. B. Erwähnungen oder Hashtags. Die Bearbeitung wird auf ähnliche Weise verarbeitet und gespeichert wie Bearbeitungsaktivitäten aus ActivityPub. Danach wird sie über ActivityPub überall dort verbreitet, von dem wir wissen, dass der ursprüngliche Beitrag dort gesehen wurde.

In der Web-App wird die Möglichkeit, einen Beitrag zu bearbeiten, über ein neues Dropdown-Menüelement für die eigenen Beiträge der Nutzenden verfügbar gemacht. Dasselbe Formular wie beim Erstellen neuer Beiträge wird wiederverwendet und mit den vorherigen Details gefüllt, wobei die Schaltfläche „Veröffentlichen“ durch die Schaltfläche „Änderungen speichern“ ersetzt wird.

### Einspruchsystem und andere Moderationswerkzeuge

Die Nutzenden sollen Mastodon mit ihrer Online-Präsenz vertrauen können. Daher braucht Mastodon bessere Moderationswerkzeuge, zur Verbesserung der Benutzer\*innensicherheit und zum Schutz der Nutzenden vor den Moderationswerkzeugen selbst, wenn diese versehentlich oder nachlässig angewendet werden.

Während Mastodon Moderator\*innen schon erlaubte, Beiträge von Nutzenden zu löschen (z. B. wenn Regeln gebrochen wurden), benachrichtigte diese Funktion den oder die Benutzer\*in in keiner Weise über die Aktion. Dies machte die Maßnahme ineffektiv bezüglich der Verhinderung zukünftiger Vergehen. Aus diesem Grund waren andere, viel härtere Moderationsfunktionen beliebter. In Fällen, in denen ein\*e Benutzer\*in zu Unrecht gesperrt wurde oder für die Aufhebung einer Sperrung zukünftig besseres Verhalten versprechen wollte, musste dies manuell über E-Mail-Kommunikation behandelt werden.

Gleichzeitig verlangte das ständig wachsende Spam-Problem auf Mastodon nach einfacheren und schnelleren Möglichkeiten, Spam-Konten zu bereinigen. Eine klare Kommunikation über Moderator\*innenentscheidungen und eine einfache Möglichkeit, gegen diese in ungerechten oder fehlerhaften Fällen Einspruch einzulegen, würden negative Auswirkungen für den Fall verringern, dass Moderator\*innen Konten im großen Stil sperren dürften.

![Die neue Meldungsansicht für Moderator*innen](/assets/images/project_images/mastodon/image5.png)

Zu diesem Zweck habe ich mehrere Änderungen an den gesamten Moderationswerkzeugen von Mastodon vorgenommen. Ich habe die Meldungsansicht in der Moderationsoberfläche von Grund auf neu gestaltet, um sicherzustellen, dass:

1. Die verfügbaren Handlungen für den oder die Moderator\*in klar sind,
2. Unterschiede zwischen legitimen und Spam-Konten offensichtlicher sind und
3. die Anzahl der Klicks, die erforderlich sind, um eine Handlung für die Meldung durchzuführen, reduziert wird.

Ich habe den Meldungen ein Kategoriensystem hinzugefügt, das über die generierte Kommunikation mit dem gemeldeten Konto verknüpft ist. Während der oder die meldende Nutzer\*in eine Kategorie wie „Spam“ oder „Es verstößt gegen Serverregeln“ auswählen und konkretisieren kann, gegen welche der Serverregeln vermeintlich verstoßen wurde, kann der oder die Moderator\*in dies leicht anpassen. Außerdem habe ich es Moderator\*innen ermöglicht, Beiträge zu Meldungen hinzuzufügen und zu entfernen, da die von den Benutzenden eingereichten Meldungen oft nicht ausführlich genug sind. Nachdem die entsprechenden Maßnahmen ergriffen wurden, wie z. B. das Löschen der anstößigen Beiträge, führt dies zu einer klaren Kommunikation mit dem gemeldeten Konto, wobei die genauen Gründe und genauen Posts aufgelistet werden, die zu der Entscheidung geführt haben.

![Die E-Mail, mit der die oder der Kontoinhaber*in informiert wird, dass anstößige Beiträge gelöscht worden sind](/assets/images/project_images/mastodon/image2.png)

Bisher führte die Auswahl der Kategorie einer Meldung zu einer anderen Seite, auf der angepasst werden musste, ob das gemeldete Konto eine E-Mail erhalten oder welcher benutzerdefinierte Text in die E-Mail aufgenommen werden sollte. Von nun an können alle Maßnahmen mit einem Klick und mit angemessenen Standardeinstellungen, wie z. B. ”immer eine E-Mail senden” ausgeführt werden. Da die ausgewählte Berichtskategorie in der E-Mail enthalten ist, ist das Verfassen individueller Textteile kaum mehr nötig. Gleichzeitig bleibt die Option zur Anpassung leicht zugänglich.

Ich habe die Möglichkeit für Moderierende entfernt, Benutzer\*innenbeiträge lautlos außerhalb von Meldungen zu löschen und stattdessen eine Verknüpfung zum Erstellen einer neuen Meldung direkt aus der Moderationsoberfläche eingesetzt, was meiner Meinung nach zu mehr Verantwortlichkeit führen wird.

Um Moderator\*innen bei der Ausführung von Strafmaßnahmen gegen Wiederholungstäter\*innen zu unterstützen (was das Entfernen von Posts wieder zu einer praktikablen Alternative zur Kontosperrung macht), wird jede Strafmaßnahme im System als eine Verwarnung erfasst und auf einen Blick angezeigt. Ein\*e Moderator\*in kann dann entscheiden, ob ein Konto mit drei Verwarnungen eine Sperrung verdient, anstatt nur einen Beitrag zu entfernen.

Jede Verwarnung kann auf der Webseite eingesehen werden und wird sowohl von der generierten E-Mail als auch von der Seite mit den Kontoeinstellungen der oder des Nutzenden verlinkt. Die Verwarnung zeigt nicht nur, was die E-Mail zeigt, sondern enthält auch ein Formular zum Einreichen eines Einspruchs. Der Einspruch kann nur einmal pro Verwarnung eingereicht werden. Moderierende können anhängige Einsprüche anzeigen und genehmigen oder ablehnen, wobei in jedem Fall das betreffende Konto über die Entscheidung informiert wird. Wenn man beispielsweise einen Einspruch gegen eine Verwarnung genehmigt, die ursprünglich zu einer Kontosperrung geführt hat, wird die Sperrung des Kontos damit automatisch aufgehoben.

![So sieht eine Verwarnung aus](/assets/images/project_images/mastodon/image8.png)

Ich habe eine Möglichkeit hinzugefügt, mehrere Konten gleichzeitig auszuwählen (z. B. wenn sie nach einem bestimmten IP-Bereich gefiltert werden) und alle auf einmal zu sperren. Dies erleichtert es Moderator\*innen, Spammer oder Bots loszuwerden. Um Administrator\*innen und Moderator\*innen zu helfen, besser zu sehen, was auf ihrem Mastodon-Server vor sich geht, habe ich die Dashboard-Seite neu gestaltet und ein Metriksystem hinzugefügt, das die Entwicklung von Zahlen im Laufe der Zeit anzeigt, sie mit früheren Zeiträumen vergleicht und Bindungskohorten berechnet.

![Die neue Dashboard-Seite für Moderatoren](/assets/images/project_images/mastodon/image7.png)

### iOS und Android-App

Da neue Benutzer\*innen in den offiziellen App-Stores für iOS und Android nach einer „Mastodon“-App suchen, ist es für Mastodon entscheidend, offizielle Apps bereitzustellen, die sich darauf konzentrieren, Nutzer\*innen einzugliedern. Zu Beginn der Förderperiode haben wir [bereits eine iOS-App veröffentlicht](https://apps.apple.com/us/app/mastodon-for-iphone/id1571998974), die jedoch noch nicht fertig war, ebenso mussten wir noch eine Android-Version entwickeln.

Während wir ein iPad-Layout für die iOS-App entwickelt haben und die Möglichkeit, sich bei mehreren Konten gleichzeitig anzumelden und zwischen ihnen zu wechseln, war die wichtigste Entwicklung die Arbeit an einer Entdeckungsseite, die die einfache Suchseite ersetzen würde. Es gab bei neuen Nutzer\*innen schon lange Probleme, dass diese keine Inhalte zum Ansehen fanden, es sei denn, sie wurden von jemand anderem manuell angeleitet. Die Entdeckungsseite hat das Potenzial, dieses Problem zu lösen.

![Von links nach rechts: neue Entdeckungsseite, Meldungsdialog und Dialog zum Wechseln zwischen Konten in der iOS-App](/assets/images/project_images/mastodon/image4.png)

Die Entdeckungsseite erforderte das Hinzufügen mehrerer neuer APIs. Ich habe das Trending-Hashtag-System erweitert, um öffentliche Beiträge und Zeitungsartikel zu verfolgen, die oft geteilt werden. Ich habe das Trending-Hashtag-System selbst mit einer übersichtlichen Benutzeroberfläche und einer neuen Datenstruktur verbessert, die nicht durch auf Überprüfung wartende Elemente verstopft wird. Ich habe die Fähigkeit von Mastodon verbessert, genaue Previews für Zeitungsartikel durch OpenGraph- und JSON-LD-Daten zu generieren, die in Beiträgen verlinkt sind.

Sowohl Trending-Beiträge als auch Trending-Zeitungsartikel werden nach dem Trending-Hashtag-Modell durch A-priori-Moderation gesichert, wobei Moderator\*innen regelmäßig über zu überprüfende Beiträge und Zeitungsartikel informiert werden. Um den erforderlichen Arbeitsaufwand zu minimieren, können Moderierende Zeitungsquellen und Beitragsautor\*innen zulassen oder verbieten, aber es gibt auch eine Möglichkeit, einzelne Elemente zuzulassen oder zu verbieten.

Ich habe die Lokalisierung sowohl für Trending-Beiträge als auch für Trending-Zeitungsartikel hinzugefügt, damit Menschen Ergebnisse in ihrer Muttersprache erhalten, und die Qualität der lokalisierten Folge-Empfehlungen für neue Nutzende während der Eingliederung verbessert.

![Neue Entdeckungsseite in der Web-App](/assets/images/project_images/mastodon/image3.png)

Um die neuen APIs optimal zu nutzen, habe ich daran gearbeitet, auch der Web-App eine Entdeckungsseite hinzuzufügen. Dort dient diese Seite ebenfalls als überarbeitete Suchseite.

Nach dem Hinzufügen von Kategorien (oder Gründen) zu Meldungen im Moderationssystem wird der Meldungsdialog in der iOS-App angepasst, sodass Benutzer\*innen auswählen können, warum sie den Beitrag oder das Konto melden und gegen welche Regeln sie ihrer Meinung nach verstoßen. Das mache ich auch in der Web-App.

![Von links nach rechts: Anmeldungsdialog, Formular zum Erstellen eines neuen Beitrags und Profilseite in der Android-App](/assets/images/project_images/mastodon/image6.png)

Die Arbeit an der Android-App [hat begonnen](https://blog.joinmastodon.org/2022/02/official-mastodon-for-android-app-is-coming-soon/).

### Vereinheitlichung von Benutzer\*innenoberflächen

Mastodon hat zwei Benutzer\*innenoberflächen, eine Single-Page-App für eingeloggte Benutzer (die „Web-App“) und öffentliche Seiten für öffentliche Ressourcen wie Beiträge und Profile ("Permalinks"). Der Unterschied zwischen diesen Oberflächen ist selbst für erfahrene Benutzer\*innen verwirrend. Obwohl sie eine ähnliche Designsprache verwenden, sind die Verhaltensweisen (z. B. wo sie klicken können, um etwas zu tun, und was man dort tun kann) zwischen den Oberflächen anders.

Ursprünglich war geplant, diese Oberflächen zu vereinheitlichen, indem die Single-Page-App auf allen öffentlichen Ressourcen gemountet und an den abgemeldeten Zugriff angepasst wird, indem Funktionen, die eine Benutzer\*innenauthentifizierung erfordern, selektiv deaktiviert werden. Allerdings reichte der Zeitraum nicht aus dies zu beenden, da andere Ziele eine höhere Priorität hatten. Jedoch habe ich einen Schritt in Richtung Erreichung dieses Ziels gemacht: Die Single-Page-App verwendet nun eine ähnliche URL-Pfadstruktur wie Permalinks, wenn auch vorerst mit „web“ vorangestellt.

### Fazit

Diese neuen Funktionen werden in Kürze in Version 3.5 von Mastodon verfügbar sein. Es ist eine Weile her seit unserer letzten großen Veröffentlichung und ich freue mich, unserer Community so viele wichtige Verbesserungen zeigen zu können. Die Android-App befindet sich noch in einem frühen Entwicklungsstadium, aber Ende des Monats wird ein Beta-Testprogramm beginnen.

Ich möchte dem BMBF, dem DLR, Marie und Patricia vom Prototype Fund und meinen KollegInnen Felix und Claire danken, die mir auf diesem Weg geholfen und dies ermöglicht haben.
