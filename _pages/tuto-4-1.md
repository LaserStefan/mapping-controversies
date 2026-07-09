---
permalink: /4.1/
layout: single
title: 4 Ein eigenes Netzwerk mit SeeAlsology scrapen
---
# Tool-Sitzung #4


**Ziele**
* **SeeAlsology** als Tool kennenlernen
* Ein Netzwerk exportieren

# Fall

Weiterhin geht es um das Thema energy conversion, mit Wikipedia als Hauptdatenquelle.

# Daten

Diese CSV herunterladen:

<center><a href="../assets/data/4-1/wikipedia-URL-energy-conversion.csv">
	<i class="fas fa-file-csv" style="font-size:5em"></i><br>
	wikipedia-URL-energy-conversion.csv
</a><br><br></center>

Sie enthält 139 Wikipedia-Seiten-URLs zum Thema energy conversion (ohne Unterkategorien). Wie bereits gesehen, ist diese Datei der Ausgangspunkt des Protokolls.

<div class="notice">Anders als eine ähnliche Datei aus einem früheren Tutorial enthält diese Seiten-URLs statt Titel. Außerdem hat sie keine Kopfzeile. Genau das benötigt SeeAlsology.</div>

# SeeAlsology

[SeeAlsology](https://densitydesign.github.io/strumentalia-seealsology/) ist ein Online-Tool, das ein Netzwerk aus Wikipedia-Seiten und deren Hyperlinks erstellt. Standardmäßig berücksichtigt es nur die Hyperlinks im Abschnitt „See also“ am Ende einer Wikipedia-Seite, daher der Name. Es gibt aber eine Einstellung, um alle Hyperlinks zu erfassen (die hier verwendet wird).

* [SeeAlsology](https://densitydesign.github.io/strumentalia-seealsology/) im Browser öffnen
* Die CSV-Datei in einer Tabellenkalkulation oder einem Texteditor öffnen und die Liste der URLs in SeeAlsology einfügen
* Folgende Einstellungen verwenden:
	* ```Distance```: ```0``` (dadurch bezieht das Tool ausschließlich Hyperlinks von den eingegebenen Seiten)
	* ```Parent links```: ```deaktiviert``` (dadurch bezieht das Tool ausschließlich Links von den eingegebenen Seiten)
	* ```Take all links```: ```aktiviert``` (dadurch erfasst das Tool alle auf den eingegebenen Seiten gefundenen Hyperlinks)

Moment, **sind die richtigen Einstellungen gewählt?**

Gut, jetzt kann auf ```Start crawling``` geklickt werden.

Beobachten, wie das Netzwerk wächst, während sich das Tool durch die 139 Startseiten arbeitet.

Sobald das Tool fertig ist, kann das entstandene Netzwerk als .GEXF-Datei heruntergeladen werden. Falls das nicht funktioniert, gibt es hier eine Version des Ergebnisses [<i class="fas fa-file"></i>&nbsp;hier](../assets/data/4-1/seealsology-network.gexf).

# In Gephi visualisieren

**Erinnerung:** Wer Gephi nicht installiert hat (oder Tutorial 3.1 noch nicht gemacht hat), kann stattdessen [Gephi Lite](https://gephi.org/gephi-lite/) im Browser verwenden: auf „Open a local file“ klicken, die GEXF-Datei hochladen, dann per Zoom und Pan durch das Netzwerk navigieren.

Das entstandene Netzwerk in Gephi öffnen und Folgendes beobachten:
* Es gibt deutlich mehr Knoten in diesem Netzwerk als in dem aus [Tutorial 3.1](../3.1/) mit einem ähnlichen Datensatz. Das liegt daran, dass SeeAlsology auch die nächste Ebene an Seiten einbezieht, die von den Startseiten aus „gesehen“ wurden. Die Startseiten sind rot eingefärbt, die „gesehenen“ Seiten blau.
* Um die Seiten zu entfernen, die keine Startseiten sind, kann das Netzwerk nach Outdegree gefiltert werden. Das Minimum auf 1 setzen und filtern – dadurch bleiben nur Seiten übrig, die tatsächlich nach ausgehenden Links durchsucht wurden.

# Das Protokoll prüfen

Prüfen, ob das Protokoll eingehalten wurde. **Der Schritt „ANNOTATE“ muss in diesem und den folgenden Tutorials nicht durchgeführt werden**, außer im letzten. Trotzdem sollte man beachten, dass es gute Praxis ist, die Annotation im Protokoll zu erwähnen.

# Erstellte Dokumente

Für die spätere Weitergabe sollte man Folgendes aufbewahren:
* Die (nicht annotierte) Netzwerkkarte (JPEG, PNG oder PDF)

---

### Tools für vergleichbare Daten (GEXF bzw. GDF) anderer Quellen:

* Netzwerke von YouTube-Kanälen oder YouTube-Videos, verbunden über ihre Ähnlichkeit (gemessen an den algorithmischen Empfehlungen), mit den [YouTube Data Tools](https://tools.digitalmethods.net/netvizz/youtube/). Benötigt eine Liste von Video- oder Kanal-IDs als Input.
* Netzwerke wissenschaftlicher Publikationen, verbunden über Schlagworte oder Zitationen, mit [ScienceScape](http://medialab.github.io/sciencescape/). Benötigt einen vollständigen Export aus Scopus als Input.
