---
layout: project
title: "macht.sprache. - für inklusives und diskriminierungsfreies Übersetzen"
image: /assets/images/project_images/macht-sprache/header.png
authors:
  - author: Lucy Gasser
    link: 
  - author: Anna von Rath
    link: 
  - author: Timur Çelikel
    link: 
  - author: Kolja Lange
    link: 
brief: "Wir fördern inklusive und diskriminierungsfreie Übersetzung."
summary: "Das macht.sprache. Übersetzungstool hat eine Integration mit Google Translate bekommen und unterstützt nun verstärkt gendersensibles Übersetzen."
---

<div class="iframe-container">
    <iframe src="https://www.youtube-nocookie.com/embed/dz-fKyZxAVo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

Diskriminierung ist in Sprache eingebettet. Sprache beeinflusst die Art und Weise, wie wir über Fragen von _Race_, Geschlecht, Sexualität, Zugehörigkeit, usw. denken und sprechen. Es ist schon herausfordernd, solche Mechanismen in einer Sprache zu verstehen, selbst wenn es die eigene Muttersprache ist. Noch komplizierter wird es für diejenigen, die sprachübergreifend arbeiten, was in unserer globalisierten Welt zunehmend der Fall ist. In vielen Berufen und Alltagstätigkeiten ist es normal geworden, digitale Übersetzungshilfen zu nutzen, aber natürlich haben diese Tools ihre Grenzen. Diese Herausforderungen nahmen wir - Lucy Gasser, Anna von Rath, Kolja Lange und Timur Çelikel - zum Anlass, macht.sprache zu entwickeln.

