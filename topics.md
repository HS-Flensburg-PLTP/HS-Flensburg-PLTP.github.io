---
layout: post
title: Abschlussarbeiten/Projekte
date: 2026-01-13
---

Die hier aufgeführten Bachelor- und Masterarbeiten können in Absprache auch in Form von Bachelor- bzw. Masterprojekten bearbeitet werden.
Dabei wird ggf. der Umfang des Themas an die Gegebenheiten des Projektes angepasst.
Falls eines der Themen als Bachelor- oder Masterprojekt durchgeführt werden soll, müssen keine Kenntnisse in Elm vorhanden sein, da diese im Rahmen des Projektes erarbeitet werden können.
Falls Sie sich für andere Themen aus den Bereichen moderne Methoden der Softwareentwicklung, Compilerbau, Programmiersprachen oder Algorithmen interessieren, wenden Sie sich bitte einfach per Mail an [mich](mailto:jan.christiansen@hs-flensburg.de).

<!-- - [Allgemeine Informationen zu Abschlussarbeiten](theses.md) -->

- [FAQ zu Bachelor-Projekten](projects.md)
- [Allgemeine Informationen zur Arbeit mit Haskell](haskell.md)

## Mining Software Repositories

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

### Linguistische Muster in funktionalen Programmiersprachen

In dieser Arbeit sollen die linguistischen Muster untersucht werden, die bei der Benennung von Funktionen und Konstanten in funktionalen Programmiersprachen genutzt werden.
An dieser Stelle betrachten wir beispielhaft die funktionale Programmiersprache Elm, es wäre grundsätzlich aber auch möglich, eine andere oder mehrere Sprachen zu untersuchen.
Es sollen Namen von Funktionen und Konstanten aus der Standardbibliothek von Elm betrachtet und überprüft werden, ob es Muster bei der Benennung gibt.
In der Publikation [Cognitive Perspectives on the Role of Naming in Computer Programs](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/ppig-naming.pdf) wurden im Fall von Java drei linguistische Muster bei der Benennung von Methoden identifiziert: imperative Verbalphrasen, indikative Verbalphrasen und Nominalphrasen.
Diese linguistischen Muster werden auch für Elm-Funktionen verwendet.

Im Rahmen dieser Arbeit soll überprüft werden, ob diese Muster in der gleichen Form in Elm wie in Java verwendet werden und ob es Muster in Elm gibt, die in Java keine Verwendung finden.
Im Anschluss an die Identifikation von Mustern soll diese Hypothese im besten Fall mit Elm-Code von GitHub verifiziert werden.
Dazu soll eine bestehende Anwendung genutzt werden, die Elm-Repositories von GitHub klont und analysiert.
Im besten Fall soll zur Analyse der Bezeichner in Elm eine Bibliothek wie [Wordnet](https://wordnet.princeton.edu) verwendet werden.

**Voraussetzungen:** Kenntnisse in einer funktionalen Sprache  
**Geeignet als:** Bachelorarbeit

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

## Programmanalyse

### Identifikation von schlecht gewählten Bezeichnern in Java

Im Rahmen dieser Arbeit soll die Haskell-Anwendung [jlint](https://github.com/HS-Flensburg-PLTP/jlint) erweitert werden.
Die Anwendung wurde im Rahmen von mehreren Bachelor-Projekten entwickelt und wird dazu genutzt, den Studierenden in der Veranstaltung [Algorithmen](https://hs-flensburg-algo.github.io) Rückmeldung zur Code-Qualität zu geben.
Im Rahmen dieser Arbeit soll die Anwendung um Regeln erweitert werden, die sich auf die Qualität von Bezeichnern, also die Namen in einem Programm, beziehen.
In den letzten Jahren wurden manuell Rückmeldungen zu schlecht gewählten Bezeichnern gegeben, etwa wenn ein Attribut den Namen `array` trug, aber eine Liste enthielt.
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

### Digitalisierung von Anträgen zur Anerkennung von Leistungen

In dieser Arbeit soll ein Prototyp einer Web-Anwendung entwickelt werden, die genutzt werden kann, um Anträge auf die Anerkennung von Leistungen an anderen Hochschulen digital einzureichen.
In einem Studierenden-Projekt wurde bereits ein erster Prototyp einer solchen Anwendung umgesetzt.
Grundsätzlich soll die Anwendung neu entwickelt werden, ggf. kann aber das UI-Design oder das Datenmodell der bestehenden Anwendung übernommen werden.
Zur Umsetzung der Anwendung soll ein einfaches REST-Backend und eine Frontend-Anwendung in Elm umgesetzt werden.
Zu Beginn des Projektes sollen verschiedene Alternativen für die Umsetzung des Backends evaluiert werden.

Zu Beginn des Projektes sollen verschiedene Alternativen für die Umsetzung des Backends evaluiert werden.

**Voraussetzungen:** Gute Kenntnisse in Elm  
**Geeignet als:** Bachelorarbeit

### Weiterentwicklung einer Web-Anwendung für Rezepte

Im Rahmen einer vorangegangenen Bachelorarbeit wurde eine Web-Anwendung zur Darstellung von Rezepten entwickelt.
Die Rezepte werden dabei nach der regionalen und saisonalen Verfügbarkeit von Zutaten bewertet.
Die Anwendung enthält kleinere Mängel und soll zusätzliche Funktionalitäten erhalten.
Das Frontend der Anwendung ist in Elm mit dem Framework [Elm Land](https://elm.land) entwickelt.
Das Backend der Anwendung ist in Haskell mit dem Framework [Servant](https://www.servant.dev) entwickelt.
Bei der Weiterentwicklung der Anwendung sollen die Vorgaben des [Barrierefreiheitsstärkungsgesetz](https://www.bmas.de/DE/Service/Gesetze-und-Gesetzesvorhaben/barrierefreiheitsstaerkungsgesetz.html) berücksichtigt werden.
Das heißt, Accessibility-Aspekte der Anwendung sollen bewertet und ggf. an die Vorgaben des Gesetzes angepasst werden.
Auch bei der Entwicklung neuer Funktionalitäten soll dieser Aspekt berücksichtigt werden.

**Voraussetzungen:** Gute Kenntnisse in Elm  
**Geeignet als:** Bachelorarbeit
