---
layout: project
title: "PoliTrack"
image: /assets/images/project_images/politrack/header.png
authors:
  - author: Michael Perk
    link: https://twitter.com/perkmi
  - author: Jonas Dippel
    link: https://twitter.com/jdppel
brief: "Wir machen Informationen über Politiker\\*innen zugänglich und durchsuchbar."
summary: "Unsere KI liest alle politische Nachrichtenartikel von den größten Medien aus Deutschland und generiert daraus spannende Statistiken und Einblicke."
---

Einer der Grundpfeiler der Demokratie sind unabhängige Medien, die kritisch über die politische Lage im Land berichten. In Zeiten von Online-Journalismus und Livetickern zu aktuellen Geschehnissen vergisst man leicht, dass sich die Entscheidung bei einer Wahl auch an bereits vergangenen Entscheidungen und Meinungen orientieren sollte. Möchte man über eine\*n Bundestagsabgeordneten eines Landkreises mehr erfahren, kann man eine Onlinesuche machen, sich Interviews ansehen und auf Wahlkampfveranstaltungen gehen. All diese Möglichkeiten haben einen großen Makel: Es fehlt die zeitliche Dimension. Mehr noch ist es als Bürger\*in unglaublich schwer, bei aktuellen Berichten auf dem Laufenden zu bleiben. Sobald einzelne Themen durch die Nachrichten in den Vordergrund geraten sind, bekommen sie für einige Tage oder Wochen volle Aufmerksamkeit. Im Anschluss geraten sie dann wieder schnell in Vergessenheit.
Für politische Partizipation und eine gute Wahlentscheidung ist es jedoch wichtig, möglichst gut informiert über die Positionen einzelner Politiker\*innen zu sein.
Bei der Internetrecherche zu Politiker\*innen erscheinen nur aktuelle Themen. Um auch historische Daten einzubeziehen, muss ein enormer Aufwand betrieben werden, den nur die wenigsten in Kauf nehmen möchten. Gerade über Politiker\*innen, die selten in Medien erwähnt werden, ist es sehr schwierig, fundierte Informationen zu bekommen.
Um die Meinungsbildung zu erleichtern, wollen wir Nachrichtenartikel besser ordnen und zugänglich machen. Dazu indizieren wir regelmäßig alle politische Nachrichtenartikel von den größten Medien aus Deutschland. Insgesamt haben wir bereits über eine halbe Million Artikel gesammelt.

![](/assets/images/project_images/politrack/articles_over_time.png)
![](/assets/images/project_images/politrack/article_distribution.png)

## Politiker\*innen-Profile

Diese Menge an Artikeln erlaubt es uns einige interessante Auswertungen zu machen. Wir speichern zu jedem Nachrichtenartikel, welche Politiker\*innen in dem jeweiligen Artikel vorkommen. Basierend auf diesen Information erstellen wir für jede\*n Politiker\*in ein Profil.

![Suche nach Politiker*innen](/assets/images/project_images/politrack/search.gif)

![Die Profil-Seite eines/einer Politiker*in.](/assets/images/project_images/politrack/profile.png "Title")

Dieses beinhaltet grundlegende Attribute, wie Parteizugehörigkeit, aktuelle Position und weiterführende Links. Zudem berechnen wir, mit welchen Personen die oder der jeweilige Politiker\*in am meisten in einem Artikel vorkommt. Natürlich zeigen wir ebenfalls aktuelle Artikel an, in denen der oder die Politiker\*in erwähnt wird.
Politiker\*innen werden oft an ihren Meinungen und Äußerungen zu bestimmten Themen gemessen. Um die Informationen über Aussagen und Positionen schneller zugänglich zu machen, extrahieren wir automatisch Zitate aus den einzelnen Artikeln und ordnen sie den jeweiligen Politiker\*innen zu. Damit ermöglichen wir einen direkten Überblick, über alle ihrer Aussagen in den Medien. Leider gelingt die Extraktion der Zitate nicht immer fehlerfrei. Manchmal werden bestimmte Zitate einer falschen Person zugeordnet. Darauf weisen wir die Nutzenden explizit hin. Neben den Zitaten liefern wir außerdem eine Quelle, in der die Aussage im Zweifelsfall validiert werden kann. Natürlich arbeiten wir weiter daran, die Extraktion der Zitate zu verbessern.

![Zitate einzelner Politiker*innen werden automatisch von uns extrahiert.](/assets/images/project_images/politrack/quotes.png)

Durch den Einsatz von Machine-Learning-Techniken, den sogenannten Transformer Modellen, können wir weitere Informationen über die Themen extrahieren, mit denen sich bestimmte Politiker\*innen beschäftigen.
Transformer Modelle sind in der KI-Forschung das State-of-the-Art Werkzeug, um dem Computer zu ermöglichen Sprache/Text zu verstehen. Dabei wird der zu analysierende Text zunächst in eine Repräsentation der im Text vorkommenden Themen und Inhalte überführt.
Auf Basis dieser Repräsentation können im Anschluss Funktionen wie Themenextraktion oder eine Ähnlichkeitssuche stattfinden.
Durch diese grobe Kategorisierung der Artikel, können wir dann eine Übersicht geben, mit welchen politischen Themen sich eine Person am meisten beschäftigt. Zu diesen Kategorien gehören zum Beispiel “Soziales”, “Außenpolitik”, “Gesundheit” oder “Klimaschutz”. So bekommen Nutzende einen schnellen Überblick über den Themenfokus eines Politikers.

![Erwähnungen eines/einer Politiker*in in Artikeln über die Zeit am Beispiel von Olaf Scholz.](/assets/images/project_images/politrack/articles_trend.png)

