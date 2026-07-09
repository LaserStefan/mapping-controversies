---
permalink: /5.1/
layout: single
title: "5.1. Das Protokoll schreiben: von einem Artikel aus mit SeeAlsology scrapen"
---

# Mit dieser Übung startet man ins zweite Semester

Das sind noch die rohen Dateien, wie sie aus der englischsprachigen Übersetzung kommen. Wer möchte, kann schon einmal hereinschauen.
Hinzu kommen werden Informationen dazu, was es mit einem „Protokoll“ auf sich hat. Stay tuned.

**Ziele**
* Ein **eigenes Netzwerk sammeln** mit SeeAlsology
* Wissen, dass das Tool eine Kombination aus Scraping und API-Aufrufen nutzt, um Hyperlinks zu erhalten und dann zu crawlen.
* Eine Entscheidung treffen, wie das Netzwerk gesammelt wird (welche Einstellungen)
* Das Ergebnis mit Gephi erkunden
* **Das eigene Protokoll schreiben**

# Fall

**Freie Wahl!** Einen Wikipedia-Artikel aussuchen. Bevorzugt werden sollte ein Thema, das:
* einen selbst interessiert
* mit einer Kontroverse verknüpft ist, die man kartieren möchte
* ein Artikel, der nicht zu lang ist, *oder* einen guten „See also“-Abschnitt hat.

