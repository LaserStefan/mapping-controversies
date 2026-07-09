---
permalink: /2.1/
layout: single
title: 2.1. Daten mit Toolforge scrapen
---
# Tool-Sitzung #2

**Ziele**
* Einen Datensatz mit einem Tool aus einer Online-Quelle *sammeln*
* Verstehen, dass das Tool eine API aufruft, um Daten zu bekommen

# Einen Datensatz sammeln

Wir nutzen Toolforge [PageViews](https://pageviews.toolforge.org), um einen Datensatz zu sammeln, wie wir ihn schon für die Zeitachse der Seitenaufrufe in [Tutorial 1.1](../1.1/) verwendet haben.

* Man geht auf [PageViews](https://pageviews.toolforge.org)
* Man stellt die Daten für zwei Wikipedia-Artikel eigener Wahl dar:
* Dabei sollte man auf die richtigen Einstellungen achten:
	* Bei ```Dates``` wählt man den Zeitraum vom 01.07.2015 bis heute (denn davor gibt es keine Daten)
	* Bei ```Date type``` wählt man ```Daily```. Tableau kann die Daten nämlich problemlos zu Monaten oder Jahren zusammenfassen – je genauer die Rohdaten, desto besser.
* Man lädt den Datensatz herunter, indem man im Dropdown-Menü ```Download``` die Option ```CSV``` auswählt.

Das Tool funktioniert, indem es die Programmierschnittstelle (API) von Wikipedia aufruft. Der [Endpoint für Seitenaufrufe](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews) bietet eigentlich noch mehr Möglichkeiten, als das Tool anzeigt, aber mit dem Tool lässt sich die API besonders einfach nutzen. Im nächsten Tutorial schauen wir uns an, wie man die API direkt per Skript anspricht.

---

### Ähnliche Tools und Datenformat (CSV mit Zeitmarken) von anderen Quellen:
Suchinteresse im Zeitverlauf mit Google Trends. Man kann das übrigens nach geografischen Regionen filtern oder auch auf andere Google-Plattformen wie YouTube, News oder Shopping beziehen.
Publikationsaktivität zu einem Thema im Zeitverlauf in wissenschaftlichen Zeitschriften mit Scopus. Dafür braucht man allerdings den Uni-Login.
Aktivität auf öffentlichen Facebook-Seiten im Zeitverlauf mit FacePager. Dafür muss man die Software erst installieren.

### Literatur

* Scraping, calling und allgemein das Arbeiten mit APIs wird diskutiert in: **Chapter 6: Collecting and curating digital records** of *Venturini, T. & Munk, A.K. (2021). Controversy Mapping: A Field Guide.*
