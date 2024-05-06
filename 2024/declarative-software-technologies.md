---
layout: post
title: "Deklarative Software-Technologien"
date: 2024-05-06
---


## Abschlussprojekte

Auf dieser Seite werden Information zum Abschlussprojekt zur Verfügung gestellt.


### Beispiele aus vorherigen Veranstaltungen

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

Die meisten der Anwendungen werden ein einfaches Daten-Backend benötigen.
Hierfür soll der Backend-as-a-Service-Dienst [Supabase](https://supabase.com) verwendet werden.
Supabase bietet eine Web-Anwendung, in der Datenbank-Tabellen erstellt werden können.
Die Daten in den Tabellen können dann über eine REST-API abgerufen und aktualisiert werden.
Grundsätzlich erlaubt Supabase auch die Umsetzung von Authentifizierung und Autorisierung.
Authentifizierung ist dabei der Prozess, in dem Nutzer\*innen ihre Identität belegen, zum Beispiel durch die Verwendung eines Passwortes.
Autorisierung ist dagegen die Funktionalität, dass bestimmte Nutzer\*innen nur bestimmte Routen nutzen dürfen.
Auf diese Funktionalität soll aber im Rahmen des Projektes verzichtet werden, um den Aufwand für die Erstellung eines Backends möglichst gering zu halten.

Es ist nicht notwendig, in einer Anwendung eine Seite zur Registrierung von neuen Nutzer\*innen oder andere zusätzliche Seiten, etwa für Einstellungen zu implementieren.
Wenn der Umfang der sonstigen Anwendung zu gering ist, ist es aber gut möglich, Seiten dieser Art als Erweiterung zu implementieren, um auf einen sinnvollen Umfang an Code zu kommen.


### Mögliche Themenbereiche

<!-- Im Gegensatz zu vorherigen Semestern werden in diesem Jahr zwei Themenbereiche vorgegeben.
Ihr Projekt muss in einen dieser beiden Themenbereiche fallen. -->
<!-- In den vergangenen Jahren wurde gefordert, dass eine Projektidee (zumindest in Elm) zuvor noch nie umgesetzt wurde.
Aufgrund der Einschränkung der möglichen Themen ist es in diesem Jahr aber auch erlaubt, dass mehrere Projektteams eine ähnliche Idee umsetzen. -->

In den folgenden Abschnitten werden die Themenbereiche vorgestellt, aus denen das Projekt stammen kann, das Sie umsetzen.
Die konkreten Ideen, die dabei erwähnt werden, sind nur zur Inspiration gedacht und erheben keinen Anspruch darauf, sinnvoll zu sein.


#### Digitalisierung der Hochschule

In diesem Themenbereich sollen Anwendungen umgesetzt werden, die Prozesse an der Hochschule digitalisieren.
Wenn es zum Beispiel Formulare gibt, die bisher ausgedruckt und ausgefüllt werden müssen, könnte eine Anwendung das entsprechende Formular als Webseite zur Verfügung stellen.
Bei solchen Anwendungen sollte berücksichtigt werden, dass es auch Nutzer\*innen geben muss, die das abgegebene Formular weiterverarbeiten.
Das heißt, es muss ggf. so etwas wie eine Admin-Ansicht geben.
Beispiele für Formulare, die aktuell an der Hochschule ausgefüllt werden müssen, sind etwa Dokumente des Prüfungsmanagements, aber auch Dokumente für das Berufspraktikum.

Neben der Digitalisierung eines bestehenden Prozesses, der aktuell durch ein Formular abgebildet wird, können durch eine Anwendung auch neue Prozesse eingeführt werden.
So könnte zum Beispiel eine Anwendung umgesetzt werden, die es erlaubt, das Angebot an Projekten in einem Semester einzusehen und Interesse an einem Projekt zu bekunden.
Alternativ könnte man zum Beispiel eine Anwendung umsetzen, in der man studentische Räume reservieren kann oder eine Anwendung, die den Prozess der Anerkennung von Leistungen digitalisiert.

Eine weitere Möglichkeit wäre die Umsetzung einer Anwendung auf Grundlage von _Crowdsourcing_.
Wenn man sich zum Beispiel regelmäßig ärgert, weil man in einer nicht ganz so beliebten Vorlesung mal wieder alleine sitzt, wäre es möglich eine Anwendung umzusetzen, in der man angeben kann, dass man eine Vorlesung besuchen wird.
Andere Nutzer\*innen können diese Information dann einsehen und sich ebenfalls anmelden.
Alternativ könnte man eine Anwendung wie "Gibt es noch Pommes?" umsetzen, in der man angeben kann, ob es eine beliebte Speise in der Mensa noch gibt.
Die Nutzer\*innen können dann eintragen, ob es die entsprechende Speise noch gibt.

Alternativ ist auch die Umsetzung von Projekten möglich, die Informationen zur Hochschule aufbereiten.
So könnte man zum Beispiel Statistiken der Hochschule oder von einzelnen Fachbereichen visualisieren, etwa die Anzahl der Studierenden über die Jahre, durchgeführte Transferprojekte oder Ähnliches.
In diese Kategorie würden auch Anwendungen fallen, die dabei helfen sich an der Hochschule zurechtzufinden.
So wäre es zum Beispiel möglich eine "Wo finde ich was?"-Anwendung umzusetzen, die dabei unterstützt Einrichtungen an der Hochschule zu finden.


#### Grundungsprojekte

In diesem Themenbereich können Projekte umgesetzt werden, die eine Komponente einer StartUp-Idee umsetzen.
Dabei kann es sich um eine digitale Dienstleistung handeln, die später, zum Beispiel über Nutzergebühren oder Werbung monetarisiert werden kann.
Es kann sich aber zum Beispiel auch um eine Dienstleistungsanwendung handeln, die für die Umsetzung der Gründungsidee notwendig ist.
Wenn die Gründungsidee zum Beispiel im Verleih von Fahrrädern besteht, kann im Rahmen des Projektes eine Anwendung entwickelt werden, in der Kund\*innen die Fahrräder buchen können.

Um die Anwendung umzusetzen, muss keine Marktanalyse durchgeführt werden, das heißt, es kann auch eine Idee verfolgt werden, bei der es am Ende nicht realistisch ist, Geld damit zu verdienen.
Bei der Idee sollte es aber zumindest plausibel sein, dass es einzelne Personen gibt, die dafür Geld bezahlen würden.
