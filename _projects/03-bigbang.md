---
layout: project
title: "BigBang"
image: /assets/images/project_images/bigbang/header.jpg
authors:
  - author: Christoph Becker
    link: https://christovis.github.io/
  - author: BigBang
    link: https://datactive.github.io/bigbang/
brief: "Wir machen die Produktion digitaler Infrastrukturen transparenter und rechenschaftspflichtiger."
summary: "Ziel von BigBang ist es, die Produktion digitaler Infrastrukturen transparenter und rechenschaftspflichtiger zu machen. Dies erreichen wir, indem wir deutlich machen, wer teilnimmt, entscheidet oder ausgelassen wird. Dazu werden öffentliche Mailinglisten, Dokumente und weitere netzbasierte Medien von Normgremien (z. B. IETF und W3C) untersucht. BigBang verwendet dafür statistische Analysemethoden wie Häufigkeitsverteilung, Diskurse und Zeitreihen. BigBang ist in Python programmiert und enthält Notizbücher, die es für Forschende und Bürger\\*innen mit oder ohne Erfahrung in quantitative Methoden zugänglicher machen."
---

Jedes Mal, wenn du das Internet benutzt, um mit Verwandten in Kontakt zu bleiben oder Nachrichten aus aller Welt zu lesen, verlässt du dich auf die Arbeit von Normgremien, die ein schnelles, sicheres und genaues Übermitteln von Webseiten, Videos und Telefonsignalen garantieren. Es gibt eine Vielzahl von unterschiedlichen regionalen und globalen Normgremien, die Standards und Protokolle für das Internet definieren. Zwei der wichtigsten Normgremien sind die '[Internet Engineering Task Force](https://www.ietf.org/)' (IETF) und das '[World Wide Web Consortium](https://www.w3.org/)' (W3C), die zusammen Standards wie HTML, JPEG, SSH, oder PGP gesetzt haben.

Weil man nicht über die Kabel, Datenzentren oder Antennen nachdenken muss, wenn man im Internet surft, entfaltet sich der enorme Einfluss von Normgremien, z. B. auf die Fähigkeit privater Nutzer\*innen ihre eigenen Datenströme zu kontrollieren, oftmals unbemerkt im Hintergrund. Auch wenn einige Normgremien offen für die Teilnahme eines/einer jeden sind, werden sie oft von internationalen Konzernen (so wie Ericsson, Qualcomm, Siemens, Nokia, Huawei) dominiert. Die Kontrolle darüber, ob neue Standards gewisse Kriterien erfüllen (z. B. auf die Gewährleistung der Privatsphäre von Nutzer\*innen) oder richtig implementiert werden, wird den von privaten Unternehmen dominierten Normgremien selbst überlassen.

Mit BigBang haben wir uns das Ziel gesetzt, die Machtverhältnisse, Intentionen und Motivationen innerhalb der Normgremien offen zu legen und sie somit transparenter und rechenschaftspflichtiger zu machen. Normgremien wie IETF und W3C veröffentlichen nicht nur einen großen Teil ihrer Berichte und Dokumente sondern auch Aufzeichnungen von Treffen, Telefonkonferenzen und Mailinglisten auf ihren Webseiten. Diese Archive bieten Forscher\*innen eine einzigartige Gelegenheit, die Prämissen der Entscheidungen, die innerhalb von Normgremien getroffen werden, zu untersuchen. Insbesondere in Mailinglisten spiegeln sich die vielfältigen Schichten der Normgremien wider - hier werden Entscheidungsfindungen sichtbar gemacht. 

