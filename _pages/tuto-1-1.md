---
permalink: /1.1/
layout: single
title: 1.1. Einführung in Tableau und Visualisierung
---
# Tool-Sitzung #1

**Ziele**
* Arbeit mit **Tableau Desktop**, einer populären Visualisierungs-Software
* Die Annotation eines Ergebnisses

**Was gebraucht wird**
* Tableau Desktop 
* Zugang zu einer Slide-Software: Office 

# Der Fall

Zunächst geht es darum, grundlegend zu verstehen, wie mit Tableu Wikipedia-Daten annotiert werden können.

Als Beispiel nehmen wir Zeitleisten, und zwar zwei spezifische AI-Technologien im Vergleich.

# Data

Download:

<center><a href="../assets/data/1-1/pageviews-20210101-20260331.csv">
	<i class="fas fa-file-csv" style="font-size:5em"></i><br>
	pageviews-20210101-20260331.csv
</a><br><br></center>

Enthalten sind Daten von Wikipedia von 2021 to 2026.
Dieses [tool](https://pageviews.toolforge.org/?project=en.wikipedia.org&platform=all-access&agent=user&redirects=0&start=2015-07&end=2021-12&pages=Space-based_solar_power|Thorium-based_nuclear_power) wurde benutzt, worauf wir noch zurückkommen werden in der nächsten Sitzung.

# Video
Neben der lokalen Vorbereitung (auf Deutsch) gibt es ein englischsprachiges Video mit Erklärungen von Mathieu.

{% include video id="5XEdQgHgMdU" provider="youtube" %}

# Daten in Tableau laden

* Tableau Desktop öffnen
* Die CSV-Datei öffnen. Dazu aufrufen: "To a File" und dann: "Text file", hier die entsprechende Datei auswählen: ```pageviews-20210101-20260331```
* Sind die Daten richtig geladen? Sind drei Spalten zu sehen. Wenn nicht, müssen [die Einstellungen angepasst werden](https://help.tableau.com/current/pro/desktop/en-gb/examples_text.htm#set-text-file-options).
* Ist der Type der Spalte korrekt? Erste Spalte: Datum/dateGgf. [muss der Typ gewechselt werden](https://help.tableau.com/current/pro/desktop/en-us/datafields_typesandroles_datatypes.htm).

Ungefähr so sehen Ergebnisse aus.

[
	![Parsing data in Tableau](../assets/images/1-1/MappingControversies_TutorialScreenshots_TableauParsing.svg)
](../assets/images/1-1/MappingControversies_TutorialScreenshots_TableauParsing.svg)


# Visualisierung als Timeline

* Unten auf die Registerkarte „Blatt 1“ klicken, um mit der Erstellung Ihrer ersten Visualisierung zu beginnen.
* Links unter „Tabellen“ sind die Datenspalten zu sehen, die wir gerade parst haben: „Datum“, „AI risk“ und „AI safety“. Drag & Drop auf das Blatt ziehen.
* Oben auf dem Blatt sind zwei horizontale Felder namens „Spalten“ und „Zeilen“ zu sehen. Das Ziehen der Daten in jedes dieser Felder legt fest, was auf der horizontalen und vertikalen Achse Ihrer Visualisierung dargestellt werden soll. Da wir eine Zeitleiste erstellen, ziehen wir zunächst „Datum“ in das Feld „Spalten“ (dies stellt die Zeit auf der horizontalen Achse dar).
* Jetzt eine der beiden Datenzeilen in das Feld „Zeilen“ ziehen, AI risk oder Safety. So sollte eine Zeitleiste zu sehen sein. Man kann auch beide in das Feld „Zeilen“ ziehen, um zwei Zeitleisten zum Vergleich zu erstellen.
* Da Tableau nicht mitgeteilt wurde, wie die Seitenaufrufe aggregiert werden sollen – nach Tagen, Wochen, Quartalen oder Jahren –, trifft das Programm eine willkürliche Auswahl. Das sollte je nach Bedarf geändernt werden. Siehe unter „Spalten“ das Dropdown-Menü für „Datum“:

[
	![Setting date in Tableau](../assets/images/1-1/MappingControversies_TutorialScreenshots_TableauDateSetting.svg)
](../assets/images/1-1/MappingControversies_TutorialScreenshots_TableauDateSetting.svg)

* Es stehen mehrere Einstellungen zur Auswahl. Es gibt zwei Wege. Standardmäßig fasst Tableau lediglich alle Daten für einen Monat oder eine Woche zusammen, beispielsweise für den August, ohne dabei das jeweilige Jahr zu berücksichtigen. Wir sollten die Ergebnisse entsprechend sortieren.


# Exportieren als Bild

Als statistisches Bild über das Menu exportieren:

```
Worksheet > Export > Image...
```

Als ```.PNG``` speichern

# In ein Präsentationsprogramm laden
Der letzte Schritt besteht darin, die Zeitleiste mit Anmerkungen zu versehen. Das Ziel ist es, dem Leser durch kurze Erläuterungen zu helfen, die Spitzen bei den Seitenaufrufen zu verstehen. Folge [diesem Template](https://laserstefan.github.io/mapping-controversies/assets/data/1-1/MappingControversies_Annotation.pptx) in einem Slide-Programm. 

[
	![Partially annotated timeline in Google Slides](../assets/images/1-1/MappingControversies_AnnotationExamples_PageViews_SpaceBasedSolar.svg)
](../assets/images/1-1/MappingControversies_AnnotationExamples_PageViews_SpaceBasedSolar.svg)

Ziel: Ausreißer ("Spikes") annotieren. Warum gibt es Ausschläge? 

<div class="notice--warning"><i class="fas fa-exclamation-triangle"></i>&nbsp;<b>WARNUNG:</b> Für einige der Spikes lässt sich ggf. in den Nachrichten keine schlüssige Erklärung finden. </div>


# Exportieren

Exportieren als JPEG oder PNG.

# Ergebnis

Datei speichern für spätere Nutzung.
* Die annotierte Datei (JPEG oder PNG)

---

### Weitere Resources

* [Tableau 101 in 20 Minuten](https://www.youtube.com/watch?v=jEgVto5QME8)
* [Tableau viz mit Google Slides](https://docs.google.com/presentation/d/1WFBRnr-USNOybHRmKWfGwpOffqFH8PB_SfzDQuBwKI0/edit?usp=sharing), anhand des Bsp. "OK Boomer" auf Twitter.

