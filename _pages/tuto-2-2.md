---
permalink: /2.2/
layout: single
title: 2.2. Daten mit Jupyter-Notebooks scrapen
---
# Tool-Sitzung #2

**Ziele**
* Lernen, wie man ein **Jupyter-Notebook** über Jupyter ausführt. Siehe https://ruhr-uni-bochum.jupyterhub.nrw/
* Eine API aufrufen, um Daten zu erhalten
* Eine annotierte Visualisierung erstellen

*Hinweis: Ab hier sind die Beispieldaten noch die alten (Thema „energy conversion“). Sie werden demnächst durch KI-bezogene Beispiele ersetzt. Aktuell dient dieser Abschnitt also nur zum Testen des Ablaufs.*

# Fall

Noch immer das Thema *energy conversion*, diesmal aber mit 22 Artikeln (weshalb sich ein Notebook anbietet).

# Daten

Diese CSV herunterladen:

<center><a href="../assets/data/2-2/wikipedia-edits-1-2.csv">
	<i class="fas fa-file-csv" style="font-size:5em"></i><br>
	wikipedia-edits-1-2.csv
</a><br><br></center>

Sie enthält lediglich eine Liste von 22 Artikeln zum Thema energy conversion. Diese Liste ist eigentlich nur ein kleiner Ausschnitt aller Artikel zu energy conversion, sollte aber für den Anfang genügen.

