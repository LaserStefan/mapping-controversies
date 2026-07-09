---
permalink: /3.2/
layout: single
title: 3.2. Ein bipartites Netzwerk
---

# Übung zur Tool-Sitzung #3


**Ziele**
* Ein **bipartites** Netzwerk visualisieren
* Mit **Zentralitätsmaßen** experimentieren
* Wichtige Knoten annotieren

# Daten

Diese GEXF herunterladen:

<center><a href="../assets/data/3-2/wikipedia-articles-editors-network.gexf">
	<i class="fas fa-file" style="font-size:5em"></i><br>
	wikipedia-articles-editors-network.gexf
</a><br><br></center>

Es handelt sich um das Netzwerk aus Artikeln und Editoren, das entsteht, wenn ein Editor zu einem der 139 Wikipedia-Artikel der Kategorie [energy conversion](https://en.wikipedia.org/wiki/Category:Energy_conversion) beigetragen hat (ohne Unterkategorien).

Die Datei wurde erzeugt, indem diese [<i class="fas fa-file-csv"></i>&nbsp;CSV-Datei](../assets/data/3-2/energy-conversion-category-depth-0.csv) in folgendes Skript eingespeist wurde: [🍄&nbsp;Wikipedia articles to articles and editors network](https://colab.research.google.com/github/jacomyma/mapping-controversies/blob/main/notebooks/Wikipedia_articles_to_articles_and_editors_network.ipynb).

# Video-Tutorial

Zuerst dieses Tutorial ansehen. Es verwendet die gerade heruntergeladenen Daten. Dieselben Anweisungen finden sich unten auch als Text.

{% include video id="de_sAxlVTNQ" provider="youtube" %}

# Das Netzwerk schnell visualisieren

Das Netzwerk schnell visualisieren und die Knoten nach dem Attribut ```type``` einfärben. An dieser Stelle nicht zu viel Zeit investieren. Das Netzwerk ist **groß**, und es muss zunächst reduziert werden.

Zu beachten:
* Jeder Knoten kann einen von zwei Typen haben: ```article``` oder ```editor```
* Jede Kante verbindet einen Artikel mit einem Editor. Anders als beim Hyperlink-Netzwerk aus dem vorherigen Tutorial gibt es keine Kanten zwischen Artikeln. Und auch keine Kanten zwischen Editoren.
* Die Kanten sind nicht gerichtet (man könnte sagen, ein Editor überarbeitet einen Artikel, oder ein Artikel wird von einem Editor überarbeitet, aber anders als beim Hyperlink ist hier nicht offensichtlich, was auf was verweist).

Das sind die Merkmale eines **bipartiten** Netzwerks.

Modularitäts-Clustering funktioniert bei bipartiten Netzwerken nicht gut, da deren Struktur sich in der Regel nicht auf dieselbe Weise clustert. Stattdessen liegt der Fokus hier auf Zentralitätsmaßen.

[
	![Network](../assets/images/1-9/preview.png)
](../assets/images/1-9/preview.png)


# Das Netzwerk filtern

99,67 % dieses Netzwerks bestehen aus Editoren. Wenig überraschend, da jeder Artikel von vielen Personen bearbeitet wird. Die weniger interessanten Editoren – die am schwächsten vernetzten – werden entfernt.

Im ```Filters```-Panel rechts folgenden Filter aufsuchen:
```
Filters panel > Topology > Degree Range
```
Diesen Filter per Drag-and-drop auf das Zielsymbol darunter, unter ```Queries```, ziehen. Unten erscheint ein Unterpanel für den Filter.

In diesem Unterpanel mit dem Titel ```Degree Range Settings``` befindet sich ein Schieberegler mit zwei Griffen, der einen Wertebereich auswählt. Auf den linken Wert doppelklicken (standardmäßig ```1```), ```3``` eingeben und **```Enter``` drücken** (sonst wird der Wert nicht übernommen).

Nun auf den ```Filter```-Button unten rechts klicken. Dadurch sollte das Netzwerk gefiltert werden. Das Panel sollte danach so aussehen:

[
	![Filter panel](../assets/images/1-9/filter.png)
](../assets/images/1-9/filter.png)

**Was bedeutet das?** Beim Filtern werden manche Knoten samt der mit ihnen verbundenen Kanten ausgeblendet. Der verwendete Filter behält nur Knoten mit einem bestimmten *Degree*-Wertebereich, also einer bestimmten Anzahl an Nachbarn. In diesem Fall wurden nur Knoten mit 3 oder mehr Nachbarn beibehalten.

Dadurch wurde das Netzwerk auf nur noch 5,12 % der Knoten und 24,38 % der Kanten reduziert. Es hat nun eine handlichere Größe: 2.131 Knoten und 13.520 Kanten.

Anmerkung: Filter wirken auf beide Knotentypen, Editoren wie Artikel gleichermaßen, aber da Artikel viele Nachbarn haben, blieben sie in diesem Fall unangetastet. Entfernt wurden ausschließlich Editoren.


# Ein Layout anwenden und speichern

Nun werden die ausgeblendeten Knoten vollständig gelöscht, um Rechenleistung freizugeben.
* Bei Bedarf ein Layout anwenden, da das Netzwerk nun gespeichert wird.
* Im Menü auf ```File > Export > Graph file...``` klicken.
* Als Dateityp ```GEXF``` wählen.
* Unten im Fenster auf ```Visible only``` klicken.
* Datei benennen und irgendwo speichern.

Gephi kann nun geschlossen und die exportierte Datei erneut geöffnet werden. Es sollte etwa Folgendes zu sehen sein:

[
	![Network](../assets/images/1-9/filtered-network.png)
](../assets/images/1-9/filtered-network.png)


Falls etwas schiefgegangen ist, hier die [<i class="fas fa-file"></i>&nbsp;gefilterte GEXF](../assets/data/3-2/wikipedia-articles-editors-network-filtered.gexf).


# Zentralitätsmaße berechnen

Im ```Statistics```-Panel rechts ```Network diameter``` ausführen.

Der Netzwerkdurchmesser gibt an, wie viele Kanten zwischen den beiden am weitesten voneinander entfernten Knoten liegen (in diesem Fall ergibt sich der Wert 5). Wichtiger ist jedoch, dass dabei gleichzeitig einige *Zentralitätsmaße* berechnet werden, darunter:
* *Betweenness centrality*: Je höher, desto mehr fungiert der Knoten als Brücke, als Vermittler.
* *Closeness centrality*: Je höher, desto näher liegt der Knoten im Durchschnitt an den anderen Knoten.

Diese Zentralitätsmaße als Knotengröße visualisieren. So sieht es mit Größen von 1 bis 10 aus.

**Closeness centrality**
[
	![Network](../assets/images/1-9/closeness.png)
](../assets/images/1-9/closeness.png)

**Betweenness centrality**
[
	![Network](../assets/images/1-9/betweenness.png)
](../assets/images/1-9/betweenness.png)

Sind das dieselben Ergebnisse? Macht es einen Unterschied, ob ein Knoten ein Artikel oder ein Editor ist?

# Eine Visualisierung annotieren

Das Netzwerk mit der Betweenness Centrality ist das interessanteste. Die Netzwerkkarte exportieren und in Google Slides annotieren.

Gefragt ist eine **Annotation der wichtigen Knoten** (die Cluster können vorerst ignoriert werden). Ein paar Tipps:
* Eine hohe Betweenness Centrality bedeutet, dass der Knoten eine Brücke ist, ein Vermittler zwischen vielen anderen Knoten – anders gesagt ein *Broker*, ein obligatorischer Durchgangspunkt.
* Da dieses Netzwerk bipartit ist, lässt sich sagen: Die Broker sind die Knoten, die am meisten dazu beitragen, den jeweils anderen Knotentyp zu verbinden. In diesem Sinne sind sie strukturell wichtig. Zum Beispiel sind die Editoren mit der höchsten Betweenness Centrality diejenigen, die am meisten zur *Verbindung* von Artikeln beitragen.
* In diesem Netzwerk entspricht jede *Verbindung* einer Bearbeitung, also dem *Akt des Editierens* eines Artikels.
* Broker-Editoren sind also jene, die zu den unterschiedlichsten Artikeln beitragen, und Broker-Artikel sind jene, bei denen die Beitragenden am unterschiedlichsten sind.

Die Annotationen sollten die Natur der Daten korrekt widerspiegeln.

# Erstellte Dokumente

Für die spätere Weitergabe sollte man Folgendes aufbewahren:
* Das annotierte Netzwerk (JPEG oder PNG)

---

### Bezug zu den Kurslektüren

* Die Besonderheiten von Wikipedia und die verschiedenen Wege, wie die Plattform für die Kontroversenanalyse genutzt werden kann, werden behandelt in *Weltevrede, E., & Borra, E. (2016).* **Platform affordances and data practices: The value of dispute on Wikipedia**
*Big Data & Society, 3(1).*
* Die Prinzipien und Konzepte der Visual Network Analysis (VNA) werden behandelt in **Kapitel 2: What is visual network analysis** in *Jacomy, M. (2021). Situating Visual Network Analysis*
* Sowie in **Kapitel 7: Visual network analysis** in *Venturini, T. & Munk, A.K. (2021). Controversy Mapping: A Field Guide*
