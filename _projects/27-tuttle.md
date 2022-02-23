---
layout: project
title: "Tuttle"
image: /assets/images/project_images/tuttle/header.png
authors:
  - author: Christian Staudt
    link: https://clstaudt.me
brief: "Wir bauen ein Businessplanungstool für Freelancer\\*innen und Solo-Selbständige."
summary: ""
---

## Motivation und Projektziel

Die Arbeitswelt ist im Wandel, der Trend geht zum Freelancing: Softwareentwickler\*innen, Designer\*innen oder Journalist\*innen schätzen die Freiheiten und Gestaltungsmöglichkeiten der Solo-Selbständigkeit. Immer mehr Profis wählen sie für sich als die "artgerechte" Form des Arbeitens. Sie erlaubt es ihnen, sich zu spezialisieren und mit vielen Projekten und Kund\*innen Erfahrung zu sammeln. Freelancer\*innen spielen dadurch eine besondere Rolle - für kreative Ideen, unabhängige Beratung, innovativen Wissenstransfer und eine vielfältige Medienlandschaft.

Beim Freelancing gibt es viele Nebentätigkeiten: Vermarktung, Kundenkommunikation, Rechtliches, und vor allem Zeit- und Finanzplanung - wohl nicht das, was am Freelancen am meisten reizt. Vernachlässigte Planung birgt aber das Risiko von Insolvenz, Verschuldung, prekärer Selbständigkeit, oder Altersarmut. Was aber, wenn Software die Finanzplanung beim Freelancing fast so einfach wie ein Angestelltenverhältnis machen würde? Was, wenn intelligente Datenauswertung dabei hilft, gute Entscheidungen als "Arbeitszeitunternehmer\*in" zu treffen? Unser Tool minimiert Risiken und macht den finanziellen "Papierkram" einfach. Freelancing wird so effizienter, weniger riskant, und damit auch einsteigerfreundlicher.

Mit Tuttle entwickeln wir eine Applikation, die genau auf die Anforderungen von Solo-Selbständigen zugeschnitten ist. Wir automatisieren und verschaffen Freelancer\*innen mehr Zeit für die Arbeit, die sie lieben. Die Idee zu diesem Projekt entstand aus dem Erfahrungsaustausch unter Freelancer\*innen.

### Funktionalität 

Unser Ziel ist eine GUI-Applikation für die gängigen Desktop-Betriebssysteme zur Verfügung zu stellen. Die Verarbeitung von Geschäftsdaten erfolgt dabei bewusst lokal auf dem Endgerät - ohne zentrale Datenerfassung. 

Für die Kernfunktionalität setzen wir auf Open-Source-Tools aus dem Python-Ökosystem. Die Kernfunktionen sind in Kürze:

- **Kunden- und Vertragsmanagement**: Unsere Applikation wird zum zentralen Ort zur Ablage und Organisation von Kundendaten und vertraglichen Vereinbarungen (Laufzeiten, Stundensätze...).

- **Zeiterfassung**: Wir ermöglichen den Import von Zeiterfassungsdaten über verschiedene Schnittstellen, wie beispielsweise den Kalender in der Cloud.

- **Rechnungswesen**: Basierend auf Zeiterfassung und Vertragsdaten generiert die Applikation auf Knopfdruck Rechnungen.

- **Zeitmanagement**: Als Freelancer\*in möchte ich vorausschauend meine Kapazitäten für verschiedene Projekte und Kund\*innen planen, beispielsweise über meinen Kalender. Auf Basis dieser Planung kann ich zukünftige Umsätze schätzen und die Einhaltung vertraglich vereinbarter Kontingente überwachen. 

- **Umsatzvorschau**: Basierend auf Zeiterfassung und Zeitplanung können wir den voraussichtlichen Umsatz berechnen und live anpassen sobald sich die Planung ändert. Damit hilft die Applikation, Entscheidungen bei der Kapazitätsplanung zu treffen.