*Noch keine Idee? [Diesen hier](https://en.wikipedia.org/wiki/Copenhagen) ausprobieren.*

# Ein Netzwerk mit SeeAlsology sammeln

* [SeeAlsology](https://densitydesign.github.io/strumentalia-seealsology/) öffnen
* Die URL des gewählten Wikipedia-Artikels einfügen
* Ein Netzwerk sammeln

Dabei sollte man sich, vermutlich in dieser Reihenfolge, folgende Fragen stellen:
* Möchte man alle Links, oder nur die „See also“-Links am Ende der Seite? Die Einstellung ```Take all links``` entsprechend aktivieren oder deaktivieren. Bei allen Links ruft SeeAlsology einfach den [Links-Endpoint der Wikipedia-API](https://www.mediawiki.org/wiki/API:Links) auf und fragt die Information direkt ab. Bei nur den „See also“-Links muss das Tool [den Seiteninhalt über die API abfragen](https://www.mediawiki.org/wiki/API:Get_the_contents_of_a_page), den „See also“-Abschnitt identifizieren und daraus die Links extrahieren.
* Möchte man Links auch rückwärts sammeln (Seiten, die auf den eigenen Artikel verweisen, aber nicht unbedingt von ihm aus verlinkt sind)? Falls ja, ```Parent links``` aktivieren. Da diese Links vom eingegebenen Artikel aus nicht sichtbar sind, kann das Tool hier nichts scrapen und muss sich [auf die API verlassen, um Informationen zu Backlinks zu erhalten](https://www.mediawiki.org/wiki/API:Backlinks).
* Wie weit soll gecrawlt werden? Also: Wie viele Link-Schritte darf das Tool von der eingegebenen Startseite aus maximal gehen? Das Tool arbeitet wie ein Crawler und kann den Vorgang, Links zu holen, jedes Mal wiederholen, wenn es neue Seiten findet. Dieser Vorgang heißt Crawling, und in der Crawler-Terminologie wird die maximale Anzahl an Link-Schritten von der Startseite aus ```Distance``` genannt. **Tipp:** Mit kurzen Distanzen beginnen, um die Erhebung überschaubar zu halten.
* Möchte man die Knoten später in Gephi filtern? Möglicherweise, weil es zu viele schwach verbundene Knoten gibt...

Auf diese Fragen gibt es keine offensichtliche Antwort. Sie hängen vom jeweiligen Artikel und den eigenen Interessen ab. Manche Artikel haben keinen „See also“-Abschnitt, sodass zwangsläufig alle Links genommen werden müssen. Manche Artikel verlinken viele andere Artikel, sodass das Netzwerk zu schnell wächst und eine niedrige Distanz gewählt werden muss. Manche Artikel haben viele übergeordnete Artikel, manche keine, usw.

*Wie entscheiden:* Auf eine machbare Netzwerkgröße achten. Zu groß, und die Arbeit damit wird langsam oder unmöglich. Zu klein, und es gibt nichts zu interpretieren. Eine Größe anstreben, mit der man gut arbeiten kann. Vielleicht 100 bis 1.000 Knoten? Das hängt auch von der Leistung des eigenen Rechners ab!

***Anmerkung:** Per Definition liefert eine Distanz von 0 nur den Startartikel. Ebenso liefert eine Distanz von 1 den Startartikel und seine Nachbarn, aber nicht die Links zwischen ihnen (ein sternförmiges Netzwerk). Meist ist also eine Distanz von 2 oder mehr nötig.*

**Tipp:** Wenn die Startseite genügend „See also“-Links hat, lässt sich – ohne alle Links zu nehmen – bei höheren Distanzen (3 oder mehr) unter Umständen ein schönes Netzwerk erzielen.

**Tipp:** Wurden alle Links gesammelt, muss das Netzwerk vermutlich in Gephi gefiltert werden.

Dies ist das Netzwerk, das für den Artikel [Copenhagen](https://en.wikipedia.org/wiki/Copenhagen) mit einer Tiefe von 3, mit Parent Links und nur See-also-Links entstanden ist. Hier die [<i class="fas fa-file"></i>&nbsp;GEXF](../assets/data/5-1/see-also-copenhagen.gexf).

[
	![See also Copenhagen](../assets/images/2-2/see-also-copenhagen.png)
](../assets/images/2-2/see-also-copenhagen.png)

# In Gephi visualisieren

* Die GEXF aus SeeAlsology exportieren (über das Dropdown ```Download```).
* In Gephi visualisieren. Eventuell müssen einige Knoten herausgefiltert werden, falls es zu unübersichtlich ist...
* Das PNG exportieren (eine Annotation ist hier nicht nötig)

# Das Protokoll schreiben

In Google Slides das Protokoll zum erstellten Bild schreiben. **Es müssen die methodischen Entscheidungen enthalten sein, die in SeeAlsology getroffen wurden.** Dafür kann [diese Vorlage](https://docs.google.com/presentation/d/1pnV8ofxUogb9dKgiBzVuXDI5C1hk3A3WXgHo3HRdWug/edit?usp=sharing) kopiert und selbst bearbeitet werden.

# Erstellte Dokumente

Für die spätere Weitergabe sollte man Folgendes aufbewahren:
* Das Bild der Netzwerkkarte (JPEG oder PNG)
* Das Bild des Protokolls (JPEG oder PNG)

---


### Tools für vergleichbare Daten (Netzwerke im GEXF- oder GDF-Format) aus anderen Quellen:

* Netzwerke von YouTube-Kanälen oder YouTube-Videos, verbunden über ihre Ähnlichkeit (gemessen an den algorithmischen Empfehlungen), mit den [YouTube Data Tools](https://tools.digitalmethods.net/netvizz/youtube/). Benötigt eine Liste von Video- oder Kanal-IDs als Input.
* Netzwerke wissenschaftlicher Publikationen, verbunden über Schlagworte oder Zitationen, mit [ScienceScape](http://medialab.github.io/sciencescape/). Benötigt einen vollständigen Export aus Scopus als Input.

### Bezug zu den Kurslektüren

* Der Prozess der Datenerhebung über Scraping, Crawling und API-Aufrufe wird behandelt in **Kapitel 6: Collecting and curating digital records** von *Venturini, T. & Munk, A.K. (2021). Controversy Mapping: A Field Guide.*
* Die Besonderheiten von Wikipedia und die verschiedenen Wege, wie die Plattform für die Kontroversenanalyse genutzt werden kann, werden behandelt in *Weltevrede, E., & Borra, E. (2016).* **Platform affordances and data practices: The value of dispute on Wikipedia**
*Big Data & Society, 3(1).*
* Ein ähnliches Netzwerk wird beschrieben in **Abbildung 47** von *Venturini, T. & Munk, A.K. (2021). Controversy Mapping: A Field Guide*:

[
	![Overview tuto 1.10](https://medihal.archives-ouvertes.fr/hal-03227358/image)
](https://medihal.archives-ouvertes.fr/hal-03227358/image)
*Netzwerk, das durch Crawlen der Seite „Circumcision controversies“ auf Wikipedia mit Crawl-Distanz 1 entstand, wobei zusätzlich die Wikipedia-API aufgerufen wurde, um über Backlinks weitere Seiten zu finden. Seiten, die ausschließlich über Backlinks gefunden wurden, sind entsprechend beschriftet.*
