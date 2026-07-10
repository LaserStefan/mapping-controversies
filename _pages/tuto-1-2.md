---
permalink: /1.2/
layout: single
title: 1.2. Andere Daten mit Tableau darstellen
---
# Tool #1

Das ist eine Übung für Zuhause: eine zweite Visualisierung.

**Ziele**
* Andere Daten erzählen andere Geschichten: der Vergleich
* Eine Auswahl an Schwerpunkten ausprobieren
* Simply: mal eine andere Visualisierung bauen

# Der Fall KI

Wir bleiben bei dem Thema KI-Risiken mit den beiden Artikeln
* [AI Safety](https://en.wikipedia.org/wiki/AI_safety)
* [AI Risk](https://en.wikipedia.org/wiki/Existential_risk_from_artificial_intelligence)

# Daten

CSV herunterladen:

<center><a href="../assets/data/1-2/wikipedia-edits-1-2.csv">
	<i class="fas fa-file-csv" style="font-size:5em"></i><br>
	wikipedia-edits-1-2.csv
</a><br><br></center>

Die Datei zeigt Wikipedia-Edits und diverse Meta-Daten, erzeugt mit einem Notebook, das wir noch kennenlernen werden.

# Video tutorial

Das ist ein Video mit einem anderen Beispiel, aber das Prinzip ist gleich.

{% include video id="1LcsxtNaNdk" provider="youtube" %}

# Tableau

Wie in [tutorial 1.1](../1.1/) Beschrieben: Daten hereinladen. Es gibt aber mehr Daten, etwa geographische.

[
	![Data table](../assets/images/1-2/data-table.png)
](../assets/images/1-2/data-table.png)

# Visualize a timeline of revisions

Nun interessieren wir uns wieder für Zeitläufte, aber mit einem Blick auf Edits.

Zu beachten ist, dass man auch „Größe“ oder „Benutzer in das Feld „Zeilen“ ziehen kann, wenn man die Größe der Überarbeitungen (Anzahl der hinzugefügten oder entfernten Zeichen) oder die Anzahl der Benutzer, die die Überarbeitungen in einem bestimmten Monat vorgenommen haben, darstellen möchte.

Es sieht alles aus wie im [Tutorial 1.1](../1.1/), die Daten repräsentieren jedoch etwas völlig anderes (Bearbeitungen statt Aufrufe), was Fragen aufwirft wie:
* Gibt es im Zeitverlauf einen Zusammenhang zwischen der Anzahl der Aufrufe und der Anzahl der Bearbeitungen?
* Sollten wir einen solchen Zusammenhang erwarten? Warum oder warum nicht?
* Erzählen die Bearbeitungen eine andere Geschichte als die Aufrufe? Und wenn ja, wie sieht diese Geschichte aus?

Außerdem ist zu beachten, dass die Daten zu den *Bearbeitungen* weiter in die Vergangenheit zurückreichen als die Daten zu den *Aufrufen*. Das liegt daran, dass Wikipedia erst seit 2015 Seitenaufrufe als abrufbaren Datenpunkt bereitstellt, während Aufzeichnungen aller Bearbeitungen seit der Gründung der Plattform verfügbar sind. Was wir hier sehen, ist der Beginn zweier Artikel aus den Jahren 2006 bzw. 2012.
# In Tableu annotieren

* Exportieren 
* Importieren im Slide-Programm
* Merkmale (nach Recherche) hervorheben
* Exportieren 

Diesmal haben wir jedoch weitere Möglichkeiten, die "Spikts" zu interpretieren. Wir können uns etwa ansehen, was die Editoren in einem bestimmten Zeitraum hinzugefügt oder entfernt haben. Oben auf jeder Wikipedia-Seite befindet sich eine Registerkarte mit dem Namen „Versionsgeschichte anzeigen“. Hier gibt es die Informationen, die wir aus der Contropedia kennen.
# Weitere Möglichkeiten 
Man kann weitere Feinheiten untersuchen, etwa die Frage, ob Editoren unterschiedlich aktiv waren:

[
	![Ranked editors](../assets/images/1-2/tableau-ranked-list-editors.png)
](../assets/images/1-2/tableau-ranked-list-editors.png)

Oder wo sie herkommen:
[
	![Map](../assets/images/1-2/tableau-geographical-map.png)
](../assets/images/1-2/tableau-geographical-map.png)

Bitte beachten: Wenn „Breitengrad“ und „Längengrad“ in die Felder „Spalten“ und „Zeilen“ gezogen wird, versucht Tableau möglicherweise, einen Durchschnittswert zu berechnen und diesen darzustellen. Dies führt dazu, dass alle Bearbeiter als ein einziger Knoten irgendwo in der Mitte der Karte dargestellt werden. Um dies zu beheben, müssen in den Feldern „Spalte“ und „Zeile“ ausgewählt und im Dropdown-Menü „Dimension“ geklickt werden.

Anmerkung: Nicht alle Editors verfügen über Breiten- und Längengradangaben (in ihren Profilen). Das zeigt bereits die Datentabelle. Der Grund dafür ist, dass Wikipedia die IP-Adressen anonymer Nutzer offenlegt und IP-Adressen geolokalisiert werden können. Kurz gesagt visualisieren wir hier den Standort aller anonymen Mitwirkenden. Tableau weist in der Visualisierung darauf hin, dass einige der Datenpunkte nicht auf der Karte platziert wurden.
# Ergebnisse

Im Ordner speichern:
* Annotierte Versionen (JPEG or PNG) 
* Die Tableu Datei mit den Daten, wie aufbereitet 
---

### Literaturgrundlage

* The intricacies of Wikipedia and the different ways in which the platform may be reappropriated for controversy analysis are covered in *Weltevrede, E., & Borra, E. (2016).* **Platform affordances and data practices: The value of dispute on Wikipedia**
*Big Data & Society, 3(1).*
