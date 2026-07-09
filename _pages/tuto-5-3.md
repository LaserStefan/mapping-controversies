---
permalink: /5.3/
layout: single
title: "5.3. Das Protokoll schreiben: Artikel-Editor-Netzwerk aus einer Kategorie"
---

# Übung für das zweite Semester

**Ziele**
* Ein **neues Notebook** kennenlernen
* Ein bipartites Netzwerk aus einer Wikipedia-Kategorie **sammeln**
* Ein **komplexeres Protokoll schreiben**
* Das eigene Wissen über Notebooks und digitale Methoden **anwenden**

# Daten

```
Category:Energy conversion
```

# Aufgabe

Dies ist eine Übung und kein Tutorial, auch wenn dabei ein neues Notebook vorgestellt wird. Da der Ablauf inzwischen bekannt ist, fallen die Anweisungen kürzer aus. Im Kern geht es darum, das Netzwerk zu erzeugen und zu analysieren, das bereits in [Tutorial 3.2](../3.2/) visualisiert wurde (und im Grunde noch einmal in [1.11](../1.11/)): Artikel und Editoren. „Wiederholung ist die Mutter allen Lernens“, sagt man.

Konkret geht es um Folgendes:
1. Die Artikel der Kategorie *energy conversion* mit einem Max Level von 1 sammeln ([🍉&nbsp;Notebook](https://colab.research.google.com/github/jacomyma/mapping-controversies/blob/main/notebooks/Wikipedia_category_to_article_list.ipynb)).
1. Mit dieser Liste das bipartite Netzwerk aus Artikeln und Editoren sammeln, mithilfe dieses Notebooks: [🍄&nbsp;Wikipedia articles to articles and editors network](https://colab.research.google.com/github/jacomyma/mapping-controversies/blob/main/notebooks/Wikipedia_articles_to_articles_and_editors_network.ipynb)
1. Eine Netzwerkkarte in Gephi erstellen (eine Annotation ist nicht nötig)
1. Das visuelle Protokoll in Google Slides schreiben

**Empfehlung:** Wie in den vorherigen Tutorials gesehen, muss das Netzwerk in Gephi **gefiltert** werden. Die verwendeten Filtereinstellungen sowie jede ungewöhnliche Operation müssen **im visuellen Protokoll festgehalten werden**.

# Erstellte Dokumente

Für die spätere Weitergabe sollte man Folgendes aufbewahren:
* Das Bild der Netzwerkkarte (JPEG oder PNG)
* Das Bild des Protokolls (JPEG oder PNG)

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
