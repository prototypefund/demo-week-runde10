---
layout: project
title: "OpenSanctions"
image: /assets/images/project_images/open-sanctions/header.png
authors:
  - author: Friedrich Lindenberg
    link: https://opensanctions.org
brief: "Wir zeigen, welche Firmen und Personen von internationalen Sanktionen betroffen sind."
summary: "OpenSanctions ist eine Ressource für Journalist\\*innen, Aktivist\\*innen und Finanzdienstleister. Das Projekt sammelt Profile über Personen und Firmen, denen ein besonderes öffentliches Interesse gilt."
---

## Was ist OpenSanctions?

OpenSanctions ist eine Ressource für Journalist\*innen, Aktivist\*innen und Finanzdienstleister. Das Projekt sammelt Profile über Personen und Firmen, die Ziel internationaler Sanktionen sind. Hinzu kommen Einträge zu Personen, die aufgrund von kriminellem Verhalten oder als politische Mandatsträger\*innen (sog. PEPs) ins öffentliche Interesse gerückt sind.

Solche Profile sind ein wichtiges Werkzeug, um in großen Datenmengen systematisch Hinweise auf Interessenkonflikte, Korruption und Geldwäsche zu finden. Zudem stellen Sanktionen eine Art quantifizierte Geopolitik dar: Sie dokumentieren in ungewöhnlicher Klarheit, welche außenpolitischen Ziele unterschiedliche Staaten verfolgen.

Weil die Daten jedoch nicht leicht auffindbar sind, ist ihre Nutzung bisher technisch aufwändig. Konsolidierte Datenbanken, die von Firmen wie Dow Jones oder Refinitiv angeboten werden, sind für Journalist\*innen und Aktivist\*innen unerschwinglich. OpenSanctions macht diese Quellen für sie deshalb einfach, gratis und strukturiert nutzbar.

![OpenSanctions home page](/assets/images/project_images/open-sanctions/header.png)

## Gerd, wie baut man eine Pipeline?

Sanktionsdaten werden in der Regel von Regierungsbeamt\*innen in veraltete Computersysteme getippt, die diese dann auf einer Website bereitstellen (oft als XML oder JSON, manchmal aber auch als PDF oder Excel-Datei). Dabei entstehen natürlich (sowohl durch die Beamt\*innen wie auch durch die Systeme) verschiedene Probleme: Wie buchstabiert man etwa einen arabischen Namen im lateinischen Alphabet? Oder einen russischen Namen auf Hebräisch? Welche Länder gibt es? In welchem Land befindet sich ein\*e Einwohner\*in der Stadt Sevastopol? Wie formatiert man eine Telefonnummer oder Hausadresse? Mit welcher Identifikationsnummer beschreibt man eine Firma oder Person am besten?

![Schritte der Datenpipeline](/assets/images/project_images/open-sanctions/os-pipeline.png)

Ein wesentlicher Teil der Arbeit an OpenSanctions besteht darin, die unterschiedlichen Quellformate in eine neue, kohärente Datenstruktur zu überführen. Der Ansatz ist, alle Bereinigungen vollständig reproduzierbar und transparent zu machen. Um die Verarbeitung transparent zu machen, wird der ganze Prozess öffentlich einsehbar bei GitHub Actions ausgeführt, und alle entstehenden Fehlermeldungen oder Warnungen werden auf der OpenSanctions-Webseite in der Beschreibung des Datensatzes veröffentlicht.