- **Vorschau auf Steuern und Sozialversicherungsbeiträge**: Diese umsatzabhängigen Zahlungsverpflichtungen schätzt das Tool basierend auf Zeiterfassung und vorausschauender Zeit- und Projektplanung.

- **Effektives Einkommen**: Was ist mein effektives "Gehalt" aus meiner selbständigen Tätigkeit? Unsere App beantwortet nach guter Pflege der Daten auch diese Frage.

## Status und Roadmap

In der Förderphase haben wir uns auf das Prototyping fokussiert, d. h. Entwurf und Implementierung der Kernfunktionalität sowie des benötigten Technolgiestacks. In Interviews mit Solo-Selbständigen aus verschiedensten Branchen haben wir dazu Anforderungen gesammelt und analysiert. Dies half uns dabei zu konsolidieren, was für unser Projekt als "in scope" gilt und was für ein Minimal Viable Product (MVP) priorisiert werden sollte. Die Interviews lieferten auch die Erkenntnis, dass schon relativ einfache Automatisierungen vielen Freelancer\*innen relevant Zeit sparen können.

Es folgte die Evaluation eines geeigneten Technologiestacks, die Implementierung eines Datenmodells, sowie die Implementierung der für ein MVP benötigten Workflows und Automatisierungen. Diese Grundfunktionen stellen wir in Form einer Python-Library zusammen. Diesen Prototyp in Form von Workflows validieren wir im Test mit diversen Freelancer\*innen.

Wir werden das Tool im Anschluss an die Förderphase zu einer anwenderfreundlichen Desktop-Applikation weiterentwickeln. Nächste Schritte beinhalten also das Design und Integration der Funktionen in einer Cross-Platform GUI-Applikation.

Wir planen außerdem, das Projekt für Contributors zu öffnen und evaluieren Möglichkeiten, das Projekt über die Förderung hinaus nachhaltig aufzustellen.

![](/assets/images/project_images/tuttle/demo-invoicing.gif)

## Erfahrungen mit Open Source

Die Förderung durch den Prototype Fund ermöglicht es Softwareentwickler\*innen, sich auf das Open-Source-Modell und freie Software zu fokussieren. Durch die Förderung wurde es für uns zur realen Möglichkeit, von Grund auf eine moderne Desktop-Applikation in Python zu entwickeln und dabei komplett auf Open-Source-Technologien aufzubauen.

Einerseits konnten wir auf ein reichhaltiges Open-Source-Ökosystem zurückgreifen - viele freie Module boten bereits benötigte Funktionalität, sodass wir in einigen Fällen unsere Funktionen aus bereits existierenden Modulen "zusammenzustecken" konnten. Andererseits stellten wir fest, dass einige dieser Module eher unregelmäßig maintained werden und oft mit wenig Kapazität auskommen müssen. Grundlegende digitale Infrastruktur entsteht oft in der Freizeit einiger weniger Entwickler\*innen.

Unser Projekt wurde also zum Stakeholder anderer Open-Source-Projekte und folgerichtig auch zu Unterstützer\*in und Contributor. Eine sehr motivierende Erfahrung war dabei die Effizienz und Geschwindigkeit der Zusammenarbeit auf GitHub: Bei einem Python-Modul, das man Anfang der Woche entdeckt, kann man mithilfe der Maintainer zum Ende der Woche bereits Contributor sein und einen Pull Request für ein fehlendes Feature beitragen.

Wir danken dem Bundesministerium für Bildung und Forschung für die Förderung sowie dem Deutschen Luft- und Raumfahrtzentrum für die Unterstützung.

## Links

- [Projekt-Website](https://tuttle-dev.github.io/tuttle/)
- [GitHub](https://github.com/tuttle-dev)

Bild: (c) Nenad Stojkovic - CC-BY - [https://www.flickr.com/photos/nenadstojkovic/49922626421](https://www.flickr.com/photos/nenadstojkovic/49922626421)