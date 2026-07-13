---
layout: single
title: Kontroversen-Mapping
header:
  image: assets/images/cover.png
---

Diese Website führt in grundlegende Methoden des Kontroversen-Mappings ein. Diese Einführung ist Teil des Seminars "Kontroverse KI" (Sommersemmester 2026, Ruhr-Universität Bochum, MA Kultur & Demokratie). 

**Ziel:** Daten sammeln, explorieren und visualisieren.

**Daten:** Zentrale Grundlage sind daten der Wikipedia, aber die Techniken und Jupyter-Notebooks sind für weitere Datentypen nutzbar. Siehe die Notebooks für weitere Quellen, wie etwa Reddit. Jenseits von Anders Munk und Mathieu Jacomy sei hier an die [Digital Methods-Initiatve verwiesen](https://www.digitalmethods.net/).

**Tools:** Contropedia, Tableau, Gephi, und [Jupyter Notebooks mit Python](nb/). Wir erschließen die Tools in den unteren Tutorials; keine weitere Vorerfahrungen sind notwendig.

## Übersicht des Workflows
```mermaid
flowchart TD
    K[Kontroverse als leitende Problematik]
    K --> K1["hot" statt cold (evtl. über Archive erschließen)]
    K --> K2[spezifisch statt allgemein]
    K --> K3[Expertenwissen fokussiert statt Allgemeinwissen]
    K --> K4[soziale Situation rückgebunden]

    K --> T[konkrete KI-Technologie und Kontroverse benennen, keine PR/Hype-Begriffe]

    T --> SC[vier Sciebo-Umfelder]

    SC --> G1[Arbeit]
    SC --> G2[Bildung]
    SC --> G3[Umwelt]
    SC --> G4[Gewalt]

    G1 --> G1a[Logbuch]
    G1 --> G1b[Forschungsmaterial 1]
    G1 --> G1c[Forschungsmaterial 2]
    G1 --> G1d[Analysen]
    G1 --> G1e[Memos]

    G2 --> G2a[Logbuch]
    G2 --> G2b[Forschungsmaterial 1]
    G2 --> G2c[Forschungsmaterial 2]
    G2 --> G2d[Analysen]
    G2 --> G2e[Memos]

    G3 --> G3a[Logbuch]
    G3 --> G3b[Forschungsmaterial 1]
    G3 --> G3c[Forschungsmaterial 2]
    G3 --> G3d[Analysen]
    G3 --> G3e[Memos]

    G4 --> G4a[Logbuch]
    G4 --> G4b[Forschungsmaterial 1]
    G4 --> G4c[Forschungsmaterial 2]
    G4 --> G4d[Analysen]
    G4 --> G4e[Memos]

    SC --> AT[Arbeitsteilung bei der Datenerhebung, pro Gruppe drei mögliche Rollen, enge Zusammenarbeit/ggf. überscheinend]

    AT --> Q1[quantitativ: Wikipedia-Datenverlauf, Versionsgeschichte und Revisionen]]
    AT --> Q2[qualitativ: verlinkte Newsartikel aus Wikipedia-Quellen, vertieftende Analyse]
    AT --> Q3[Expert:inneneninterviews]
```

## Übersicht der angestrebten Ergebnisse und benötigter Tools

[Contropedia](https://roaring-horse-7a6c46.netlify.app/network) für qualitative Analyse (Schwesterumgebung).

| # | Ergebnis | Datenquelle | Aufbereitung | Visualisierung | Interpretation | Module |
|---|---|---|---|---|---|---|
| 1 | Bearbeitungs-Zeitstrahl | Bearbeitungs-CSV | J. Notebook | TABLEAU | Annotation | 1.1, 1.2, 1.3, 1.4, 1.5 |
| 2 | Seitenaufruf-Zeitstrahl | Seitenaufrufe-CSV | J. Notebook | TABLEAU | Annotation | 1.1, 1.2, 1.3, 1.4, 1.5 |
| 3 | Hyperlink-Netzwerk | Artikelliste | J. Notebook | GEPHI | Annotation | 1.3, 1.4, 2.1, 2.3, 2.5 |
| 4 | Ko-Referenz-Netzwerk | Artikelliste | J. Notebook | GEPHI | Annotation | 1.3, 1.4, 2.1, 2.3, 2.5 |
| 5 | Artikel-Redakteur-Netz | Artikelliste | J. Notebook | GEPHI | Annotation | 1.3, 1.4, 2.2, 2.4, 2.5 |


### Tutorials Teil 1: Visualisierungen erstellen und Daten abrufen (Tableau, Toolforge und Notebook)
**[1.1. Tableau Einstieg](1.1/)**
<br>Daten mit Tableau aufbereiten und via Slides annotieren.

**[1.2. Tableau. Übung](1.2/)**
<br>Visualisierungen mit einem anderen Fokus erstellen.

**[2.1. Wikipedia scrapen](2.1/)**
<br>Kurze Einführung in die Datenerhebung von Wikipedia mit Toolforge.

**[2.2. Daten mit einem Notebook erheben](2.1/)**
<br>Tutorial für JupyterHub, um die Erhebung zu skalieren. (Jupyter Notebooks).

### Tutorials Teil 2: Netzwerke visualisieren (Gephi und Notebooks)

**[3.1. Intro Gephi](3.1/)**
<br>Einstieg in Gephi anhand eines Beispieldatensatzes.

**[3.2. Ein gewichtetes Netzwerk visualisieren. Übung](3.3/)**
<br>Gephi mit einem gewichteten Netzwerk explorieren.

**[4.1. Ein bipartites Netzwerk](3.2/)**
<br>Bipartite Netzwerke verstehen und in Gephi visualisieren.


## Weitere Resourcen
* [Jupyter notebooks](nb/)
* [Das Buch: Controversy-Mapping: A Field-Guide.](https://www.wiley-vch.de/de/fachgebiete/kunst-und-kultur/kulturwissenschaften-15cu/allg-kulturwissenschaften-15cu0/digitale-kultur-im-informationszeitalter-15cu03/controversy-mapping-978-1-5095-4450-9)
* [Weiteres Mapping an der Ruhr-Universität](https://datastories.rub.de/).
* [Für ein Bsp.-Mapping siehe etwa das Buch "Artenübergreifende Fürsorge" (Open Access](https://www.transcript-verlag.de/978-3-8376-6341-9/artenuebergreifende-fuersorge/?number=978-3-8394-6341-3))
* [Oder diesen Bericht zur Obsoleszenz bei der Deutschen Bahn mit Twitter-Mappings](https://dspace.ub.uni-siegen.de/entities/publication/6bae9010-9b48-428c-b519-c565f75d80a1)

## Lizenz
[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png