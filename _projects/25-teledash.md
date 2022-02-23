---
layout: project
title: "Teledash – Recherche- und Analyse-Software für Telegram"
image: /assets/images/project_images/teledash/header.png
authors:
  - author: Grischa Stanjek
    link: https://twitter.com/grischka
  - author: Gregor Weichbrodt
    link: https://twitter.com/greg00r
brief: "Wir wollen öffentliche Inhalte auf Telegram erheben und auswerten."
summary: "Die Webanwendung *Teledash* ist eine Recherche- und Analyse-Software und vereinfacht die Untersuchung der Inhalte auf Telegram."
---

## Teledash – Recherche- und Analyse-Software für Telegram

Telegram ist insbesondere bei Rechtsextremen und Verschwörungsideologen beliebt. Vor allem seit der Corona-Pandemie verzeichnen einschlägige Kanäle und Gruppen einen Anstieg an Nutzer\*innenzahlen. Einzelne Akteur\*innen erreichen dort mit geringem technischen Aufwand hunderttausende Nutzer\*innen und tragen so zur Normalisierung von Antisemitismus und verschwörungsideologischem Denken bei. Falschinformationen zum Coronavirus sowie rechtsextreme und antisemitische Inhalte werden nahezu uneingeschränkt in deutschsprachigen öffentlich zugänglichen Telegram-Gruppen geteilt. Die Mobilisierung gegen die Corona-Maßnahmen der Bundesregierung fand im vergangenen Jahr vor allem über Telegram statt.

Eine systematische Untersuchung der Inhalte auf Telegram ist jedoch schwer. Trotz seiner Popularität gibt es für Telegram bis dato kaum frei verfügbare Werkzeuge, die eine quantitative und qualitative Untersuchung zulassen. Journalist\*innen und Wissenschaftler\*innen konnten dies nur mit hohem technischen Aufwand bewältigen oder waren auf teure Software angewiesen, die für Marketing-Zwecke erschaffen wurde.

Die Webanwendung [_Teledash_](https://github.com/democ-de/teledash) vereinfacht eine Untersuchung der Inhalte auf Telegram. Sie soll im Folgenden vorgestellt werden.

![](/assets/images/project_images/teledash/1-start.gif)

## Funktionen

Ein oder mehrere Telegram-Accounts können mit Teledash verknüpft werden. Anschließend werden die Inhalte in regelmäßigen Abständen heruntergeladen und verarbeitet. Die wichtigsten Funktionen in der Übersicht:

### Suchen

Mithilfe eines Web-Interface lassen sich übergreifend alle Kanäle, Gruppen und Chats durchsuchen. Möchte man die Suche einschränken, kann man mit verschiedenen Parametern die Suche feinjustieren. Hier können bspw. Nachrichten aus einem bestimmten Zeitraum in bestimmten Kanälen gesucht werden. Oder Nachrichten von bestimmten Telegram-Nutzer\*innen.

![](/assets/images/project_images/teledash/2-nachrichten-filter.gif)

### Text- und Spracherkennung

Mittels automatisierter Texterkennung wird Text auf Bildern erkannt und gespeichert. Darüber hinaus werden Sprachnachrichten automatisiert im Hintergrund transkribiert und als durchsuchbarer Text gespeichert. So werden Inhalte aus Medien durchsuchbar, die ursprünglich nicht in Textform vorlagen. Die Qualität der Ergebnisse hängt stark von der Qualität der Audioaufnahme sowie des verwendeten Sprachmodells ab. Models für Text- sowie Spracherkennung können ggf. manuell nachgebessert bzw. trainiert werden.

### Metriken

Teledash erhebt regelmäßig statistische Daten zur Aktivität und zum Wachstum von Kanälen und Gruppen, wodurch quantitative Analysen ermöglicht werden. So lassen sich beispielsweise Trends frühzeitig erkennen und der Zuwachs von Nutzer\*innen im Verlauf der Zeit abbilden.

![](/assets/images/project_images/teledash/3-chats-filter.gif)

### Storage

Medien wie Videos, Fotos und Sprachnachrichten können automatisiert heruntergeladen und in einer MinIO-Instanz oder in einem S3-kompatiblen Cloud-Storage abgelegt werden. Das Web-Interface zeigt alle Medien als Vorschau an und stellt diese für den Download bereit.

### Export

Alle von Teledash erhobenen Daten sind auch über eine Programmierschnittstelle (API) abrufbar. Die API-Endpunkte sind mit verschiedenen Parametern ausgestattet, mit denen alle Inhalte gefiltert ausgegeben werden können. Die REST-API eignet sich z. B. für eine Weiterverarbeitung der Inhalte durch Software Dritter. Alle API-Endpunkte können im Browser mittels Swagger getestet werden. Die von der Datenbank mitgelieferte Konsolen-Anwendung _mongoexport_ ermöglicht wahlweise den Export kompletter Datensätze als CSV oder JSON.

![](/assets/images/project_images/teledash/4-swagger.gif)

### Ausblick

Teledash soll in den kommenden Monaten weiterentwickelt und in journalistischen und wissenschaftlichen Kontexten erprobt werden.

**Github**

[teledash](https://github.com/democ-de/teledash)

**Kontakt**  

- Gregor Weichbrodt ([@greg00r](https://twitter.com/greg00r))
- Grischa Stanjek ([@grischka](https://twitter.com/grischka))
- [teledash@democ.de](mailto:teledash@democ.de)

Wir danken dem BMBF für die Förderung sowie dem DLR für die Unterstützung.