Zur Zeit zeigen wir nur aktuelle Artikel und Aussagen von Politiker\*innen an. Jedoch wollen wir in Zukunft auch historische Aussagen und Zitate themenbasiert geordnet anzeigen. Dazu arbeiten wir aktuell noch an einem intuitiven Interface, dass es den Benutzer\*innen ermöglicht historische Daten übersichtlich durchsuchen zu können. Derzeit gibt es schon unten auf der Seite eine Übersicht, wann die Präsenz einzelner Politiker\*innen in den Medien besonders hoch war und aus welchen Medien die Artikel stammen. Ein hohes Aufkommen einer Person in den Medien korreliert meist mit einem besonderen politischen Ereignis, wie zum Beispiel einer Wahl.

## Dashboard

Wir geben aber nicht nur eine spezifische Übersicht über Politiker\*innen, sondern auch über das aktuelle Tagesgeschehen in den Politik-Nachrichten. Auf der Dashboard-Seite (www.politrack.org/#/dashboard) zeigen wir die “Schlagzeilen des Tages”. Dabei gruppieren wir einzelne Schlagzeilen thematisch und verweisen auf die Artikel zu dem jeweiligen Thema. Dadurch kann man sich eine umfangreichere Meinung über ein Thema bilden und die Berichte von verschiedenen Herausgebern auf einen Blick vergleichen.

![Die Politik-Schlagzeilen des Tages.](/assets/images/project_images/politrack/headlines.png)

Wir klassifizieren basierend auf den Schlagworten des Artikels, ob ein Artikel eine bestimmte Partei behandelt. Damit lässt sich berechnen, welche Parteien besonders im Fokus der Medien sind. Zudem zeigen wir auch, welche Politiker\*innen einer Partei besonders viel in den Medien vorkommen und identifizieren Newcomer, die im Vergleich zu früheren Monaten nun besonders oft in Artikeln erscheinen.

![Statistiken zu einzelnen Parteien, prominenten Politiker*innen und Newcomern.](/assets/images/project_images/politrack/party-statistics.png)

## Bundestagswahl 2021

Wie hat die SPD es geschafft die Bundestagswahl für sich zu entscheiden? Wie kam es zum Absturz der CDU/CSU? Diese Fragen haben wir uns gestellt und können sie teilweise mit unseren Daten beantworten. Im Zuge der Bundestagswahl haben wir eine Themenübersicht geschaffen, die Berichte über politische Ereignisse mit den Umfragewerten der jeweiligen Parteien verknüpft. Dazu haben wir alle politischen Nachrichtenartikel von 2019-2021 thematisch verknüpft und dann prominente Ereignisse identifiziert. Zu diesen Ereignissen haben wir dann die Zeitspanne gewählt, an denen das Thema am meisten in den Medien behandelt wurde. Daraus entstand eine interaktive Übersicht, in der diese Ereignisse mit den Umfragewerten zeitlich verknüpft sind. Diese Übersicht findet ihr auf politrack.org/#/btw. Mit etwas zusätzlicher Arbeit können ähnliche Auswertungen auch für zukünftige Wahlen durchgeführt werden.

![Übersicht zur Bundestagswahl 2021.](/assets/images/project_images/politrack/btw.png)

##Warum PoliTrack?

Wir sind zwei Informatiker aus Berlin und Braunschweig und haben im letzten Jahr mit einem größeren Team an einem anderen Data-Science-Projekt gearbeitet. Mit “Collabovid” haben wir mehr als 20.000 Wissenschaftler\*innen aus der ganzen Welt dabei geholfen, Publikationen über das Coronavirus SARS-CoV-2 besser durchsuchbar zu machen. Uns war klar, dass man die Techniken zur Textanalyse, die wir im Zuge des Projektes gelernt haben, auch auf andere Bereiche übertragen kann. Da wir beide großes Interesse an der deutschen Politik haben, kam uns die Idee, diese Methoden auch in diesem Gebiet einzusetzen. Besonders vor der Bundestagswahl haben wir festgestellt, dass man sich viel zu wenig mit den wichtigen Themen und den einzelnen Kandidat\*innen auseinandergesetzt hat.
Wir beobachten, dass es manchen deutschen Medien mehr um Schlagzeilen geht als um unabhängige Berichterstattung. Diesen Trend halten wir für problematisch. Wir hoffen, mit unserem Projekt den Bürger\*innen viele unterschiedliche Perspektiven zu einem Thema geben zu können. Damit soll die Transparenz in unserer Demokratie verbessert und eine objektivere Meinungsbildung gefördert werden.

## Kooperationen

Andere Projekte wie [Face the Facts](https://facethefacts.app/) und [abgeordnetenwatch.de](https://www.abgeordnetenwatch.de/) haben auch das Ziel für mehr Transparenz in der Politik zu sorgen. Derzeit kooperieren wir bereits mit “Face the Facts” und stellen ihnen unsere aggregierten Daten mittels einer Schnittstelle zur Verfügung.

## 4x Danke und eine Bitte

Abschließend danken wir dem BMBF und dem DLR für die Möglichkeit dieses Projekt umsetzen zu können, sowie dem Prototype Fund für die tolle Organisation und Unterstützung. Vielen Dank auch an David von Zero360 für deine Anregungen und Hilfe.

Wir planen unsere API weiter auszubauen, sodass auch Journalist\*en unsere Daten für ihre Recherchen nutzen können. Ebenso können wir für Journalisten eine thematische Suche anbieten, um Hintergrundrecherchen in Zukunft zu vereinfachen. Mittels der Artikeldaten wollen wir außerdem noch weitere spannende Auswertungen machen und die Seite damit ergänzen. Falls ihr Ideen habt, welche Metriken zur politischen Berichterstattung noch besonders interessant wären oder als Journalist\*in an unseren Daten interessiert seid, schreibt uns bitte eine Nachricht! :)
