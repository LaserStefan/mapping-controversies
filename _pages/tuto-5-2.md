---
permalink: /5.2/
layout: single
title: "5.2. Dem Protokoll folgen: Co-Referenz-Netzwerk aus einer Kategorie"
---

# Übungen für das zweite Semester


**Ziele**
* **Zwei neue Jupyter-Notebooks** kennenlernen
* Prüfen, wie sich **Wikipedia-Kategorien** zur Datengewinnung nutzen lassen
* Ein Co-Referenz-Netzwerk aus einer Wikipedia-Kategorie **sammeln**
* Einem komplexeren Protokoll folgen

# Daten

Die einzige benötigte Angabe ist dieser kurze Text:

```
Category:Energy conversion
```

Das ist lediglich der Titel der [Wikipedia-Kategorie zu energy conversion](https://en.wikipedia.org/wiki/Category:Energy_conversion). Trotzdem ist es ein *Datum* (Singular von Daten)!

Eine Kategorie auf Wikipedia ist eine von den Editoren kuratierte Sammlung von Seiten zu einem bestimmten Thema. Innerhalb der Kategorie gibt es auch Unterkategorien. Das bedeutet, manche Seiten befinden sich direkt in der Kategorie, während andere, thematisch ebenfalls relevante Seiten sich auf tieferen Ebenen von Unterkategorien befinden. Ebene 0 wären Seiten, die direkt in der Kategorie liegen, während Ebene 2 Seiten wären, die innerhalb einer Unterkategorie einer Unterkategorie der Kategorie liegen. Das wird im Folgenden genutzt, um die Erhebung zu steuern.

# Protokoll

Hier das Protokoll (die Annotation kann übersprungen werden, da bereits etwas Ähnliches in Tutorial 3.2 gemacht wurde):

[
	![Overview tuto 2.3](../assets/images/2-3/Protocol_Tutorial2-3.svg)
](../assets/images/2-3/Protocol_Tutorial2-3.svg)


Folgende Anweisungen befolgen:
* Die in einer Wikipedia-Kategorie aufgeführten Wikipedia-Artikel sammeln
	* Die Wikipedia-Kategorie ist *energy conversion*
	* Ein ```max level``` von 0 verwenden (keine Unterkategorien sammeln)
	* Folgendes Notebook verwenden: [🍉&nbsp;Wikipedia category to article list](https://colab.research.google.com/github/jacomyma/mapping-controversies/blob/main/notebooks/Wikipedia_category_to_article_list.ipynb)
	* Als Ergebnis sollte eine [<i class="fas fa-file-csv"></i> CSV-Liste](../assets/data/5-2/wikipedia-articles.csv) mit 139 Artikeln entstehen
* Ein Co-Referenz-Netzwerk sammeln (Artikel werden verbunden, wenn sie eine oder mehrere Referenzen teilen)
	* Die Artikelliste als Input verwenden
	* Folgendes Notebook verwenden: [🫕&nbsp;Wikipedia articles to co-reference network](https://colab.research.google.com/github/jacomyma/mapping-controversies/blob/main/notebooks/Wikipedia_articles_to_co_reference_network.ipynb)
	* Als Ergebnis sollte eine [<i class="fas fa-file"></i> GEXF](../assets/data/5-2/wikipedia-articles-coreference-network.gexf) entstehen
* Die GEXF in Gephi visualisieren
	* Die Netzwerkkarte als Bild exportieren

Wer das alles geschafft hat, bravo! Damit wurden zwei neue Notebooks entdeckt, die sich auch später noch nutzen lassen. Die erstellte Netzwerkkarte entspricht im Wesentlichen der aus [Tutorial 1.10](../1.10/), nur mit weniger Knoten. Bei mehr Zeit lässt sich auch das große Netzwerk erzeugen: dafür einfach ```max level``` auf 2 setzen. Für die vorhandene Zeit ist das allerdings etwas viel...

# Erstellte Dokumente

Für die spätere Weitergabe sollte man Folgendes aufbewahren:
* Die (nicht annotierte) Netzwerkkarte (JPEG oder PNG)

---

### Bezug zu den Kurslektüren

* Der Prozess der Datenerhebung über Scraping, Crawling und API-Aufrufe wird behandelt in **Kapitel 6: Collecting and curating digital records** von *Venturini, T. & Munk, A.K. (2021). Controversy Mapping: A Field Guide.*
* Die Besonderheiten von Wikipedia und die verschiedenen Wege, wie die Plattform für die Kontroversenanalyse genutzt werden kann, werden behandelt in *Weltevrede, E., & Borra, E. (2016).* **Platform affordances and data practices: The value of dispute on Wikipedia**
*Big Data & Society, 3(1).*
* Die Prinzipien und Konzepte der Visual Network Analysis (VNA) werden behandelt in **Kapitel 2: What is visual network analysis** in *Jacomy, M. (2021). Situating Visual Network Analysis*
* Sowie in **Kapitel 7: Visual network analysis** in *Venturini, T. & Munk, A.K. (2021). Controversy Mapping: A Field Guide*

### Tools für vergleichbare Daten (Netzwerke im GEXF- oder GDF-Format) aus anderen Quellen:

* Netzwerke von YouTube-Kanälen oder YouTube-Videos, verbunden über ihre Ähnlichkeit (gemessen an den algorithmischen Empfehlungen), mit den [YouTube Data Tools](https://tools.digitalmethods.net/netvizz/youtube/). Benötigt eine Liste von Video- oder Kanal-IDs als Input.
* Netzwerke wissenschaftlicher Publikationen, verbunden über Schlagworte oder Zitationen, mit [ScienceScape](http://medialab.github.io/sciencescape/). Benötigt einen vollständigen Export aus Scopus als Input.
