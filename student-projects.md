---
layout: post
title: Abschlussarbeiten/Projekte
date: 2025-01-20
---

Die hier aufgeführten Bachelor- und Masterarbeiten können in Absprache auch in Form von Bachelor- bzw. Masterprojekten bearbeitet werden.
Dabei wird ggf. der Umfang des Themas an die Gegebenheiten des Projektes angepasst.
Falls eines der Themen als Bachelor- oder Masterprojekt durchgeführt werden soll, müssen keine Kenntnisse in Elm vorhanden sein, da diese im Rahmen des Projektes erarbeitet werden können.
Falls Sie sich für andere Themen aus den Bereichen moderne Methoden der Softwareentwicklung, Compilerbau, Programmiersprachen oder Algorithmen interessieren, wenden Sie sich bitte einfach per Mail an [mich](mailto:jan.christiansen@hs-flensburg.de).

<!-- - [Allgemeine Informationen zu Abschlussarbeiten](theses.md) -->
- [Allgemeine Informationen zur Arbeit mit Haskell](haskell.md)


<!-- ## Design von Programmiersprachen -->


<!-- ### Freie Theoreme in Java

Ein [freies Theorem](http://www.cs.sfu.ca/CourseCentral/831/burton/Notes/July14/free.pdf) ist eine Aussage über eine Funktion/Methode, die allein an Hand des Typs der Funktion/Methode getroffen werden kann.
Als Beispiel betrachten wir die Signatur der folgenden Haskellfunktion.

```haskell
foo :: [a] -> [a]
```

Obwohl wir nur den Typ der Funktion kennen und nicht die konkrete Implementierung, muss diese Funktion sich an gewissen Regeln halten.
Das freie Theorem für diese Funktion sagt aus, dass für jede Liste `list` gilt, dass `map f (foo list)` das gleiche Ergebnis liefert wie der Aufruf `foo (map f list)`.
Das heißt, es macht keinen Unterschied, ob wir `map` auf das Argument der Funktion oder das Ergebnis der Funktion anwenden.
Gesetze dieser Art kann man für jede polymorphe Funktion herleiten.
Während die Gesetzmäßigkeit für `foo` recht einfach wirkt, kann man bei komplexeren Typen erstaunlich komplexe Aussagen über eine Funktion ableiten.

Diese Form der Gesetzmäßigkeit gilt nicht nur in Sprachen wie Haskell, sondern auch in anderen Programmiersprachen die Polymorphismus/Generics zur Verfügung stellen.
Eine Einführung zu freien Theoremen im Kontext von Java bietet zum Beispiel [dieser Vortrag](http://data.tmorris.net/talks/yow-west-2016/1d388b6263e7cbeedfbea224997648daa1d7862d/parametricity.pdf).
Freie Theoreme basieren auf der Grundidee, dass man keinen Wert von einem polymorphen Typ erfinden kann.
Die Funktion `foo` kann in der Ergebnisliste zum Beispiel kein neues Element hinzufügen, die Funktion kann eigentlich nur die Elemente der Argumentliste verwenden, um die Ergebnisliste zu konstruieren.

Je nach dem, welche Sprachkonstrukte eine Programmiersprache zur Verfügung stellt, sind freie Theoreme nur noch in eingeschränkter Form gültig.
So können zum Beispiel Sprachfeatures wie Typumwandlung oder Typprüfung dafür sorgen, dass freie Theoreme nur mit Einschränkungen gültig sind.
In dieser Arbeit soll eine Fallstudie über Sprachfeatures in Java gemacht werden.
Dabei soll untersucht werden, bei der Verwendung von welchen Sprachfeatures in Java freie Theoreme nur noch unter Einschränkungen gültig sind.

**Voraussetzungen:** gute Kenntnisse der Programmiersprache Java, Grundkenntnisse in Haskell  
**Geeignet als:** Bachelor- oder Masterarbeit -->


## Mining Software Repositories


<!-- ### Programmierstil in Elm

In dieser Arbeit soll der Programmierstil analysiert werden, der in Elm-Projekten bei GitHub verwendet wird.
Es existiert bereits eine Haskell-Anwendung, die Elm-Projekte bei GitHub sammelt und Kennwerte für diese Anwendungen erhebt, zum Beispiel die Anzahl der Module oder die durchschnittliche Anzahl an Definitionen pro Modul.
In diesem Projekt sollen Eigenschaften der Projekte analysiert werden, die sehr Elm-spezifisch sind.
Zum Beispiel kann überprüft werden, wie die Projekte _underscore pattern_ einsetzen und ob Funktionen immer eta-reduziert sind.
Oder es kann überprüft werden, in welcher Reihenfolge die Definitionen in einem Modul sortiert sind, also zum Beispiel zuerst alle Datentypdefinitionen und dann alle Funktionsdefinitionen oder gemischt.
Es kann aber auch geprüft werden, in welcher Reihenfolge das _Pattern Matching_ der `update`-Funktion durchgeführt wird, also zuerst _Pattern Matching_ auf `Model` und anschließend auf `Msg` oder andersherum.
Oder es kann überprüft werden, wie Funktionen genannt werden, die eine `Html`-Struktur liefern, also aus `view` heraus aufgerufen werden.

Im ersten Schritt muss in dieser Arbeit definiert werden, welche Eigenschaften evaluiert werden sollen und wie diese Eigenschaften bewertet, gruppiert werden.
Danach muss die jeweilige Analyse in das Bestehende Tool integriert werden.

**Voraussetzungen:** gute Kenntnisse in Elm  
**Geeignet als:** Bachelor- oder Masterarbeit -->


<!-- ### Durchführung einer Meta-Studie

Im Rahmen dieser Arbeit soll eine sogenannte Meta-Studie durchgeführt werden.
Das heißt, es sollen Informationen aus publizierten Studien gesammelt und aufbereitet werden.
Es gibt zahlreiche wissenschaftliche Arbeiten zur Wahl von Bezeichnern in Programmiersprachen.
Dabei gibt es zum Einen Studien, die anhand von Probanden testen, welche Art von Bezeichnern besonders schnell oder korrekt zu erinnern sind.
Außerdem gibt es Studien, die Code daraufhin analysieren, welche Arten von Bezeichnern in Open-Source-Projekten in verschiedenen Programmiersprachen genutzt werden.
Im Rahmen der Meta-Studie muss zuerst eine Strategie entwickelt werden, mit der relevante wissenschaftliche Arbeiten identifiziert werden.
Dazu kann etwas auf Plattformen in wissenschaftlichen Arbeiten nach Schlüsselwörtern gesucht werden.
Im nächsten Schritt müssen alle wissenschaftlichen Arbeiten durchgearbeitet und die wichtigsten Eigenschaften der Arbeiten extrahiert werden.

**Voraussetzungen:** Sorgfältiges Arbeiten, gute englische Sprachkenntnisse  
**Geeignet als:** Bachelorarbeit -->


### Empirische Untersuchung von Piping in Elm

In dieser Arbeit soll die Verwendung der Operatoren `|>` und `<|` in Elm-Projekten bei GitHub untersucht werden.
Aus mehreren vorhergehenden Abschlussarbeiten steht bereits eine Anwendung zur Verfügung, die Elm-Repositories von GitHub klont und analysiert.
Diese Anwendung ist in Haskell geschrieben.
Die Anwendung extrahiert aus den Repositories die Elm-Quelldateien und erzeugt mithilfe eines [Parsers](fundamentals.md#parser) aus jeder Quelldatei einen [abstrakten Syntaxbaum (AST)](fundamentals.md#abstrakter-syntaxbaum-ast).
Der abstrakte Syntaxbaum eines Programms kann dann traversiert werden, um Informationen über die Elm-Programme zu extrahieren.

Die Informationen, die zu den Operatoren `|>` und `<|` erhoben werden, können sich an der Publikation [An Empirical Study of Method Chaining in Java](https://static.csg.ci.i.u-tokyo.ac.jp/papers/20/nakamaru-msr2020.pdf) orientieren.
Es soll zum Beispiel untersucht werden, wie häufig die Operatoren (ggf. im Vergleich zu normalen Funktionsanwendungen) verwendet werden.
Außerdem soll untersucht werden, ob es eher lange Sequenzen von Verwendungen der Operatoren gibt oder ob die Operatoren eher einzeln verwendet werden.
Daneben soll untersucht werden, in welchen Fällen die Operatoren `|>` und `<|` vor allem verwendet werden.
Zum Beispiel wird der Operator `|>` gern zusammen mit Funktionen wie `andThen` und `andMap` verwendet.
Außerdem wird der Operator `<|` gern verwendet, wenn das Argument, auf das die Funktion angewendet wird, mehrere Zeilen überspannt.
Es soll untersucht werden, ob die Operatoren `|>` und `<|` vor allem in diesen Fällen verwendet werden oder ob es noch weitere wiederkehrende Anwendungsfälle gibt.

Um die Elm-Anwendungen zu parsen, also einen abstrakten Syntaxbaum aus dem Quelltext zu erzeugen, wird die Haskell-Bibliothek [elm-format](https://github.com/HS-Flensburg-PLTP/elm-format) verwendet.
Diese Bibliothek stellt auch den Datentyp zur Verfügung, der den abstrakten Syntaxbaum von Elm modelliert.
Um einfach Informationen aus dem AST zu extrahieren, nutzt die Haskell-Anwendung die Ideen aus [Uniform Boilerplate and List Processing](https://ndmitchell.com/downloads/paper-uniform_boilerplate_and_list_processing-30_sep_2007.pdf).
Diese Publikation stellt eine Ansatz zur Verfügung, wie man mit vergleichsweise wenig Code aus einem komplexen Datentyp Informationen extrahieren kann.

Falls die Zeit es erlaubt, kann die Untersuchung auf weitere funktionale Sprachen ausgedehnt werden.

Die Arbeit startet mit einer Einarbeitung in Konzepte wie [Parser](fundamentals.md#parser), [abstrakter Syntaxbaum](fundamentals.md#abstrakter-syntaxbaum-ast) und die grundsätzliche Idee von _Repository Mining_-Studien.

**Voraussetzungen:** Grundkenntnisse in Haskell  
**Geeignet als:** Bachelor- oder Masterarbeit


### Replikation einer Studie über Bezeichner in verschiedenen Programmiersprachen

In dieser Arbeit soll die Studie [Meaningful Identifier Names: The Case of Single-Letter Variables](https://www.cs.huji.ac.il/w~feit/papers/SingleLetter17ICPC.pdf) repliziert werden.
Die Studie untersucht, wie lang die Bezeichner in den Programmiersprachen C, Java, JavaScript, PHP, und Perl sind und wie häufig Einbuchstabenbezeichner sind.
Dazu werden Projekte von GitHub analysiert.
Bei [GitHub](https://github.com/sarahgin/Meaningful-Identifier-Names-The-Case-of-Single-Letter-Variables) stehen die Programme zur Verfügung, die zur Durchführung der Studie genutzt wurden.
Dabei werden kleine Python-Skripte genutzt und ein paar sprachspezifische Skripte zur Extraktion der Variablen aus Programmen in den verschiedenen Programmiersprachen.
Bei der Replikation sollen insbesondere die Ergebnisse für die Programmiersprache JavaScript genauer überprüft werden.
Die Ergebnisse für die Programmiersprache JavaScript lassen vermuten, dass ggf. minifizierte JavaScript-Dateien mit analysiert wurden.
Das folgende Zitat stammt aus der Originalpublikation.

> This (together with the fact that single-letter variables are very common as shown in Figure 1) may indicate that the dataset includes some minified code that was not identified correctly and removed by our filter.

Daher soll nach der Replikation insbesondere ein Konzept entwickelt werden, um minifizierte JavaScript-Module auszuschließen.

Die Arbeit startet mit einer Einarbeitung in Konzepte wie [Parser](fundamentals.md#parser), [abstrakter Syntaxbaum](fundamentals.md#abstrakter-syntaxbaum-ast) und die grundsätzliche Idee von _Repository Mining_-Studien.

**Voraussetzungen:** Kenntnisse in Python  
**Geeignet als:** Bachelorarbeit

### Replikation einer Studie über Bezeichner in Java

In dieser Arbeit soll die Studie [A Large-Scale Investigation of Local Variable Names in Java Programs: Is Longer Name Better for Broader Scope Variable?](https://link.springer.com/chapter/10.1007/978-3-030-85347-1_35) repliziert werden.
Die Studie untersucht, wie Bezeichner in Java-Programmen vergeben werden.
Dazu wurden 1000 GitHib-Repositories analysiert.
Die Studie gibt an, dass 637 077 lokale Variablen aus 472 665 Java-Quelldateien extrahiert wurden.
Das wären etwa 1,3 lokale Variable pro Java-Quelldatei.
Die Daten der Studie stehen unter <https://bit.ly/3xLuaLK> zur Verfügung.
Bei einer ersten Sichtung der Daten ist bereits aufgefallen, dass gegen die Aussage "The local variables include the formal arguments (parameters) of methods." aus der Publikation anscheinend keine Bezeichner von Methodenparametern gesammelt werden.
Daher soll die Sammlung der Daten reproduziert und überprüft werden.
Die Anwendung, welche zum Sammeln der Daten genutzt wurde, wurde in Java geschrieben und steht ebenfalls unter https://bit.ly/3xLuaLK zur Verfügung.

**Voraussetzungen:** Gute Kenntnisse in Java  
**Geeignet als:** Bachelorarbeit


### Extraktion von Bezeichnern in F#

In dieser Arbeit soll eine bestehende Haskell-Anwendung um die Verarbeitung von F#-Programmen erweitert werden.
Die Programmiersprache F# ist eine funktionale Sprache, die von Haskell inspiriert wurde und auf der .Net-Platform von Microsoft läuft.
Die bestehende Haskell-Anwendung sammelt die 100 Repositories mit dem meisten Sternen von GitHub für die Programmiersprachen Haskell, Elm, PureScript und OCaml.
Diese Anwendung soll um die Verarbeitung der 100 Repositories mit den meisten Sternen in F# erweitert werden.
Zu diesem Zweck muss im ersten Schritt die Möglichkeit geschaffen werden, F#-Programme in Haskell zu verarbeiten.
Dazu soll ein minimales F#-Programm geschrieben werden, das eine Datei mit einem F#-Programm einliest und einen [abstrakten Syntaxbaum (AST)](fundamentals.md#abstrakter-syntaxbaum-ast) auf der Konsole ausgibt.
Das F\#-Programm gibt die Struktur des AST auf der Konsole aus und ein Haskell-Programm soll die Struktur einlesen und als Haskell-Datentyp zur Verfügung stellen.
Dazu muss in Haskell ein [Parser](fundamentals.md#parser) mithilfe von Parser-Kombinatoren geschrieben werden.
Der Parser überführt die Ausgabe auf der Konsole in einen Haskell-Datentyp, der den AST darstellt.
Wenn auf diese Weise erfolgreich in Haskell ein AST für ein F#-Programm erzeugt werden kann, soll prototypisch gezeigt werden, dass die Bezeichner aus einem F#-Programm gesammelt werden können.

Bei der Umsetzung als Masterarbeit soll die gesamte Integration der Sprache in das bestehende Tool umgesetzt werden.
Dazu sollen Build-Konfigurationsdateien der Sprache F# analysiert werden, um die Quelldateien, die ich in einem Repository befinden, zu sammeln.

Die Arbeit startet mit einer Einarbeitung in die Grundlagen der Programmiersprache F\# und Konzepte wie [Parser](fundamentals.md#parser), [abstrakter Syntaxbaum](fundamentals.md#abstrakter-syntaxbaum-ast) und die Verwendung von Parser-Kombinatoren in Haskell.

**Voraussetzungen:** Gute Kenntnisse in einer funktionalen Sprache  
**Geeignet als:** Bachelor- oder Masterarbeit


<!-- ### Web-Anwendung zur Datenvisualisierung

In einer zuvor durchgeführten Abschlussarbeit wurden die Bezeichner in 200 Haskell-Projekten auf GitHub untersucht.
In dieser Arbeit soll eine Web-Anwendung in Elm entwickelt werden, welche es Nutzern ermöglicht, diese Daten zu inspizieren.
Die Ergebnisse der Analyse liegen in Form von CSV-Dateien vor.
Im ersten Schritt muss ein Konzept entwickelt werden, wie die vorliegenden CSV-Dateien als Backend-Web-Anwendung zur Verfügung gestellt werden können.
Die Daten können zum Beispiel mittels [Supabase](https://supabase.com) oder [PostgREST](https://postgrest.org) zur Verfügung gestellt werden.

Es soll zum einen möglich sein, einfach die Rohdaten der verschiedenen Projekte zu inspizieren.
Das heißt, es ist möglich, eine Liste aller Bezeichner eines Modules, eines Projektes einzusehen.
Außerdem soll es möglich sein, sich Histogramme anzeigen zu lassen.
Diese Histogramme sollen die Verteilung von Einbuchstabenbezeichnern angeben und die Verteilung der Länge von Bezeichnern.
Die Publikation [Meaningful Identifier Names: The Case of Single-Letter Variables](https://www.cs.huji.ac.il/w~feit/papers/SingleLetter17ICPC.pdf) vermittelt einen Eindruck darüber, welche Histogramme auf jeden Fall pro Projekt und für die Gesamtdaten dargestellt werden sollten.
Diese Daten können im ersten Schritt im Frontend erzeugt werden, müssen bei Performance-Problemen aber ggf. bereits im Backend zur Verfügung gestellt werden.

Neben diesen Basisinformationen soll die Anwendung im besten Fall noch weitere Informationen zur Verfügung stellen, zum Beispiel die Namen von besonders langen Bezeichnern, aber auch Bezeichner, die besonders häufig vorkommen.

**Voraussetzungen:** Gute Kenntnisse in Elm  
**Geeignet als:** Bachelorarbeit -->


<!-- ### Typinformationen für Elm-Projekte

In dieser Arbeit soll eine bestehende Anwendung, die Elm-Projekte von GitHub sammelt und analysiert, verbessert werden.
Die Anwendung sammelt die Variablennamen, die in Elm-Projekte verwendet werden.
Um besser zu verstehen, nach welchen Regeln Programmierer\*innen Namen vergeben, sollen neben den Namen die Typen der Variablen gesammelt werden.
Da Elm eine Programmiersprache mit Typinferenz ist, müssen die Elm-Projekte zu diesen Zweck gebaut werden.
Das heißt, der Elm-Compiler wird für jedes Repo genutzt, um das Elm-Projekt zu bauen.
Der Elm-Compiler legt Dateien an, in denen Informationen über die Typen von

- den Elm-Compiler nutzen, um ein Projekt zu bauen
- die `elmi`-Dateien auslesen, um die Typinformationen auszulesen
- die Funktion https://github.com/elm/compiler/blob/2f6dd29258e880dbb7effd57a829a0470d8da48b/builder/src/Generate.hs#L191 liest die Typinformationen aus einer `elmi`-Datei aus
- die Funktion liefert `Types (Map.Map ModuleName.Canonical Types_)`, wobei `Types_ ` Informationen
- die Datei `elmi` enthält anscheinend nur die Typdefinitionen in einem Modul
- die Funktion https://github.com/elm/compiler/blob/2f6dd29258e880dbb7effd57a829a0470d8da48b/builder/src/Elm/Details.hs#L134C1-L134C15 liest die Interfaces aus der `i.dat`-Datei aus
- der Typ `type Interfaces = Map.Map ModuleName.Canonical I.DependencyInterface`
- der folgende Typ liefert Informationen über ein Modul
  ```elm
  data Interface =
    Interface
      { _home    :: Pkg.Name
      , _values  :: Map.Map Name.Name Can.Annotation
      , _unions  :: Map.Map Name.Name Union
      , _aliases :: Map.Map Name.Name Alias
      , _binops  :: Map.Map Name.Name Binop
      }
    deriving (Eq)
  ```

**Voraussetzungen:** Gute Kenntnisse in Haskell  
**Geeignet als:** Masterarbeit -->



<!-- ## Künstliche Intelligenz im _Software Engineering_

### Generieren von Funktionsnamen aus Funktionsdefinitionen

In dieser Arbeit soll eine bestehende Technik zum Lernen von Methodennamen aus Methodendefinitionen mit Hilfe eines neuronalen Netzes auf die Programmiersprache Haskell angewendet werden.
[CODE2VEC](https://code2vec.org) ist eine Technik, mit der Programme in Vektoren mit Zahlen umgewandelt werden können.
Diese Vektoren können dann genutzt werden, um neuronale Netze zu trainieren, die Programme verarbeiten können.
In einer ersten Anwendung wurde diese Technik verwendet, um für eine gegebene Java-Methode einen möglichst gut passenden Namen zu generieren.
In dieser Arbeit soll genau diese Technik auf Funktionen in der Programmiersprache Haskell angewendet werden.
In einer Vorarbeit wurde eine Haskell-Anwendung entwickelt, die ein Haskell-Modul einliest und daraus die entsprechenden Vektoren erzeugt.

Im ersten Schritt müssen in dieser Arbeit Haskell-Module gesammelt werden, zum Beispiel von GitHub.
Diese Module werden dann mit Hilfe der bestehenden Anwendung in Vektoren umgewandelt.
Mit Hilfe der auf diese Weise generierten Trainingsdaten muss dann ein neuronales Netz trainiert werden.
Dazu muss eine Python-Anwendung, die für das Training mit den Java-Programmen genutzt wird, entsprechend angepasst werden.
Es ist zu erwarten, dass die Haskell-Anwendung zur Generierung der Vektoren aus Haskell-Modulen noch angepasst werden muss.

**Voraussetzungen:** Grundkenntnisse in Haskell  
**Geeignet als:** Bachelor- oder Masterarbeit -->


## Programmiersprachen-Design


### Entwicklung einer Sprache für mathematische Beweise

In der Veranstaltung [Algorithmen](https://hs-flensburg-algo.github.io) müssen die Studierenden kleine Beweise zum asymptotischen Verhalten von Funktionen schreiben.
Es ist leider sehr aufwendig, sinnvoll Rückmeldungen zu den Beweisen zu geben.
Dieses Problem soll in dieser Arbeit angegangen werden.

Das erste Problem bei der Abgabe der Aufgaben besteht darin, dass die Studierenden Fotos ihrer Beweise oder PDF-Dateien abgeben.
Diese Daten lassen sich im Vergleich zum Programmcode, der in den anderen Aufgaben abgegeben wird, nicht gut automatisiert analysieren.
Daher soll im ersten Schritt eine Sprache für die spezielle Form von Beweisen, die die Studierenden schreiben, entwickelt werden.
Diese Sprache orientiert sich stark an den mathematischen Formalismen, kann aber in Form einer Textdatei verfasst werden.

Wenn die Studierenden ihre Textdatei hochladen, sollten sie eine direkte Rückmeldung zu Ihrer Abgabe erhalten.
In den Programmieraufgaben geschieht dies durch Testfälle und statische Analysen, die durch Automatisierung bei jedem _Push_ in ein Git-Repository ausgeführt werden.
Im Vergleich zu Programmieraufgaben scheitern viele Studierenden bei den Mathematikaufgaben bereits daran, korrekte Syntax zu verwenden und Variablen korrekt einzuführen, bevor sie verwendet werden.
Um Feedback zu den Aufgaben zu erhalten, soll ein [Parser](fundamentals.md#parser) für die sehr einfache mathematische Sprache entwickelt werden.
Dieser [Parser](fundamentals.md#parser) muss berücksichtigen, dass Studierende häufig bereits Probleme mit der Syntax haben und sollte gute Erklärungen für Fehler liefern.

Die Arbeit startet mit einer Einarbeitung in die grundlegende Struktur der mathematischen Beweise im Rahmen ver Veranstaltung [Algorithmen](https://hs-flensburg-algo.github.io) sowie in die Konzepte [Parser](fundamentals.md#parser) und Parser-Kombinatoren in Haskell.

**Voraussetzungen:** Gute Kenntnisse in einer funktionalen Sprache, grundlegende mathematische Fähigkeiten  
**Geeignet als:** Bachelorarbeit


### Konzept einer sicheren _Model_-_View_-_Update_-Architektur

In dieser Arbeit soll ein Konzept für eine _Model_-_View_-_Update_-Architektur entwickelt werden, die mehr statische Garantien erlaubt.
Dabei geht es insbesondere um den Fall, dass in einem bestimmten Modellzustand nur bestimmte Nachrichten an die Anwendung möglich sind.
Das Konzept soll prototypisch für eine _Model_-_View_-_Update_-Architektur in Haskell umgesetzt werden.

Aktuell lässt sich in der Programmiersprach Elm nicht ausdrücken, dass nur bestimmte Nachrichten in einem bestimmten Modellzustand erwartet werden.
Wenn man etwa das Beispiel eines Spiels nimmt, kann das Spiel laufen oder beendet sein.
Während das Spiel läuft ist es beispielsweise möglich eine Spielfigur mit den Tasten zu bewegen.
Ist das Spiel beendet, sollen diese Eingaben aber nicht verarbeitet werden.
Wenn die Anwendung im Beendet-Zustand eine Nachricht zum Bewegen der Spielfigur erhält, gibt es zwei Möglichkeiten.
Die Nachricht kann ignoriert werden, was schnell dazu führt, dass fehlerhafte interne Zustände erhalten bleiben.
Alternativ kann die Anwendung in einen Fehlerzustand wechseln, wenn ein inkonsistenter Zustand auftritt.
In diesem Fall wird im Grunde ein Laufzeitfehler ausgelöst und es ist wünschenswert, solche Laufzeitfehler durch statische Fehler zu ersetzen.

Als mögliche Lösung für dieses Problem soll der Einsatz von generalisierten algebraischen Datentypen (GADTs) evaluiert werden.
Die Programmiersprache Elm stellt keine generalisierten algebraischen Datentypen zur Verfügung, in der Programmiersprache Haskell können diese aber genutzt werden.
Daher soll das Konzept mithilfe der Haskell-Bibliothek [miso](https://haskell-miso.org) evaluiert werden.
Das Framework [miso](https://haskell-miso.org) ist eine Implementierung der _Model_-_View_-_Update_-Architektur in Haskell.
Zur Illustration der Verwendung von miso enthält das miso-Repository eine [Implementierung des TodoMVC](https://github.com/dmjio/miso/blob/master/examples/todo-mvc/Main.hs).

Im Kontext von Haskell soll evaluiert werden, welche Probleme bei der Modellierung von konkreten Anwendungen im Kontext eines sicheren _Model_-_View_-_Update_ entstehen.
Während die Verwendung von GADTs zum Beispiel eine höhere statische Sicherheit ermöglicht, werden Programmierer*innen ggf. so stark eingeschränkt, dass es schwieriger ist, eine Anwendung zu strukturieren.
Um diesen Aspekt zu evaluieren, sollen verschiedene typische Beispiele aus der Entwicklung von Frontendanwendungen mit der _Model_-_View_-_Update_-Architektur evaluiert werden.

Die Arbeit startet mit einer Einarbeitung in die _Model_-_View_-_Update_-Architektur und die konkrete Umsetzung in miso.
Anschließend wird das Konzept der generalisierten algebraischen Datentypen (GADTs) in Haskell erarbeitet.

**Voraussetzungen:** Gute Kenntnisse in einer funktionalen Sprache  
**Geeignet als:** Bachelor- oder Masterarbeit

<!--
## Programmiersprachen-Migration

### Werkzeuge zur Migration von JavaScript nach TypeScript

In dieser Arbeit sollen Werkzeuge evaluiert werden, die genutzt werden können, um JavaScript-Anwendungen nach TypeScript zu migrieren.
Zur Evaluation soll eine konkrete JavaScript-OpenSource-Anwendung genutzt werden.
Im ersten Schritt muss einer Liste der möglichen Werkzeuge zur Migration erstellt werden.
Dabei soll sowohl wissenschaftliche Literatur als auch OpenSource-Anwendungen berücksichtigt werden.
 -->

## Programmanalyse

### Identifikation von schlecht gewählten Bezeichnern in Java

Im Rahmen dieser Arbeit soll die Haskell-Anwendung [jlint](https://github.com/HS-Flensburg-PLTP/jlint) erweitert werden.
Die Anwendung wurde im Rahmen von mehreren Bachelor-Projekten entwickelt und wird dazu genutzt, den Studierenden in der Veranstaltung [Algorithmen](https://hs-flensburg-algo.github.io) Rückmeldung zur Code-Qualität zu geben.
Im Rahmen dieser Arbeit soll die Anwendung um Regeln erweitert werden, die sich auf die Qualität von Bezeichnern, also die Namen in einem Programm, beziehen.
In den letzten Jahren wurden manuell Rückmeldungen zu schlecht gewählten Bezeichnern gegeben, etwa wenn ein Attribut den Namen `array` trug aber eine Liste enthielt.
Diese manuellen Anmerkungen sollen evaluiert und wiederkehrende Muster in Form von Regeln implementiert werden.

Schlechte Bezeichner dieser Art werden in der Literatur auch als _Linguistic Anti-Pattern_ bezeichnet.
Im Rahmen der Arbeit sollen daher wissenschaftliche Publikationen aus diesem Bereich evaluiert werden und ggf. Anti-Pattern als Regeln in [jlint](https://github.com/HS-Flensburg-PLTP/jlint) implementiert werden.
Einen Einstieg bietet die Publikation [A New Family of Software Anti-Patterns: Linguistic Anti-Patterns](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=901209b3a70e7e46a477f5457e7ba687f0defc4f).

**Voraussetzungen:** Grundlegende Kenntnisse in einer funktionalen Programmiersprache  
**Geeignet als:** Bachelorarbeit


### Entwicklung eines _Identifier Dictionaries_ in Haskell

Die Publikation [Concise and consistent naming](https://wwwbroy.in.tum.de/publ/papers/deissenboeck_pizka_identifier_naming.pdf) stellt das Konzept eines _Identifier Dictionaries_ vor.
Diese Anwendung sammelt die Bezeichner, die in einem Software-Projekt verwendet werden und listet sie zusammen mit ihrem Typ auf.
Die Anwendung soll dabei helfen, ungenaue oder inkonsistente Benennungen zu erkennen.

In dieser Arbeit soll eine vergleichbare Anwendung für die Programmiersprache Haskell entwickelt werden.
Die größte Herausforderung besteht dabei darin, Typinformationen für die in einer Haskell-Anwendung verwendeten Variablen zu erhalten.
Um dies zu erreichen, muss die Haskell-Anwendung inklusive der Auflösung von Abhängigkeiten gebaut werden.
Es soll prototypisch ein Ansatz für ein solches _Identifier Dictionary_ entwickelt werden.
Zu diesem Zweck werden Hie-Dateien verwendet.
Der Haskell-Compiler ist in der Lage, [Hie-Dateien](https://www.haskell.org/ghc/blog/20190626-HIEFiles.html) zu erzeugen.
Bei diesen Dateien handelt es sich um Beschreibungen des Interface eines Moduls.
Diese Dateien werden zum Beispiel verwendet, um Funktionalitäten einer IDE für die Programmierung mit Haskell umzusetzen.
Diese Hie-Dateien müssen für ein Projekt erzeugt und gelesen werden, um ein _Identifier Dictionary_ zu erzeugen.

**Voraussetzungen:** Gute Kenntnisse in Haskell  
**Geeignet als:** Bachelor- oder Masterarbeit


<!-- ### Erweiterung des Elm-Compilers

In dieser Arbeit soll eine

Alternativ kann eine solche Anwendung auch für die Programmiersprache Elm entwickelt werden.
In diesem Fall muss der [Compiler](https://github.com/elm/compiler) der Programmiersprache Elm verwendet werden, um ein Elm-Programm zu bauen  -->


### Redundante Fälle in `case`-Ausdrücken

Um Studierenden Rückmeldungen zu Ihren Programmierabgaben in der Programmiersprache Elm zu geben, wird in einer Vorlesung die Bibliothek [elm-review](https://github.com/jfmengels/elm-review) genutzt.
In dieser Arbeit soll eine Regel für die Bibliothek [elm-review](https://github.com/jfmengels/elm-review) entwickelt werden, die anmerkt, wenn ein Fall eines `case`-Ausdruckes redundant ist.
Ein Fall ist redundant, wenn man den Fall entfernen kann, ohne dass sich das Verhalten der Funktion verändert.
Die folgende Definition enthält eine Regel, die redundant ist.

```elm
snocList : List a -> a -> List a
snocList list element =
    case list of
        [] ->
            element :: []

        head :: [] ->
            head :: element :: []

        head :: rest ->
            head :: snocList rest element
```

Wenn die zweite Regel aus dieser Definition entfernt wird, verändert sich das Verhalten dieser Funktion nicht.
Wenn die Funktion mit einer Liste der Form `head :: []` aufgerufen wird, wird die dritte Regeln genommen, falls die zweite Regel nicht existiert.
In diesem Fall wird der Aufruf `snocList [] element` durchgeführt, wobei `element` ein abstraktes Argument ist, das an die Funktion `snocList` übergeben wurde.
Der Aufruf `snocList [] element` liefert als Ergebnis `element :: []`.
Somit erhalten wir von der gesamten dritten Regel als Ergebnis `head :: element :: []`, was identisch zum Ergebnis ist, das die zweite Regel geliefert hätte.
Daher kann in dieser Definition die zweite Regel entfernt werden.


<!-- ```elm
hasCollision : Snake -> Bool
hasCollision snake =
    case snake of
        Cons _ [] ->
            False

        Cons x xs ->
            List.any (\y -> x == y) xs
```

```elm
indexedMap : (Int -> a -> b) -> NonEmpty a -> NonEmpty b
indexedMap func list =
    case list of
        Cons a [] ->
            Cons (func 0 a) []

        Cons x xs ->
            Cons (func 0 x) (helpindexedMap func 1 xs)
```


```elm
removeLast : NonEmpty a -> List a
removeLast (Cons x rest) =
    case rest of
        [] ->
            []

        y :: list ->
            x :: removeLastCons y list


removeLastCons : a -> List a -> List a
removeLastCons x xs =
    case xs of
        [] ->
            []

        y :: ys ->
            x :: removeLastCons y ys
``` -->

Um zu überprüfen, ob ein Fall entfernt werden kann, muss zuerst überprüft werden, ob es zwei _Pattern_ gibt, die sich überlappen.
In der Funktion `snocList` überlappen zum Beispiel die _Pattern_ `head :: []` und `head :: rest`, da das erste _Pattern_ ein Spezialfall des zweiten _Pattern_ ist.
Aus den beiden _Pattern_ kann nun eine Substitution berechnet werden.
Eine Substitution beschreibt, wie man aus dem einen _Pattern_ das andere _Pattern_ erzeugen kann.
Im Fall von `snocList` besteht die Substitution aus `rest -> []`.
Das heißt, wenn wir die Variable `rest` durch `[]` ersetzen, können wir aus dem _Pattern_ `head :: rest` das _Pattern_ `head :: []` erzeugen.

Wenn zwei _Pattern_ gefunden sind, die sich überlappen, kann die Substitution auf die rechte Seite des Falles angewendet werden.
Wir ersetzen in unserem Beispiel also zum Beispiel im Ausdruck `head :: snocList rest element` alle Vorkommen von `rest` durch `[]`.
Wir erhalten somit `head :: snocList [] element`.

**Voraussetzungen:** Gute Kenntnisse in einer funktionalen Sprache  
**Geeignet als:** Masterarbeit


### Reimplementierungen erkennen

Um Studierenden Rückmeldungen zu Ihren Programmierabgaben in der Programmiersprache Elm zu geben, wird die Bibliothek [elm-review](https://github.com/jfmengels/elm-review) genutzt.
In dieser Arbeit soll eine Regel für die Bibliothek [elm-review](https://github.com/jfmengels/elm-review) entwickelt werden, die anmerkt, wenn eine Funktion eine Reimplementierung einer vordefinierten Funktion ist.

Als Beispiel betrachten wir die folgende Funktion, die sich mithilfe von `List.map` implementieren lässt.

```elm
incAll : List Int -> List Int
incAll list =
    case list of
        a :: as ->
            a + 1 :: incAll as

        _ ->
            []
```

Es ist relativ aufwändig, alle möglichen Varianten dieser Funktion mit der Funktion `List.map` zu vergleichen.
Zum Beispiel nutzt die Funktion `incAll` im Unterschied zu `List.map` ein Unterstrich\-_Pattern_.
Außerdem prüft die Funktion `List.map` zuerst das _Pattern_ `[]`.
Daher soll die zu prüfende Funktion zuerst normalisiert werden.
Das heißt, zuerst wird das Unterstrich\-_Pattern_ durch ein konkrete _Pattern_ ersetzt.
Wir erhalten also die folgende Definition.

```elm
incAll : List Int -> List Int
incAll list =
    case list of
        a :: as ->
            a + 1 :: incAll as

        [] ->
            []
```

Im nächsten Schritt werden die _Pattern_ in eine vorgegebene Reihenfolge gebracht und wir erhalten die folgende Definition.

```elm
incAll : List Int -> List Int
incAll list =
    case list of
        [] ->
            []

        a :: as ->
            a + 1 :: incAll as
```

Im nächsten Schritt werden für die Variablen in den _Pattern_ die Namen verwendet, die auch in `List.map` verwendet werden.
Das heißt, wir erhalten die folgende Definition.

```elm
incAll : List Int -> List Int
incAll list =
    case list of
        [] ->
            []

        head :: rest ->
            head + 1 :: incAll rest
```

Nun kann die Funktion einfacher mit der vordefinierten Funktion `List.map` verglichen werden, da zum Beispiel die _Pattern_ einfach der Reihenfolge nach verglichen werden können.

Als Beispiele für die Erkennung von Reimplementierungen können die Funktionen `List.length`, `List.filter`, `List.any`, `List.map` und `List.concatMap` betrachtet werden.

**Voraussetzungen:** Gute Kenntnisse in einer funktionalen Sprache  
**Geeignet als:** Bachelorarbeit


### Feedback zu Mathematikaufgaben

Dieses Projekt ist einer Erweiterung des Projektes [Entwicklung einer Sprache für mathematische Beweise](#entwicklung-einer-sprache-für-mathematische-beweise).
Wenn die Abgabe der mathematischen Beweise syntaktisch akzeptiert wird, sollten die Studierenden auch Rückmeldung zur Korrektheit der Abgabe erhalten.
Dazu soll der interaktive Theorembeweiser [Coq](https://coq.inria.fr) verwendet werden.
Coq stellt eine Programmiersprache zur Verfügung, in der Beweise programmiert werden können.
Das Web-Buch [Software Foundations](https://softwarefoundations.cis.upenn.edu/lf-current/toc.html) bietet eine Einführung in die Programmiersprache Coq.
Das Buch führt aber sehr viel mehr Konzepte der Sprache ein als für die Bearbeitung des Themas benötigt werden.
Um einen Beweis zu überprüfen, muss ein Programm in der Sprache, die in [Entwicklung einer Sprache für mathematische Beweise](#entwicklung-einer-sprache-für-mathematische-beweise) entwickelt wurde, in ein Coq-Programm übersetzt werden.
Das Coq-Programm kann anschließend durch den Coq-Compiler auf Korrektheit überprüft werden.
Wenn der Coq-Compiler das Programm akzeptiert, ist der Beweis korrekt.
Im ersten Schritt muss erst einmal keine Rückmeldung gegeben werden, warum der Beweis falsch ist.

Zu Anfang der Arbeit soll eine Literaturrecherche zum Thema Vermittlung von mathematischen Fähigkeiten mithilfe von Theorembeweisern durchgeführt werden.
Einen guten Einstieg bietet [Waterproof: Educational Software for Learning How to Write Mathematical Proofs](https://arxiv.org/pdf/2211.13513).

**Voraussetzungen:** Gute Kenntnisse in einer funktionalen Sprache, grundlegende mathematische Fähigkeiten  
**Geeignet als:** Masterarbeit


## Web-Anwendungen

<!-- ### Regionale Rezepte

In dieser Arbeit soll ein Prototyp für eine Web-Anwendung für Rezepte mit regionalen Zutaten entwickelt werden.
Der durchschnittlichen Bevölkerung ist heutzutage häufig gar nicht mehr klar, dass nicht jedes Lebensmittel zu jeder Jahreszeit in der Nähe angebaut werden kann.
Das Ziel dieser Anwendung ist daher, Rezepte zur Verfügung zu stellen, bei denen berücksichtigt wird, dass Zutaten aktuell/zu einem bestimmten Zeitpunkt regional angebaut werden können.
Im ersten Schritt muss dazu ein Konzept entwickelt werden.
Das Internet bietet bereits zahlreiche Quellen, in denen man sich über die Saisonalität von landwirtschaftlichen Produkten informieren kann.
Bei der Nutzung dieser Quellen muss man sich aber aktiv für dieses Thema interessieren und häufig manuell die Zutaten von Rezepten in saisonalen Kalendern suchen.
Die Anwendung soll daher möglichst niedrigschwellig dafür sorgen, dass mehr Personen Rezepte auswählen, deren Zutaten saisonal regional angebaut werden können.
Bei der Anwendung soll nicht die Vermittlung von Wissen im Vordergrund stehen, sondern die Motivation von Nutzer\*innen, die Rezepte zu verwenden.

Im ersten Schritt müssen Datenquellen für landwirtschaftliche Produkte evaluiert werden.
Dabei kann es sich sowohl um Onlinedienste handeln, als auch um Quellen, deren Daten statisch in der Anwendung integriert werden.
Diese Quellen sollen Daten darüber zur Verfügung stellen, welche landwirtschaftlichen Produkte zu welcher Zeit in Schleswig-Holstein zur Verfügung stehen.

Bei der Bewertung der Nachhaltigkeit von Produkten muss berücksichtigt werden, dass einige Produkte auch als Lagerware zur Verfügung stehen.
Die Lagerung von Produkten bedeutet aber in einigen Fällen, dass eine aktive Kühlung durchgeführt werden muss.
Einige Produkte werden außerdem in bestimmten Monaten nur aus dem Gewächshaus angeboten.
Vor der Umsetzung der Anwendung soll die Nachhaltigkeit dieser Optionen bewertet werden, um zu entscheiden, wie diese Fälle von der Anwendung bewertet werden.
Außerdem soll bewertet werden, ob alle Zutaten eines Rezeptes regional sein müssen.
Dies würde zum Beispiel alle Rezepte, die Reis verwenden, ausschließen.
Ggf. wäre es sinnvoll, um die Ernährung in der breiten Masse nachhaltiger zu gestalten, einen gewissen Kompromiss einzugehen und eine nicht-nachhaltige Zutat in den Rezepten zu erlauben.

<!-- In einem späteren Schritt, der nicht in der Arbeit durchgeführt werden soll, sollen hinter den Rezepten konkrete Anbieter hinterlegt werden.
Das heißt, für eine Zutat wird dann angegeben, wo das Produkt in der Region erworben werden kann.
Zu diesen Zweck soll es erst einmal eine Beispielregion, etwa Flensburg oder Kiel verwendet werden. -->

<!-- Technologisch soll die Anwendung mit Elm im Frontend umgesetzt werden.
Zu Beginn des Projektes sollen verschiedene Alternativen für die Umsetzung des Backends evaluiert werden.

**Voraussetzungen:** Gute Kenntnisse in Elm  
**Geeignet als:** Bachelor- oder Masterarbeit
-->

<!-- ### Priorities

In dieser Arbeit soll ein Prototyp für eine Web-Anwendung entwickelt werden.
Die Anwendung erlaubt es, eine Umfrage zu erstellen, bei der Teilnehmer\*innen aus einer vorgegebenen Liste von Optionen eine festgegebene Anzahl an Optionen auswählen können.
Die Grundstruktur der Anwendung soll sich an Diensten wie [Doodle](doodle.com) oder auch dem [DFN-Terminplaner](https://terminplaner6.dfn.de) orientieren.
Außerdem kann man die gewählten Optionen in eine Prioritätenreihenfolge bringen.
Für die Anwendung muss also sowohl ein _Interface_ für die Konfigurator\*innen als auch für Teilnehmer\*innen entwickelt werden.

Die Daten werden in einem Backend gespeichert.
Die Daten können zum Beispiel mittels [Supabase](https://supabase.com) oder [PostgREST](https://postgrest.org) zur gespeichert werden.
Es muss kein Nutzermanagement implementiert werden.
Stattdessen wird die Autorisierung über zufällige _Token_ umgesetzt.
Das heißt, Teilnehmer\*innen erhalten eine URL mit einem zufälligen _Token_, um an einer Umfrage teilzunehmen.
Um eine Umfrage editieren zu können, gibt es ebenfalls eine URL mit einem zufälligen _Token_.
Es soll evaluiert werden, ob es sinnvoll ist, dass Teilnehmer\*innen ihre Auswahl im Nachhinein ändern.

Um die Optionen möglichst optimal auf die Teilnehmer\*innen zu verteilen, wird eine Zuordnung von Optionen zu Teilnehmer\*innen mithilfe von linearer Programmierung durchgeführt.
Dazu wird ein Microservice zur Verfügung gestellt, der eine Instanz mittels der C-Bibliothek [GNU Linear Programming Kit](https://en.wikipedia.org/wiki/GNU_Linear_Programming_Kit) löst und das Ergebnis in geeigneter Form zurückliefert.
Zur Umsetzung des Frontends soll die Programmiersprache Elm verwendet werden.
Die Anwendung wird als _Single Page Application_, zum Beispiel mithilfe des Frameworks [Elm Land](https://elm.land) erstellt.

Neben der Entwicklung der Anwendung soll ein Schwerpunkt der Arbeit auf einem sehr benutzerfreundlichen _User Interface_ liegen.


Zu Beginn des Projektes sollen verschiedene Alternativen für die Umsetzung des Backends evaluiert werden.
-->


<!-- ### Prove It

Neben den in <a href="#feedback-zu-mathematik-aufgaben">Feedback zu Mathematik-Aufgaben</a> beschriebenen Problemen, besteht ein weiteres Problem darin, dass die Studierenden nicht ausreichend Möglichkeiten haben, die mathematischen Beweise zu üben.
Aufgrund des Aufwändigen Feedbacks gibt es vergleichsweise wenige Aufgaben zu Beweisen.

Aus diesem Grund soll eine Web-Anwendung entwickelt werden, mit der einfache Formen von Beweisen dieser Art erstellt werden können.
Bei der Durchführung der Beweise sind nur eine handvoll Schritte möglich.
Diese möglichen Schritte werden den Nutzer\*innen als Optionen angeboten.
Je nach dem, welche Option gewählt wird, müssen die Nutzer\*innen dann noch zusätzliche Informationen angeben.

Um den Coq-Compiler aufzurufen, kann entweder [jsCoq](https://github.com/ejgallego/jscoq) genutzt werden, eine JavaScript-Implementierung des Coq-Compilers, oder es wird ein einfaches Backend entwickelt, das den Coq-Compiler ausführt und die Ergebnisse in geeigneter Form zurückgibt.
Dazu muss das Ergebnis, das der Coq-Compiler bei der Übersetzung eines Programms liefert, entsprechend geparset werden.
Das heißt, es müssen die notwendigen Informationen aus der Ausgabe des Compilers extrahiert werden.

In einer Erweiterung der Anwendung können Nutzer\*innen die Aufgaben textuell bearbeiten statt eine feste Anzahl von Optionen anzubieten.
Das heißt, die Anwendung muss in der Lage sein, die Eingabe der Nutzer\*innen zu parsen und auf die Struktur eines typischen Beweise zu überprüfen. -->


### Digitalisierung von Anträgen zur Anerkennung von Leistungen

In dieser Arbeit soll ein Prototyp einer Web-Anwendung entwickelt werden, die genutzt werden kann, um Anträge auf die Anerkennung von Leistungen an anderen Hochschulen digital einzureichen.
In einem Studierenden-Projekt wurde bereits ein erster Prototyp einer solchen Anwendung umgesetzt.
Grundsätzlich soll die Anwendung neu entwickelt werden, ggf. kann aber das UI-Design oder das Datenmodell der bestehenden Anwendung übernommen werden.
Zur Umsetzung der Anwendung soll ein einfaches REST-Backend und eine Frontend-Anwendung in Elm umgesetzt werden.
Zu Beginn des Projektes sollen verschiedene Alternativen für die Umsetzung des Backends evaluiert werden.

Zu Beginn des Projektes sollen verschiedene Alternativen für die Umsetzung des Backends evaluiert werden.

**Voraussetzungen:** Gute Kenntnisse in Elm  
**Geeignet als:** Bachelorarbeit


### Digitalisierung der Semesterplanung

Zur Verbesserung der Vorplanung eines Semesters soll ein Prototyp einer Web-Anwendung entwickelt werden, in der Dozent\*innen hinterlegen können, welche Lehrveranstaltungen sie im kommenden Semester planen.
Dazu gibt die Anwendung eine Liste von möglichen Veranstaltungen vor, die durch die Prüfungsordnung vorgegeben werden.
Die Nutzer\*innen können sich dann aus der Liste die Veranstaltungen zusammenstellen, die Sie im kommenden Semester planen.
Im besten Fall ist die Anwendung im Anschluss in der Lage sehr einfache Analysen der Planung durchzuführen.
Dazu gehört etwa die Analyse, welche Veranstaltungen aus der Prüfungsordnung noch nicht abgedeckt werden.
Zu diesem Zweck muss in der Anwendung hinterlegt werden, wie viele Studierende in den verschiedenen Semestern in etwa erwartet werden.
Ansonsten kann zum Beispiel nicht überprüft werden, ob die Anzahl der Labore oder die Anzahl der Wahlpflichtfächer ausreichend ist.

**Voraussetzungen:** Gute Kenntnisse in Elm  
**Geeignet als:** Bachelorarbeit