Wer möchte, kann auch die [<i class="fas fa-file-csv"></i> Liste mit 139 Artikeln](../assets/data/2-2/wikipedia-articles-AI-1.2.csv) aus der ersten Ebene der [Wikipedia-Kategorie](https://en.wikipedia.org/wiki/Category:Energy_conversion) ausprobieren. In dem Fall dauert der Notebook-Lauf etwa 10 Minuten.

# Das Notebook in Google Colab öffnen

Etwas Kontext:
* Ein *Jupyter-Notebook* ist ein Online-Dokument, das ausführbaren Code (in Python), Text und Bilder enthält.
* Um den Code auszuführen, braucht man einen Computer. Zum Beispiel den eigenen Rechner mit [Anaconda](https://docs.anaconda.com/anaconda/); das wird hier aber nicht verwendet.
* Stattdessen wird [Google Colab](https://colab.research.google.com/) genutzt, eine Umgebung von Google, in der der Code auf einer virtuellen Maschine ausgeführt wird. Dafür ist ein Google-Konto nötig (genau wie bei Sheets).
* Das Skript ruft die API von Wikipedia auf und fragt für jeden Artikel der Liste alle Bearbeitungen ab. Diese Bearbeitungen heißen Revisions und sind über [diesen Endpoint](https://www.mediawiki.org/wiki/API:Revisions) erreichbar.

Verwendet wird folgendes Skript. Es öffnet sich direkt in Colab (liegt aber eigentlich [auf GitHub](https://github.com/jacomyma/mapping-controversies/tree/main/notebooks)).

**[🍹&nbsp;Wikipedia articles to edits list](https://colab.research.google.com/github/jacomyma/mapping-controversies/blob/main/notebooks/Wikipedia_articles_to_edits_list.ipynb)**

*Hinweis: Das Emoji jedes Notebooks dient nur dazu, sich leichter zu merken, welches Notebook was macht.*

Zuerst aber **dieses Tutorial ansehen.** Es verwendet dieselbe Datei und dasselbe Notebook.

{% include video id="UPyGLa4q_Dw" provider="youtube" %}

# Das Notebook ausführen, um Daten zu sammeln

* **Hochladen:** Die CSV-Daten in die virtuelle Maschine laden. Dazu links auf das ```File```-Symbol klicken, dann auf das Symbol oben, das ```Upload to session storage``` heißt, und die CSV von oben hochladen.
* Den Text des Notebooks lesen, inklusive ```SETTINGS```, bis vor ```SCRIPT```. Der Code selbst muss nicht verstanden werden, nur das, was er tut.
* **Einstellungen anpassen.** Insbesondere der Name der Eingabedatei stimmt wahrscheinlich nicht mit dem angegebenen überein. Entweder die Variable in den Einstellungen ändern oder die Datei in der virtuellen Maschine umbenennen.
* **Notebook ausführen.** Jede Zelle kann einzeln ausgeführt werden, empfohlen wird aber, alles auf einmal über das Menü ```Runtime > Run all``` laufen zu lassen. Fertig ist es, wenn die *letzte Zelle* „Done“ ausgibt.
* **Herunterladen:** Die Ausgabedatei aus der virtuellen Maschine herunterladen. Dazu zunächst die Dateien der virtuellen Maschine in der Seitenleiste über das ```Refresh```-Symbol aktualisieren. Dann die Ausgabedatei suchen, deren Name in den Einstellungen des Skripts angegeben wurde, und sie über das Dropdown-Menü (die drei Punkte rechts neben der Datei) herunterladen.

Das Ergebnis sollte etwa wie [<i class="fas fa-file-csv"></i> diese Datei](../assets/data/2-2/wikipedia-edits-tuto-1.2.csv) aussehen.

# Eine annotierte Visualisierung erstellen

Die Übung entspricht im Grunde den Tutorials [1.2](../1.2/) und [1.3](../1.3/), nur mit mehr Artikeln.

Die Tableau-Visualisierung könnte etwa so aussehen...

[
	![Timeline](../assets/images/1-6/timeline.png)
](../assets/images/1-6/timeline.png)

...oder auch so...

[
	![Stacked timeline](../assets/images/1-6/stacked-timeline.png)
](../assets/images/1-6/stacked-timeline.png)

...und es gibt noch viele weitere Möglichkeiten.

**Das Notebook erlaubt es, mit größeren Datenmengen zu arbeiten, was neue Forschungsfragen eröffnet.** Eine davon lässt sich für die Annotationen aufgreifen:
* Sind die Artikel synchron oder nicht? Werden sie zur gleichen Zeit bearbeitet?
* Sind manche Artikel älter, andere neuer? *Hinweis: Würde man dafür auf das Datum der ersten Bearbeitung schauen, oder auf etwas anderes?*
* Gibt es unterschiedliche Zeitpunkte, an denen verschiedene Artikel besonders viele Bearbeitungen erhalten?
* Werden bestimmte Artikel nur in bestimmten Weltregionen bearbeitet?

**Tipp:** Man kann die Dimension ```Article``` im ```Pages```-Bereich von Tableau nutzen ([siehe Hilfe](https://help.tableau.com/current/reader/desktop/en-us/pages_shelf.htm)), um schnell zwischen Artikeln zu vergleichen.

[
	![Stacked timeline](../assets/images/1-6/pages.png)
](../assets/images/1-6/pages.png)

# Erstellte Dokumente

Für die spätere Weitergabe sollte man Folgendes aufbewahren:
* Die annotierte Visualisierung (JPEG oder PNG)

---

### Weiterführende Ressourcen

* [Intro to Google Colab in 3 minutes](https://www.youtube.com/watch?v=inN8seMm7UI).
* [Eine Liste weiterer Endpoints, die man per Skript aufrufen kann, um Daten aus der Wikipedia-API zu erhalten](https://www.mediawiki.org/w/api.php?action=help&modules=query).

### Bezug zu den Kurslektüren

* Der Prozess der Datenerhebung über APIs wird behandelt in **Kapitel 6: Collecting and curating digital records** von *Venturini, T. & Munk, A.K. (2021). Controversy Mapping: A Field Guide.*
* Die Besonderheiten von Wikipedia und die verschiedenen Wege, wie die Plattform für die Kontroversenanalyse genutzt werden kann, werden behandelt in *Weltevrede, E., & Borra, E. (2016).* **Platform affordances and data practices: The value of dispute on Wikipedia**
*Big Data & Society, 3(1).*

### Tools für vergleichbare Daten (CSV-Format mit Zeitstempeln) aus anderen Quellen:

* [Suchinteresse im Zeitverlauf mit Google Trends](https://trends.google.com/trends/?geo=DK). Kann nach geografischen Regionen oder anderen Google-Plattformen wie YouTube, News oder Shopping gefiltert werden.
* [Publikationsaktivität zu einem Thema im Zeitverlauf in wissenschaftlichen Zeitschriften mit Scopus](https://www.scopus.com/). Hierfür ist der universitäre Login erforderlich.
* [Aktivität auf öffentlichen Facebook-Seiten im Zeitverlauf mit FacePager](https://github.com/strohne/Facepager). Hierfür muss die Software installiert werden.