Des Weiteren besitzen sie die folgenden Vorteile:
- Mailinglisten sind strukturiert: Sie besitzen eine standardisierte Struktur, die seit den frühen Anfängen des Internets beibehalten wurde. Kopfzeilen machen Metadaten (z. B. Absender\*in und Zeitstempel) leicht verfügbar, was verschiedene Arten der Klassifizierung und Analyse unterstützt.
- Mailinglisten sind bereichsübergreifend: Eine Vielzahl von unterschiedlichen Fachgruppen tauscht sich innerhalb thematisierter Mailinglisten aus. Dies ermöglicht es Forscher\*innen, die Interaktion (z. B. Zusammenarbeit und Reibungspunkte) zwischen den Fachgruppen untersuchen.
- Mailinglisten sind relational: Sie liefern Informationen über Beziehungen zwischen Akteur\*innen (z. B. wer adressiert wen). Dies ermöglicht es Forschern zu sehen, wer an Entscheidungen teilnimmt oder ausgeschlossen wird.
- Mailinglisten sind mehrdimensional: Weil sie viele verschiedene Facetten besitzen, ermöglichen sie eine Reihe an statistischen Methoden wie Häufigkeitsverteilung, Diskurs-, Zeitreihen- und Netzwerkanalyse.

Um BigBang zugänglich zu machen, haben wir die weit verbreitete Programmiersprache Python verwendet, eine Befehlszeilenschnittstelle erstellt und Jupyter Notebooks geschrieben, die Tutorien beinhalten.