macht.sprache. ist eine Web-App, die das Ziel hat, politisch sensibles Übersetzen zwischen Deutsch und Englisch zu fördern. Nutzer:innen erhalten auf [macht.sprache.](https://www.machtsprache.de) bereits vielfältige Unterstützung: macht.sprache. ist eine **Diskussionsplattform**, auf der politisch sensible Begriffe, ihre Übersetzungen und Übersetzungsbeispiele gesammelt und diskutiert werden können. Ein **Text Checker** überprüft Textausschnitte von Nutzer:innen auf sensible Begriffe. Zusätzlich bietet ein begleitendes **Manifest** nützliche Grundprinzipien und Leitlinien für politisch sensibles Übersetzen. Mithilfe des Prototype Fund konnten wir außerdem eine Integration mit der gängigen Übersetzungswebsite Google Translate entwickeln. macht.sprache. kann als **Browsererweiterung** auf dieser Seite aktiviert werden und somit weitaus mehr Nutzer:innen erreichen.

### Der Text Checker

Die Browsererweiterung basiert auf dem Text Checker, den wir hier deshalb kurz als erstes vorstellen. Um einen Text auf sensible Begriffe zu überprüfen, können Nutzer:innen ihn auf [macht.sprache.](https://www.machtsprache.de) in die Maske des Text Checkers eingeben oder hinein kopieren. Der Text Checker gleicht den eingefügten Text mit den Begriffen aus der macht.sprache. Datenbank ab und hebt sensible Begriffe hervor. Die Datenbank ist über Crowdsourcing entstanden und kann von Nutzer:innen ständig erweitert werden. Kollaboratives Wissen, das vom Projektteam kuratiert wird, ist also die Grundlage des Text Checkers.

Zu den hervorgehobenen Begriffen bietet der Text Checker Definitionen und Übersetzungsoptionen an, die in der Reihenfolge angezeigt werden, wie Nutzer:innen sie zuvor auf einer Skala von “würde ich ständig benutzen” bis “würde ich nie benutzen” bewertet haben. Der Text Checker macht Vorschläge, aber letztendlich muss die übersetzende Person entscheiden, was für den übersetzten Text die beste Option ist. Um diese Entscheidung zu erleichtern, bietet macht.sprache. zusätzliche Unterstützung in Form des Manifests an, aus dem die relevantesten Abschnitte für den betreffenden hervorgehobenen Begriff gemeinsam mit der Definition und den Übersetzungsoptionen angezeigt werden. Es handelt sich um Grundprinzipien und Leitlinien für politisch sensibles Übersetzen, die z. B. auf Genre und Register, Tonfall und Haltung oder kreative Lösungen verweisen. Außerdem wird die Diskussion zu dem jeweiligen Begriff auf machtspache.de verlinkt. Nutzer:innen können sich weiterhin in die Diskussion einbringen, konkrete Übersetzungsbeispiele ansprechen, um Tipps von der Community zu erhalten, und neue Begriffe hinzufügen.

### Relevanz der Browsererweiterung

Da bereits viele Menschen regelmäßig Google Translate verwenden, kann macht.sprache. durch die Integration mit dieser gängigen Übersetzungswebsite eine größere Reichweite erzielen. Das Plug-In erleichtert es Menschen, die täglich zwischen Englisch und Deutsch wechseln, schnell und ohne großen Aufwand einen höheren Grad an Sensibilität in ihre Arbeit zu integrieren.

Die Browsererweiterung ist besonders relevant, da digitale Übersetzungstools mithilfe von Datensätzen trainiert werden, die implizite Vorurteile enthalten. Somit reproduziert Google Translate häufig etablierte Formen sprachlicher Diskriminierung. Besonders deutlich wird dies bei sexistischen Annahmen, die in gegenderter Sprache widergespiegelt werden. Das folgende Beispiel zeigt, dass bestimmten Berufen oder Tätigkeiten, die im Englischen nicht gegendert sind, im Deutschen häufig ein Geschlecht zugeschrieben wird – „science teacher“ wird zu „Wissenschaftslehrer“ und „home economics teacher“ zu „Hauswirtschaftslehrerin“.

![Screenshot von Google Translate](/assets/images/project_images/macht-sprache/screenshot-google-translate.png)

Neben den Begriffen aus unserer Datenbank werden mittels Natural Language Processing Personenbezeichnungen erkannt, die potenziell sexistisch übersetzt werden. Personenbezeichnungen werden hervorgehoben und die Erweiterung macht Vorschläge zu genderinklusiven und genderfreien Sprachformen. So sensibilisiert die macht.sprache. Browsererweiterung für die implizit sexistischen Annahmen etablierter Übersetzungshilfen und schafft Aufmerksamkeit für die größere Problematik von Diskriminierung in Sprache und Übersetzungen. Die diskriminierenden Mechanismen in Sprache sind vielfältig, dank unserer Browsererweiterung müssen nicht alle gleich Expert:innen für diese Thematik werden, können aber trotzdem mehr Sensibilität in ihre Arbeit integrieren.

### Technische Umsetzung der Erweiterung

Nutzer:innen können sich die Erweiterung über den Chrome Web Store installieren. Die Erweiterung für den Browser ist ein JavaScript-Programm, in unserem Fall geschrieben in TypeScript. Wenn die Webseite [translate.google.com](https://translate.google.com) aufgerufen wird, lädt der Browser unsere Erweiterung und wir können die Webseite manipulieren. Mittels eines Mutation Observers überwachen wir, wann sich die Elemente im DOM ändern. Wenn es ein unterstütztes Sprachpaar (DE-EN und EN-DE) gibt, schicken wir eine Anfrage an unseren Server und blenden die Hinweise ein. Die in Google Translate angezeigte Übersetzung wird mit der Datenbank von macht.sprache. abgeglichen. Hinweise zu Gender werden immer angezeigt, wenn das Natural Language Processing feststellt, dass es sich um eine Personenbezeichnung handelt.

Eine besondere Herausforderung ist, einerseits unsere Komponenten einzusetzen, ohne die Funktionalität von Google Translate zu behindern und andererseits unsere Komponenten neu einzufügen, wenn das JavaScript von Google Translate Elemente neu rendert. Um zu verhindern, dass Google Translate aufgrund unserer Intervention abstürzt, zeigt die macht.sprache.-Erweiterung die hervorgehobenen Begriffen technisch in einem Overlay an: Wir kopieren den Text sowie die CSS-Klassen bzw. Stile von Google Translate, positionieren dieses über dem Original von Google Translate und erweitern es um die Hervorhebungen. Der Text in dem Overlay ist transparent und die Pointer Events sind entfernt, nur die Hervorhebungen sind sicht- und klickbar.

Auf diese Weise umgehen wir die Interaktion mit dem originalen DOM, obwohl es so aussieht, als seien die Begriffe direkt im Text hervorgehoben. Nutzer:innen können auf die hervorgehobenen Begriffe klicken, damit sich das Modal mit dem Inhalt von macht.sprache. öffnet. Dieses bietet ihnen die bereits erwähnte Unterstützung für ihre Übersetzung. Das Modal entspricht dem, das bereits für den macht.sprache. Text Checker verwendet wird, wurde aber für die Erweiterung angepasst.

### Geplante Weiterentwicklung

Im Förderzeitraum des Prototype Funds konnten wir uns stärker mit der Gender Thematik auseinandersetzen und die macht.sprache. Erweierung für Google Translate und Chrome entwickeln. Auf dieser Basis aufbauend wird die Erweiterung zeitnah auch für DeepL und andere Browser zur Verfügung stehen. 
Wir danken dem BMBF und dem DLR für die Förderung, die dazu beiträgt, Übersetzungen sensibler zu machen!
