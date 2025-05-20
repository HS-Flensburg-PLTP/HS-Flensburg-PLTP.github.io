---
layout: post
title: "Deklarative Software-Technologien"
date: 2025-05-14
---


## Abschlussprojekte

Auf dieser Seite werden Information zum Abschlussprojekt zur Verfügung gestellt.


### Beispielprojekte aus vorherigen Veranstaltungen

Bei diesen Beispielen sollte beachtet werden, dass die formalen Anforderungen an die Projekte in den vergangenen Semestern zum Teil anders war.
Die hier vorgestellten Ergebnisse würden daher ggf. den formalen Anforderungen in diesem Semester gar nicht mehr genügen.

- [Elmigma (eine Implementierung der Enigma)](https://simonhauck.github.io/Enigma-Elm/)
- [3DelmTRIS (eine 3D-Variante von Tetris)](https://tobiaswen.github.io/3DelmTRIS/)
- [Das Spiel Kalaha (Brettspiel)](http://htmlpreview.github.io/?https://github.com/lwiedema/kalah-game-elm/blob/master/kalah-game.html)
- [Pacman (altes Computerspiel)](https://timokramer4.github.io/elm-pacman/)
- [Elmgorithm (Visualisierung von Sortieralgorithmen)](https://hs-flensburg-dst.github.io/elmgorithm)
- [Gladius (Shoot ’em up)](https://hs-flensburg-dst.github.io/gladius)
- [Stream Time (eine Art Programmzeitung für Twitch)](https://www.stream-time.xyz)
- [Guess my Cocktail (Ratespiel)](https://hs-flensburg-dst.github.io/guess-my-cocktail)
- [Wandering Journey (Strategiespiel)](https://pascldev.github.io/wandering-journey/)


### Grundlegendes zum Projekt

Aufgrund des begrenzten zeitlichen Umfangs des Projektes müssen die entwickelten Anwendungen nicht vollständig sein, sondern sollen nur die Idee illustrieren.
Es ist also völlig legitim, an bestimmten Stellen einfach anzuzeigen, dass noch eine Funktionalität fehlt oder auch Funktionalitäten durch statische Daten zu simulieren.
Für die umgesetzte Funktionalität sollten aber Fehlerfälle korrekt und sinnvoll behandelt werden.
Grundsätzlich sollte eher auf Qualität als auf Quantität gesetzt werden.
Häufig werden Anwendungen, die einen Aspekt sehr gut umsetzen, besser bewertet als Anwendungen, bei denen es viele Funktionen gibt, die alle große Mängel aufweisen.
Der Aspekt "Umfang der Lösung" ist zwar Teil der Bewertung, für ein Übererreichen dieses Aspekts wird aber auch keine bessere Note vergeben.


### Datenquellen

Alle Anwendungen sollen auf einem Daten-Backend basieren.
Zu diesem Zweck soll eine Datenquelle verwendet werden.
Es können zum Beispiel Daten aus _Open Data_-Quellen verwendet werden.

#### Open Data

Es gibt viele Quellen für offene Daten, etwa von staatlichen Stellen ([Bundesstelle für Open Data](https://github.com/bundesAPI), [Open Data Schleswig-Holstein](https://www.schleswig-holstein.de/DE/Landesregierung/Themen/Digitalisierung/openData/openData_node.html), [Das Datenportal für Deutschland](https://www.govdata.de), [Offenes Datenportal der EU](https://data.europa.eu/euodp/de/data/), [Das Datenportal der Deutschen Bahn AG](https://data.deutschebahn.com), [Datenportal zum Thema Mobilität](https://mobilithek.info)) aus der Wissenschaft ([Deutscher Wetterdienst](https://opendata.dwd.de)) oder aus aus dem Bereich Kultur ([Coding da Vinci](https://codingdavinci.de/de/daten)).
Die meisten dieser Daten stehen in Form von CSV- oder Excel-Dateien zur Verfügung.
Um CSV-Dateien bereitzustellen, kann die Anwendung [Datasette](../datasette.md) genutzt werden.
Falls nur eine Excel-Datei mit den Daten zur Verfügung steht, muss die Datei ggf. einmal in eine CSV-Datei überführt werden.
Die Daten müssen nicht wirklich öffentlich zur Verfügung gestellt werden.
Es reicht, wenn für die Entwicklung und zum Testen ein lokaler Server gestartet wird.
Bitte geben Sie später bei der Entwicklung in einer README-Datei an, welche Schritte ausgeführt werden müssen, um die Anwendung zu testen.
In den _Open Data_-Plattformen finden sich auch Daten in Form von anderen Formaten, etwa als PDF-Dateien.
Diese Daten können natürlich auch in geeigneter Form in die Anwendung eingebunden werden.

#### Open APIs

Neben _Open Data_ in Form von Dateien gibt es auch öffentliche APIs, also Web-Server, die Daten direkt zur Verfügung stellen.
Das [GitHub-Repo Public APIs](https://github.com/public-apis/public-apis) listet zum Beispiel öffentlich zugängliche APIs zu verschiedensten Themen auf.

#### Andere Datenquellen

Grundsätzlich ist es auch erlaubt, andere Datenquellen zu nutzen.
Wenn also aus einer anderen Datenquelle Daten, etwa im CSV-Format, vorliegen, ist es ebenfalls erlaubt, die Anwendung auf diesen Daten basieren zu lassen.


### Mögliche Anwendungen

In diesem Abschnitt soll illustriert werden, welche Formen von Anwendungen auf Grundlage von offenen Daten erstellt werden können.

#### Visuelle Aufbereitung

Die Daten aus einer Datenquelle können zum Beispiel visuell aufbereitet werden.
Im Gegensatz zu gängigen Beispielen sollte hierbei darauf geachtet werden, dass die Daten in einer sinnvollen Art und Weise aufbereitet werden.
Die einfachste Möglichkeit, Daten visuell aufzubereiten, ist ein Dashboard.
Als Beispiel gibt es etwa eine Anwendung, die den [Fahrzeugbestand im Kreis Neuss](https://opendata.rhein-kreis-neuss.de/explore/dataset/rhein-kreis-neuss-fahrzeugbestand/dashboard/?disjunctive.zulassung_kennzeichen&disjunctive.halterpostleitzahl&disjunctive.technik_herstellertext&disjunctive.technik_hubraum&disjunctive.technik_nennleistung&disjunctive.technik_kraftstofftext&disjunctive.technik_hauptfarbeschluessel&disjunctive.technik_sitzplaetze&disjunctive.technik_fahrzeugklasseschluessel&disjunctive.halter_wohnort&disjunctive.technikemiklasseschluessel&disjunctive.technik_aufbauschluessel) visualisiert.
Beispiele für verschiedene Arten von Dashboards finden sich auch im [Statistikportal des Kraftfahrtbundesamtes](https://experience.arcgis.com/experience/fa9edaee4fca4b31a7711cbed6fba49c).
Viele Daten können auch in Form einer Karte visuell aufbereitet werden.
Als Beispiel sei hier eine [Karte mit Denkmälern in Schleswig-Holstein](https://denkmalkarte.oklabflensburg.de).
genannt.
Daten können aber auch vergleichsweise einfach interessant visuell aufbereitet werden, wie etwa in der Anwendung zur [Trinkwasserqualität in der Region Heilbronn](https://opendatalab.de/projects/trinkwasser/).

#### Interaktive Erklärungen

Die Anwendung zur Trinkwasserqualität hat bereits eine Schnittmenge mit dem Konzept der interaktiven Erklärungen.
Bei diesen Frontend-Anwendungen werden häufig Konzepte erläutert.
Ein vergleichsweise bekanntes Beispiel ist [The Evolution of Trust: An Interactive Guide to Game Theory](https://ncase.me/trust/), die Konzepte aus dem Bereich der Spieltheorie erläutert.
Unter [Explorable Explanations](https://explorabl.es) finden sich noch weitere Anwendungen aus dem Bereich der interaktiven Erklärungen.
Als Grundlage für die Umsetzung solcher interaktiven Erklärungen eignet sich vor allem Wissen aus dem Bereich der privaten Interessen.
Wenn man sich zum Beispiel sehr gut mit Umweltaspekten auskennt, wäre es ggf. sinnvoll eine entsprechende Anwendung zu einem Thema in diesem Bereich zu entwickeln.
Wenn eine solche Anwendung umgesetzt wird, sollten Daten aus einer Datenquellen integriert werden.
Ein Beispiel für eine Anwendung dieser Art ist der Artikel [Aktuelle Datenperle – Fahrraddiebstähle](https://odis-berlin.de/aktuelles/2024-09-01-datengeschichten-fahrraddiebstaehle/), der die Statistik zu Fahrraddiebstählen in Berlin illustriert.
Ein anderes Beispiel ist die Anwendung [Klimawatch](https://klimawatch.de), welche die Entwicklung des CO2-Ausstoßes verschiedener Städte illustriert.

#### Spiele

Alternativ können offene Daten auch zur Umsetzung eines Spiels genutzt werden.
Man kann mit den Daten zum Beispiel ein Quiz gestalten, wie es in [How many cities can you name?](https://cityquiz.io) der Fall ist.
Das Quiz verbindet auch geschickt zusätzliche Hintergrundinformationen mit dem Quiz.
Alternativ wäre es auch möglich, die Leveldaten eines Spiels aus den offenen Daten zu erzeugen.
So könnte die Struktur der Level eines Spiels zum Beispiel aus Kartendaten erzeugt werden.
Alternativ könnte die Größe von Objekten wie Hindernissen oder Gegnern mit offenen Daten korrelieren.
Man kann auch andere Aspekte eines Spiels mit Daten in Einklang bringen.
So könnte man die Wahrscheinlichkeitsverteilung, nach der gegnerische Fahrzeuge gewählt werden, auf der Verteilung von Fahrzeugtypen in der Realität basieren lassen.

Zu guter Letzt soll noch erwähnt werden, dass ein Mehrwert auch dadurch entstehen kann, dass eine Kombination von mehreren Datenquellen genutzt wird.
Durch diese Kombination können Korrelationen aufgezeigt werden.
Alternativ können auch mehrere Quellen zu einem ähnlichen Thema zu einer Anwendung kombiniert werden.

### Technische Aspekte

In diesem Abschnitt werden ein paar eher technische Aspekte der Abschlussprojekte diskutiert, die berücksichtigt werden sollten.

#### Umsetzung eines Spiels

Bei der Umsetzung eines Spiels sind einige weitere Aspekte zu berücksichtigen, von denen einige hier erwähnt werden sollen.
Zuerst sollte man sich Gedanken darüber machen, welche Technologie zur Darstellung genutzt wird.
Im Wesentlichen stehen SVG, Canvas und WebGL zur Verfügung.
Diese Ansätze haben verschiedene Vor- und Nachteile, die universell, also zum Beispiel auch in JavaScript, gültig sind.
Unter [elm games](https://github.com/rofrol/elm-games) finden sich einige in Elm implementierte Spiele.
Dort können Sie sich zum Beispiel anschauen, welche Technologien/Bibliotheken von ähnlichen Spielen verwendet werden.

Für die Implementierung der Snake-Anwendung wurde ein Timer verwendet.
Dieser eignet sich aber nicht mehr, wenn das Spiel eine höhere Aktualisierungsrate hat.
In diesen Fällen sollten eher `onAnimationFrame` bzw. `onAnimationFrameDelta` ([Browser.Events](https://package.elm-lang.org/packages/elm/browser/latest/Browser-Events)) genutzt werden.
Hier wird die Aktualisierung mit dem Neuzeichnen des Browserfensters synchronisiert.
Weitere Hintergrundinformationen findet man, wenn man nach der entsprechenden JavaScript-Funktion `requestAnimationFrame` sucht.