Eine hilfreiche Komponente für die Reproduzierbarkeit waren [Normalisierungstabellen](https://github.com/opensanctions/opensanctions/blob/main/opensanctions/static/common.yml), die Ländercodes, Adressen oder Zeitangaben vereinheitlichen. Für deren systematische Anwendung habe ich die Python-Bibliothek [datapatch](https://pypi.org/project/datapatch/) veröffentlicht.

Neben der strukturellen Angleichung der Daten gab es noch ein zweites, komplexes Problem zu lösen: Die verschiedenen Datenquellen - vor allem die Sanktionslisten verschiedener Staaten - enthalten immer wieder die gleichen Personen und Organisationen. Zum ehemaligen irakischen Präsidenten [Saddam Hussein](https://www.opensanctions.org/entities/Q1316/), zum Beispiel, kennt das System Einträge aus 13 Quellen. Stattdessen sollte eine konsolidierte Ansicht angeboten werden. Dazu habe ich die Python-Bibliothek [nomenklatura](https://github.com/opensanctions/nomenklatura) weiterentwickelt, die mögliche Duplikate erkennt und auch verschmelzen kann.

![nomenklatura-Benutzeroberfläche für Deduplikation](/assets/images/project_images/open-sanctions/matching2.png)

Um eine hohe Qualität des Datensatzes sicherzustellen, wurde ein manueller Prüfungsschritt eingeführt, mit dem die Richtigkeit des Matches durch einen Menschen bestätigt wird. Zur Duplikationsstrategie gibt es auch einen [detaillierten Blogpost](https://www.opensanctions.org/articles/2021-11-11-deduplication/).

## Die Daten nutzbar machen

Schon zum Projektstart ging eine einfache Webseite online, auf der Anwender\*innen die [produzierten Datensätze](https://www.opensanctions.org/datasets/) in verschiedenen Formaten herunterladen konnten. Im Verlauf des Projekts kam dann noch eine umfangreiche [Dokumentation der verwendeten Datenstruktur](https://www.opensanctions.org/docs/usage/) und der Methodik hinzu. Aktuelle Entwicklungen wurden [in einem Blog](https://www.opensanctions.org/articles/) dokumentiert.

Bedauernswerterweise ist das Feedback der Nutzer\*innen zu den bereitgestellten Dateiformaten bisher spärlich gewesen: Zwar wurden einige spezifische Erweiterungen vorgeschlagen, aber ich hatte zu dem Thema auf mehr Dialog gehofft.

Entgegen der ursprünglichen Pläne habe ich mich schließlich dazu entschlossen, die Daten auch inhaltlich auf der Webseite zugänglich zu machen. Um eine [Suchfunktion](https://opensanctions.org/search/) und die [Darstellung einzelner Einträge](https://www.opensanctions.org/entities/Q20850503/) zu ermöglichen, habe ich einen [alleinstehenden API-Server](https://www.opensanctions.org/docs/api/) entwickelt, der die OpenSanctions-Daten in ElasticSearch durchsuchbar macht.

![OpenRefine zeigt OpenSanctions-Matches an](/assets/images/project_images/open-sanctions/score-filter.png)

Mithilfe einer Implementation der [OpenRefine Reconciliation API](https://docs.openrefine.org/technical-reference/reconciliation-api) kann dieser etwa Journalist\*innen auch dabei helfen, [einen ganze Liste von Firmen oder Personen auf relevante Einträge zu überprüfen](https://www.opensanctions.org/articles/2022-01-10-openrefine-reconciliation/).

Dazu kommt eine Matching-API, mit der etwa Firmen ihren [eigenen Kundenstamm mit der Datenbank abgleichen können](https://www.opensanctions.org/articles/2022-02-01-matching-api/). Damit solche Kundendaten nicht in die Projekt-Infrastruktur wandern müssen, ist der API-Server als Docker-Image abgepackt. Das kann einfach auf dem Server der Anwender\*innen installiert werden und holt sich jede Stunde aktuelle Daten von OpenSanctions ab.

Weil die Qualität des Matchers für die kommerzielle Nutzung von OpenSanctions von großer Bedeutung ist, will ich die erzeugten Scores in Zukunft durch ein Regressionsmodell generieren, das die manuell vorgenommenen Deduplikations-Entscheidungen als Trainingssatz nutzt. Das Modell [produziert bisher gute Erkennungswerte](https://github.com/opensanctions/nomenklatura/pull/60), soll aber noch weiter geprüft werden, bevor es in den Produktiveinsatz übergehen kann.

Ein nettes Extra der Webseite ist die [Rohdatenansicht](https://www.opensanctions.org/statements/?canonical_id=Q20850503&prop=name) mit der Anwender\*innen genau nachvollziehen können, aus welcher Quelle welches Attribut eines Eintrags stammt.

Über den Projektzeitraum haben etwa 40.000 Menschen die Webseite besucht - davon etwa 10.000 im letzten Monat. Es ist also ein wachsendes Interesse zu beobachten.

## Mehr Quellen!

Im Laufe des Projekts habe ich die Anzahl der verwendeten Datenquellen langsam erhöht. Neben den zunächst enthaltenen Sanktionslisten aus Amerika, [Europa](https://www.opensanctions.org/datasets/eu_fsf/), [Schweiz](https://www.opensanctions.org/datasets/ch_seco_sanctions/), [Ukraine](https://www.opensanctions.org/datasets/ua_sfms_blacklist/), [Kanada](https://www.opensanctions.org/datasets/ca_dfatd_sema_sanctions/), [Großbritannien](https://www.opensanctions.org/datasets/gb_hmt_sanctions/), [Frankreich](https://www.opensanctions.org/datasets/fr_tresor_gels_avoir/) und [den UN](https://www.opensanctions.org/datasets/un_sc_sanctions/) konnten wir zusätzliche Quellen aus [Argentinien](https://www.opensanctions.org/datasets/ar_repet/), [Australien](https://www.opensanctions.org/datasets/au_dfat_sanctions/), [Israel](https://www.opensanctions.org/datasets/il_mod_terrorists/), [Japan](https://www.opensanctions.org/datasets/jp_mof_sanctions/), [Kyrgyzstan](https://www.opensanctions.org/datasets/kg_fiu_national/), [Kazakhstan](https://www.opensanctions.org/datasets/kz_afmrk_sanctions/), [Russland](https://www.opensanctions.org/datasets/ru_fedsfm_terror/) und [Südafrika](https://www.opensanctions.org/datasets/za_fic_sanctions/) erschließen. Daneben haben wir einige thematisch verwandte Listen, etwa die [Vergabevertrag-Verbotslisten](https://www.opensanctions.org/datasets/debarment/) aller internationalen Entwicklungsbanken und eine [Liste von Blockchain-Konten](https://www.opensanctions.org/datasets/ransomwhere/), die im Zusammenhang mit Finanzkriminalität stehen, eingebunden.

![Wachstum der Entitäten in OpenSanctions](/assets/images/project_images/open-sanctions/entities-growth.png)

Den größten Datenzuwachs hat das Projekt allerdings nicht durch zusätzliche Sanktionslisten erfahren, sondern in einem verwandten Themenfeld: [Informationen über Politiker\*innen](https://www.opensanctions.org/datasets/peps/). Deren Profile sind aus ähnlichen Gründen relevant, die auch für Sanktionen gelten: Taucht ein\*e Politiker\*in (oder engsten Mitstreiter\*innen) etwa in einem Leak auf, dann ist das häufig der Anlass für eine journalistische Recherche.

Doch ein systematisches Verzeichnis aller Politiker\*innen gibt es nicht. Jede Nation der Welt hat andere Institutionen, die nicht immer Webseiten haben, und auf diesen Webseiten dann auch nicht immer preisgeben, wer denn aktuell Finanzminister\*in sei.

Ich habe deshalb Kontakt mit dem Gründer des Projekts [EveryPolitician.org](http://everypolitician.org/) aufgenommen, das ab 2015 Abgeordnete in aller Welt erfasste. Obwohl das Projekt mittlerweile inaktiv ist, hat er letztes Jahr angefangen, neue Scraper zu entwickeln, die zunächst [alle Kabinette der Welt erschließen](https://www.opensanctions.org/articles/2022-01-18-peppercat/) und in Wikidata eintragen sollen.

Weil unsere Projekte eine sehr ähnliche Zielsetzung haben, haben wir beschlossen, gemeinsam an der Integration aller in Wikidata erfassten Politiker\*innen in OpenSanctions zu arbeiten. So konnten bislang beinahe 80.000 relevante Personen aus über 250 Territorien identifiziert werden.

## Nachhaltigkeit

Mir war von Anfang an wichtig, zumindest die Instandhaltung des Projektes über den Förderzeitraum hinaus finanziell zu untermauern. Deshalb rief die erste Version der Webseite Firmen dazu auf, sich durch ein Sponsoring am Weiterbetrieb zu beteiligen. Nach halber Projektlaufzeit hatte das jedoch nur zu sehr begrenzter Resonanz geführt.

Deshalb habe ich im Dezember die [Lizenzierung des Datensatzes von CC-BY auf CC-BY-NonCommercial geändert](https://www.opensanctions.org/articles/2021-12-10-sustainability/), mit besonderen Ausnahmeregeln für Medienunternehmen. Das führte zu einer Gruppe von Firmen, die sich bereit erklärten, zur Nutzung der Daten eine monatliche Nutzungsgebühr zu entrichten. OpenSanctions befindet sich damit auf einem plausiblen Weg zur finanziellen Nachhaltigkeit.

## Wie es weitergeht

Fertig ist natürlich nichts. Neben einer schier unendlichen Liste an Datenquellen, die ich gerne einbinden würde, gibt es auch noch eine Reihe anderer Projekte, die vermutlich erst nach der Förderphase zum Zug kommen werden:

- Zum einen ist da die Anreicherung von Sanktionsdaten mit Fakten aus anderen, inhaltlich verwandten, Datenbanken. Dazu gehören neben [Wikidata](https://www.wikidata.org/) zum Beispiel die [OffshoreLeaks-Datenbank](https://offshoreleaks.icij.org/) von ICIJ, oder sogenannte [Beneficial Ownership](https://www.openownership.org/)-Datenbanken in denen die Eigentümer\*innen von Firmen dokumentiert sind. Die bestehende Infrastruktur zur De-Duplikation wird hier eine Rolle spielen, muss jedoch Matching-Kandidaten via Netzwerk beschaffen.
- Umgekehrt wollte ich auch gerne die Eintragung aller Sanktionsziele als Items in Wikidata in Angriff nehmen. Für die zentralen Akteur\*innen gibt es natürlich bereits Einträge, aber hier eine Vollständigkeit zu erzielen, ist ein Ziel für die Zukunft.
- Schließlich bleibt auch die politische Analyse der Sanktionsdaten unerledigt. Was können uns Sanktionziele über die Außenpolitik verschiedener Staaten verraten? Etwa über die amerikanische Fokussierung auf iranische Nonproliferation, oder die europäischen Experimente in der Bestrafung des mörderischen Lukashenko-Regimes?

## Fazit

Prototype Fund macht Spaß. Ich habe selten in meiner Arbeitszeit die Chance gehabt, so selbstbestimmt an einem Projekt zu arbeiten. Was ich besonders genossen habe: Das Sammeln der Sanktionsdaten an sich ist ein relativ überschaubares Problem, so dass wir im Projektzeitraum die Chance hatten, einige Teilaspekte besonders vertieft anzugehen und dennoch ein recht abgerundetes Produkt vorzulegen.

Ein großer Dank gilt dem Bundesministerium für Bildung und Forschung und dem Deutschen Zentrum für Luft- und Raumfahrt, die dieses Projekt erst ermöglicht haben. Und zuletzt natürlich an den Prototype Fund, der durch seine tolle Betreuung ein wundervolles Arbeitsumfeld geschaffen hat.
