---
permalink: /3.1/
layout: single
title: 3.1. Gephi-Einführung
---
# Too #3

**Ziele**
* Lernen, wie man **Gephi** benutzt
* Ein gerichtetes Netzwerk **erkunden**
* Eine **Netzwerkkarte** exportieren
* **Cluster** annotieren

**Benötigt wird**
* Gephi, installiert auf dem eigenen Rechner (oder als Plan B [Gephi Lite](https://gephi.org/gephi-lite/) im Browser)

# Daten

Diese GEXF herunterladen:

<center><a href="../assets/data/3-1/energy-conversion-wiki-cat-depth-1.gexf">
	<i class="fas fa-file" style="font-size:5em"></i><br>
	energy-conversion-wiki-cat-depth-1.gexf
</a><br><br></center>

Sie enthält 787 Wikipedia-Seiten zum Thema energy conversion (1 Ebene an Unterkategorien), verbunden durch ihre Hyperlinks.

*Hinweis: Dieses Netzwerk lässt sich erzeugen, indem man zunächst mit dem Notebook [🍉&nbsp;Wikipedia category to article list](https://colab.research.google.com/github/jacomyma/mapping-controversies/blob/main/notebooks/Wikipedia_category_to_article_list.ipynb) alle Seiten der Kategorie abruft und diese Liste dann in ein weiteres Notebook einspeist: [🍣&nbsp;Wikipedia articles to hyperlinks network (slow and clean)](https://colab.research.google.com/github/jacomyma/mapping-controversies/blob/main/notebooks/Wikipedia_articles_to_hyperlinks_network_slow_and_clean.ipynb) (Rechenzeit ca. 10 Minuten). Mit zwei Ebenen an Unterkategorien ergeben sich 3.629 Artikel, was für dieses Tutorial etwas viel wäre. Hier trotzdem die [<i class="fas fa-file"></i>&nbsp;Datei](../assets/data/3-1/energy-conversion-wiki-cat-full.gexf).*

# Gephisto ausprobieren

Als Einstieg in die Netzwerkvisualisierung kann man [Gephisto](https://jacomyma.github.io/gephisto/) ausprobieren.

[
	![Gephisto](../assets/images/1-8/gephisto.png)
](https://jacomyma.github.io/gephisto/)

Dieses Tool erstellt eine Netzwerkkarte mit einem Klick, trifft dabei aber, da es nicht erraten kann, was man möchte, eigene Entscheidungen. Das Ergebnis ist daher nicht immer besonders brauchbar. Man kann es aber jederzeit erneut versuchen. Es lassen sich Bilder wie dieses erzeugen:

[
	![Network](../assets/images/1-8/gephisto-output.png)
](../assets/images/1-8/gephisto-output.png)

Weiter geht es mit einem flexibleren Tool: Gephi (und seiner „Lite“-Version).

# Hinweis zu Gephi Lite

[Gephi Lite](https://gephi.org/gephi-lite/) ist die Browser-Version von Gephi und benötigt keine Installation. Sie kommt mit so großen Netzwerken wie die Desktop-Version nicht zurecht, bietet aber im Wesentlichen dieselben Funktionen, wenn auch in einer etwas anderen Benutzeroberfläche.

**Alles, was in diesem und den folgenden Tutorials mit Gephi gemacht wird, lässt sich auch mit Gephi Lite umsetzen**, auch wenn hier durchgehend das reguläre Gephi (also die Desktop-App) als Referenz verwendet wird. In Gephi Lite muss man sich unter Umständen etwas umschauen, um sich zurechtzufinden (dafür ist die Oberfläche dort aber auch einfacher).

[
	![Gephisto](../assets/images/1-8/gephi-lite.png)
](https://gephi.org/gephi-lite/)

# Gephi-Video-Tutorials

**Wer Gephi noch nicht installiert hat**, lädt sich die aktuellste Version von der Website herunter: [Gephi.org](https://gephi.org/).

**Diese beiden Videos ansehen**, die zeigen, wie man mit Gephi ein Netzwerk visualisiert (insgesamt 15 Minuten). Am besten versucht man, das Gezeigte mit dem gerade heruntergeladenen Netzwerk nachzuvollziehen. Da die eigene Gephi-Version neuer ist, wird man einige kleinere Unterschiede bemerken.

{% include video id="YM_37z_uURM" provider="youtube" %}

{% include video id="0LqY8OfSsKE" provider="youtube" %}

# Das Netzwerk visualisieren

Mit Gephi eine Netzwerkkarte erstellen.

Den Force-Atlas-2-Algorithmus mit den Standardeinstellungen anwenden, aber mit zwei Änderungen:
* ```Stronger gravity``` aktivieren
* ```Gravity``` auf 0.05 setzen

Diese Änderungen sorgen dafür, dass unverbundene Knoten („Inseln“) nicht zu weit abdriften, was später Probleme verursachen würde.

<div class="notice--info"><b>Tipp:</b> Wenn die Knoten zu stark zittern, lässt sich das durch Senken der Einstellung <code>Tolerance (speed)</code> beruhigen.</div>

Der Algorithmus muss manuell gestoppt werden, sobald er konvergiert ist (einfach abschätzen, wenn sich nichts mehr nennenswert bewegt).

[
	![Network](../assets/images/1-8/gephi-01.png)
](../assets/images/1-8/gephi-01.png)

<div class="notice--warning"><i class="fas fa-exclamation-triangle"></i>&nbsp;Die eigene Knotenanordnung wird abweichen, da das Layout nicht deterministisch ist.</div>

Im ```Statistics```-Panel den ```Modularity```-Algorithmus mit Standardeinstellungen ausführen. Er erkennt Cluster.

Die Knoten einfärben, um die Cluster visuell hervorzuheben. Im ```Appearance```-Panel auf ```Nodes``` klicken, dann auf das ```Color```-Symbol (eine Palette), dann auf ```Partition``` klicken und in der Dropdown-Liste ```Modularity Class``` auswählen. Danach unten im Panel auf ```Apply``` klicken. Dadurch wird jeder Knoten entsprechend dem per Modularitäts-Clustering erkannten Cluster eingefärbt.

[
	![Network](../assets/images/1-8/gephi-02.png)
](../assets/images/1-8/gephi-02.png)

<div class="notice--warning"><i class="fas fa-exclamation-triangle"></i>&nbsp;Die eigenen Cluster werden ebenfalls abweichen, da auch der Modularitäts-Clustering-Algorithmus nicht deterministisch ist.</div>

Die Knotengröße als Funktion des Indegrees festlegen (Anzahl der von anderen Knoten eingehenden Kanten): im ```Appearance```-Panel auf ```Nodes``` klicken, dann auf das ```Size```-Symbol (die drei Kreise), dann auf ```Ranking``` klicken, in der Dropdown-Liste ```In-Degree``` auswählen, ```Min size``` auf ```3``` und ```Max size``` auf ```15``` setzen, danach auf ```Apply``` klicken.

[
	![Network](../assets/images/1-8/gephi-03.png)
](../assets/images/1-8/gephi-03.png)

## Bonus
Wer sich sicher genug fühlt, kann zusätzlich Folgendes ausprobieren:
* Eine andere Farbpalette für die Modularity Class erzeugen.
* Das Force-Atlas-2-Layout mit aktiviertem ```LinLog```-Modus anwenden, was ein deutliches Absenken der ```Scaling```- und ```Gravity```-Werte erfordert.
* Das Force-Atlas-2-Layout mit aktiviertem ```Prevent Overlap``` als Feinschliff anwenden, um die Knoten besser voneinander zu trennen.
* Sofern sich die Beschriftungen nicht zu stark überlappen, lässt sich alternativ das Layout ```Label Adjust``` nutzen, um die Labels künstlich auseinanderzuziehen.
* Knotenbeschriftungen mit dem ```Size mode```-Schalter auf ```Node size``` anzeigen (das schwarze A in der unteren Leiste).

[
	![Network](../assets/images/1-8/gephi-04.png)
](../assets/images/1-8/gephi-04.png)

# Ein Bild exportieren

Nun wird ein PNG-Bild des Netzwerks exportiert.

* Zur ```Preview```-Seite wechseln (dritter Button oben in Gephi)
* In der Dropdown-Liste die Voreinstellung ```Default curved``` wählen (gebogene Kanten eignen sich für gerichtete Netzwerke)
* Unten im Seitenpanel auf ```Refresh``` klicken

An dieser Stelle sollte etwa Folgendes zu sehen sein:

[
	![Network](../assets/images/1-8/gephi-05.png)
](../assets/images/1-8/gephi-05.png)

Es fällt auf, dass es so viele Beschriftungen gibt, dass sie sich nicht mehr richtig lesen lassen. Dem wird durch eine Anpassung der Schriftgröße begegnet.

* In der ```Settings```-Seitenleiste im Bereich ```Node Labels``` sicherstellen, dass ```Proportional size``` aktiviert ist (größere Knoten erhalten eine größere Beschriftung).
* Im selben Bereich in der Zeile ```Font``` auf den Button ```...``` rechts klicken.
* Zu einer kleineren Schriftgröße wechseln, auf ```OK``` klicken, unten in der Seitenleiste auf ```Refresh``` klicken und prüfen, ob es gut genug lesbar ist. Bei Bedarf die Ansicht zoomen. Die größten Knoten sollten lesbar sein. Falls nicht, wiederholen. Eine gewisse Überlappung ist normal.

Für dieses Beispiel war ```Arial 4``` ausreichend.

[
	![Network](../assets/images/1-8/gephi-06.png)
](../assets/images/1-8/gephi-06.png)

Anschließend das Bild als PNG exportieren:
* Auf ```Export: SVG/PDF/PNG``` unten links klicken
* Einen Dateinamen festlegen
* Den Dateityp ```PNG``` wählen
* Auf ```Options...``` klicken und eine Dateigröße von ```2048px x 2048px``` einstellen
* Datei speichern

Das Ergebnis sollte etwa so aussehen:

[
	![Network](../assets/images/1-8/gephi-export.png)
](../assets/images/1-8/gephi-export.png)

<div class="notice--info"><b>Hinweis:</b> Es ist völlig in Ordnung, gar keine Labels anzuzeigen. Dazu einfach <code>Show labels</code> in den Einstellungen deaktivieren. In dem Fall müssen später relevante Beschriftungen als Annotationen ergänzt werden.</div>

# Die Visualisierung annotieren

Das exportierte Bild in Google Slides importieren und **die Cluster annotieren**.

Kommentiert werden könnte zum Beispiel:
* Die relative Größe der Cluster
* Die relative Dichte der Cluster (dicht gepackt oder eher locker)
* Die Position der Cluster (in der Mitte, am Rand)
* Der Abstand zwischen den Clustern, der Aufschluss darüber gibt, wie stark sie verbunden sind. Sind manche Cluster stärker miteinander verbunden als andere?

**Diese Beobachtungen mit dem Thema energy conversion verknüpfen.** Cluster lassen sich nutzen, um Teilthemen von energy conversion zu identifizieren. Sind bestimmte Teilthemen wichtiger als andere? Auf welche Weise? Lassen sich die Teilthemen vergleichen?

Die interessantesten Beobachtungen in den Annotationen priorisieren.

Der Anfang einer Annotation könnte etwa so aussehen:

[
	![Network](../assets/images/1-8/MappingControversies_AnnotationExamples_FirstNetwork.svg)
](../assets/images/1-8/MappingControversies_AnnotationExamples_FirstNetwork.svg)

Hier gibt es eine [Vorlage](https://docs.google.com/presentation/d/1sUoBD0Q0DjBOsV-lgFbvlVQIGF4gYfWbUN88iE-GUTQ/edit?usp=sharing) – am besten eine eigene Kopie erstellen und darin weiter annotieren, oder ganz von vorne beginnen.

# Erstellte Dokumente

Für die spätere Weitergabe sollte man Folgendes aufbewahren:
* Das annotierte Netzwerk (JPEG oder PNG)

---

### Bezug zu den Kurslektüren

* Die Prinzipien und Konzepte der Visual Network Analysis (VNA) werden behandelt in **Kapitel 2: What is visual network analysis** in *Jacomy, M. (2021). Situating Visual Network Analysis*
* Sowie in **Kapitel 7: Visual network analysis** in *Venturini, T. & Munk, A.K. (2021). Controversy Mapping: A Field Guide*
* Die Besonderheiten von Wikipedia und die verschiedenen Wege, wie die Plattform für die Kontroversenanalyse genutzt werden kann, werden behandelt in *Weltevrede, E., & Borra, E. (2016).* **Platform affordances and data practices: The value of dispute on Wikipedia**
*Big Data & Society, 3(1).*
* Ein ähnliches Netzwerk wird beschrieben in **Abbildung 48** von *Venturini, T. & Munk, A.K. (2021). Controversy Mapping: A Field Guide*:

[
	![Overview tuto 1.10](https://medihal.archives-ouvertes.fr/hal-03227362/image)
](https://medihal.archives-ouvertes.fr/hal-03227362/image)
*Netzwerk von Seiten der Kategorie „Circumcision“ auf Wikipedia, verbunden durch alle Hyperlinks zwischen ihnen. Seiten über männliche Beschneidung gruppieren sich links (dunkelgrau mit weißer Mitte), während Seiten über weibliche Beschneidung (hier als „female genital mutilation“ bezeichnet) sich rechts gruppieren (weiß mit schwarzer Mitte).*