Der Anwendungsablauf von BigBang ist in drei Phasen unterteilt. Zuerst muss angegeben werden, auf welche Mailinglisten zugegriffen werden soll. BigBang enthält alle bestehenden Mailinglisten von [IETF](https://github.com/datactive/bigbang/blob/main/examples/url_collections/mm.ietf.org.txt), [W3C](https://github.com/datactive/bigbang/blob/main/examples/url_collections/W3C.txt), [3GPP](https://github.com/datactive/bigbang/blob/main/examples/url_collections/listserv.3GPP.txt), [ICANN](https://github.com/datactive/bigbang/blob/main/examples/url_collections/mm.icann.org.txt) und [IEEE](https://github.com/datactive/bigbang/blob/main/examples/url_collections/listserv.IEEE.txt). Nutzer\*innen können die Mailinglisten, die sie interessieren, heraussuchen und in eine Textdatei kopieren.

Als zweites müssen die Mailinglisten heruntergeladen werde. Dies kann man entweder manuell in einem Python-Programm machen
```
from bigbang.ingress import W3CMailList,

mlist = W3CMailList.from_url(
    name="public-webauthn",
    url="https://lists.w3.org/Archives/Public/public-webauthn",
)
```
oder durch die Befehlszeilenschnittstelle, indem das folgende in ein Terminal eingegeben wird:
```
$ python3 bin/collect_mail.py -f <Dateipfad zu der Textdatei>
public-webauthn: 100%|#######################################################| 17956/17956 [7:58:47<00:00,  1.60s/it]
www-voice:  34%|######################8                                        | 1408/4128 [38:24<1:16:19,  1.68s/it]
```
Da dies ein zeitaufwändiges Verfahren für große Mailinglisten (einige Mailinglisten umfassen bis zu 200k E-Mails, wodurch es bis zu 111 Stunden dauern kann, um sie herunterzuladen) sein kann, arbeiten wir daran, die Datensätze in einem leichter zugänglichen Format zu teilen, welches die DSGVO-Grundsätze berücksichtigt.

Nachdem alle Mailinglisten heruntergeladen wurden, können sie mit einigen bereitgestellten Funktionen analysiert werden, wie z. B. dem Zählen der gesendeten Nachrichten per Domänenteil
```
mlist.get_messagescount(
    header_fields=["comments-to"],
    per_address_field="domain",
)
```
oder dem Filtern aller Nachrichten mit einer bestimmten Betreffzeile.
```
mlist.crop_by_subject(match="EVS SWG Sessions")
```
Mit fortgeschrittenen Funktionen können Ergebnisse erzielt werden, wie sie in den folgenden Darstellungen zu sehen sind.

![Communication Network in 3GPP_TSG_RAN_WG5_IOT](/assets/images/project_images/bigbang/bigbang_communication_network.png)
Bild 1: Kommunikationsnetzwerk der 3GPP Mailingliste '[3GPP_TSG_RAN_WG5_IOT](https://list.etsi.org/scripts/wa.exe?A0=3GPP_TSG_RAN_WG5_IOT)'. Violette und dünne Linien deuten auf weniger gesendete Nachrichten hin, rote und dicke Linien auf viele gesendete Nachrichten. Es zeigt sich, dass insbesondere Huawei viele Nachrichten mit Ericsson und Siemens ausgetauscht hat.

![Network centralities in 3GPP_TSG_RAN_WG4_IOT](/assets/images/project_images/bigbang/bigbang_centralities.png?raw=true)
Bild 2: Von links nach rechts sind die Gradzentralität, Nähezentralität und Zwischenzentralität für verschiedene Domänenteile in der 3GPP '[3GPP_TSG_RAN_WG4_IOT](https://list.etsi.org/scripts/wa.exe?A0=3GPP_TSG_RAN_WG4_IOT)' Mailingliste berechnet. Es wird deutlich, dass ETSI, ein Partnerprojekt von 3GPP und die 'China Academy of Telecommunications Technology' (CATT) besonders relevant sind.

![Number of send and received messages by Chinese companies in the 3GPP_TSG_CT_WG4](/assets/images/project_images/bigbang/bigbang_msgs_send_received.png?raw=true)
Bild 3: Oben ist die Anzahl der pro Jahr gesendeten und unten der empfangenen E-Mails von Chinesischen (farbige Linien) und anderen (graue Linien) Firmen in der 3GPP '[3GPP_TSG_CT_WG4](https://list.etsi.org/scripts/wa.exe?A0=3GPP_TSG_CT_WG4)' 

Mailingliste zu sehen. Die vertikalen gepunkteten Linien markieren die Jahre, in denen neue Standards veröffentlicht wurden.

In diesem Video finden Interessierte ein detailliertes How-To-Tutorialt: 

<div class="iframe-container">
    <iframe src="https://www.youtube-nocookie.com/embed/JWimku8JVqE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

BigBang hat bereits aktive Entwickler\*innen- und Nutzer\*innengruppen bestehend aus Akademiker\*innen und Aktivist\*innen der Zivilgesellschaft. Es wurde für Projekte der Menschenrechtsorganisation [ARTICLE19](https://www.article19.org/), des '[Center for Democracy and Technology](https://cdt.org/)' (CDT), und des '[Centre for Internet & Society](https://cis-india.org/)' (CIS-India) verwendet. Veröffentlichte Resultate beinhalten unter anderem die Untersuchungsergebnisse von Diversität von ICANN ([[1]](#1)) und dazu, inwieweit Menschenrechte von Netzinfrastrukturanbieter berücksichtigt werden ([[2]](#2), [[3]](#3)).

Wir danken dem Bundesministerium für Bildung und Forschung für die Förderung und dem Deutschen Luft- und Raumfahrtzentrum für die Unterstützung.

### References

<a id="1">[1]</a>
[ICANN Diversity Analysis](https://cis-india.org/internet-governance/blog/icann-diversity-analysis)
Akriti Bopanna, 2018

<a id="2">[2]</a>
[Public interest, private infrastructure: An analysis of the barriers and drivers for adopting human rights standards in the Internet infrastructure industry](https://www.article19.org/wp-content/uploads/2018/06/HRIA-report-UNGP_5.6.pdf)
ARTICLE 19, 2018

<a id="3">[3]</a>
[Human Rights Due Diligence and Internet Infrastructure](https://www.article19.org/wp-content/uploads/2021/06/A19-and-DIHR-pilot-project-outcome-report_FINAL.pdf)
ARTICLE 19, 2021


### Danke

Ganz besonders wollen wir uns beim Prototype Fund, dem BMBF und dem DLR für die Unterstützung und die Möglichkeit, dieses Projekt zu entwickeln, bedanken.