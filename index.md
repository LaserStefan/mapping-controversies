---
layout: single
title: Digital Controversy Mapping
header:
  image: assets/images/cover.png
---

Diese Website führt in grundlegende Methoden des Kontroversen-Mappings ein. Diese Einführung ist Teil des Seminars "Kontroverse KI" (Sommersemmester 2026, Ruhr-Universität Bochum, MA Kultur & Demokratie). 

**Ziel:** Daten sammeln, explorieren und visualisieren.

**Daten:** Zentrale Grundlage sind daten der Wikipedia, aber die Techniken und Jupyter-Notebooks sind für weitere Datentypen nutzbar. Siehe die Notebooks für weitere Quellen, wie etwa Reddit. Jenseits von Anders Munk und Mathieu Jacomy sei hier an die [Digital Methods-Initiatve verwiesen](https://www.digitalmethods.net/).

**Tools:** Tableau, Gephi, und [Jupyter Notebooks mit Python](nb/). Wir erschließen die Tools in den unteren Tutorials; keine weitere Vorerfahrungen sind notwendig.

## Übersicht der angestrebten Ergebnisse und benötigter Tools

| # | Ergebnis | Datenquelle | Aufbereitung | Visualisierung | Interpretation | Module |
|---|---|---|---|---|---|---|
| 1 | Bearbeitungs-Zeitstrahl | Bearbeitungs-CSV | J. Notebook | TABLEAU | Annotation | 1.1, 1.2, 1.3, 1.4, 1.5 |
| 2 | Seitenaufruf-Zeitstrahl | Seitenaufrufe-CSV | J. Notebook | TABLEAU | Annotation | 1.1, 1.2, 1.3, 1.4, 1.5 |
| 3 | Hyperlink-Netzwerk | Artikelliste | J. Notebook | GEPHI | Annotation | 1.3, 1.4, 2.1, 2.3, 2.5 |
| 4 | Ko-Referenz-Netzwerk | Artikelliste | J. Notebook | GEPHI | Annotation | 1.3, 1.4, 2.1, 2.3, 2.5 |
| 5 | Artikel-Redakteur-Netz | Artikelliste | J. Notebook | GEPHI | Annotation | 1.3, 1.4, 2.2, 2.4, 2.5 |


### Tutorials Teil 1: Visualisierungen erstellen und Daten abrufen (Tableau und Notebook)
**[1.1. Tableau Einstieg](1.1/)**
<br>Daten mit Tableau aufbereiten und via Slides annotieren.

**[1.2. Tableau Vertiefung](1.2/)**
<br>Visualisierungen mit einem anderen Fokus erstellen.

**[1.3. Datensatz erheben](1.3/)**
<br>Kurze Einführung in die Datenerhebung von und mit Wikipedia.

**[1.4. Daten mit einem Notebook erheben](1.4/)**
<br>Tutorial für JupyterHub (Jupyter Notebooks).

**[1.5. Tableau: Alles zusammenbringen](1.5/)**
<br>Vom Datensatz zur annotierten Visualisierung – Wikipedia auf eigene Faust.

### Tutorials Teil 2: Netzwerke visualisieren (Gephi und Notebooks)

**[2.1. Gephi 101](2.1/)**
<br>Einstieg in Gephi anhand eines Beispieldatensatzes.

**[2.2. Ein bipartites Netzwerk](2.2/)**
<br>Bipartite Netzwerke verstehen und in Gephi visualisieren.

**[2.3. Ein gewichtetes Netzwerk visualisieren](2.3/)**
<br>Gephi mit einem gewichteten Netzwerk explorieren.

**[2.4. Von Daten zum Netzwerk mit Table2Net](2.4/)**
<br>Mit Table2Net aus einer Wiki-Tabelle ein Netzwerk bauen.

**[2.5. Gephi: Alles zusammenbringen](2.5/)**
<br>Ein eigenes Wiki-Netzwerk von Grund auf aufbauen und analysieren.


## Weitere Resourcen
* [Jupyter notebooks](nb/)
* [Das Buch: Controversy-Mapping: A Field-Guide.](https://www.wiley-vch.de/de/fachgebiete/kunst-und-kultur/kulturwissenschaften-15cu/allg-kulturwissenschaften-15cu0/digitale-kultur-im-informationszeitalter-15cu03/controversy-mapping-978-1-5095-4450-9)
* [Weiteres Mapping an der Ruhr-Univesität](https://datastories.rub.de/).
* [Für ein Bsp.-Mapping siehe etwa das Buch "Artenübergreifende Fürsorge" (Open Access](https://www.transcript-verlag.de/978-3-8376-6341-9/artenuebergreifende-fuersorge/?number=978-3-8394-6341-3)
* [Oder diesen Bericht zur Obsoleszenz bei der Deutschen Bahn mit Twitter-Mappings](https://dspace.ub.uni-siegen.de/entities/publication/6bae9010-9b48-428c-b519-c565f75d80a1)

## Lizenz
[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png