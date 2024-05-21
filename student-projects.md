---
layout: post
title: Abschlussarbeiten/Projekte
date: 2024-05-21
---

Die hier aufgeführten Bachelor- und Masterarbeiten können in Absprache auch in Form von Bachelor- bzw. Masterprojekten bearbeitet werden.
Dabei wird ggf. der Umfang des Projektes an die Gegebenheiten des Projektes angepasst.
Falls Sie sich für andere Themen aus den Bereichen moderne Methoden der Softwareentwicklung, Compilerbau, Programmiersprachen oder Algorithmen interessieren, wenden Sie sich bitte einfach per Mail an [mich](mailto:jan.christiansen@hs-flensburg.de).


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


### Eine empirische Untersuchung von Piping in Elm

In dieser Arbeit soll die Verwendung der Operatoren `|>` und `<|` in Elm-Projekten bei GitHub untersucht werden.
Aus mehreren vorhergehenden Abschlussarbeiten steht bereits eine Anwendung in Haskell zur Verfügung, die Elm-Repos von GitHub klont und für den Quelltext abstrakte Syntaxbäume (AST) erzeugt.
Um die Elm-Anwendungen zu parsen, also einen AST aus dem Quelltext zu erzeugen, wird die Bibliothek [elm-format](https://github.com/HS-Flensburg-PLTP/elm-format) verwendet.
Um einfach Informationen aus dem AST zu extrahieren, nutzt die Haskell-Anwendung die Ideen aus [Uniform Boilerplate and List Processing](https://ndmitchell.com/downloads/paper-uniform_boilerplate_and_list_processing-30_sep_2007.pdf).

Die Informationen, die zu den Operatoren `|>` und `<|` erhoben werden, können sich an der Publikation [An Empirical Study of Method Chaining in Java](https://static.csg.ci.i.u-tokyo.ac.jp/papers/20/nakamaru-msr2020.pdf) orientieren.
Es soll zum Beispiel untersucht werden, wie häufig die Operatoren (ggf. im Vergleich zu normalen Funktionsanwendungen) verwendet werden.
Außerdem soll untersucht werden, ob es eher lange Sequenzen von Verwendungen der Operatoren gibt oder ob die Operatoren eher einzeln verwendet werden.
Daneben soll untersucht werden, in welchen Fällen die Operatoren `|>` und `<|` vor allem verwendet werden.
Zum Beispiel wird der Operator `|>` gern zusammen mit Funktionen wie `andThen` und `andMap` verwendet.
Außerdem wird der Operator `<|` gern verwendet, wenn das Argument, auf das die Funktion angewendet wird, mehrere Zeilen überspannt.
Es soll untersicht werden, ob die Operatoren `|>` und `<|` vor allem in diesen Fällen verwendet werden oder ob es noch weitere wiederkehrende Anwendungsfälle gibt.

Falls die Zeit es erlaubt, sind ähnliche Untersuchungen auch für die Operatoren `>>` und `<<` möglich.

**Voraussetzungen:** Grundkenntnisse in Haskell, gute Kenntnisse in Elm  
**Geeignet als:** Bachelorarbeit


### Replikation einer Studie

In dieser Arbeit soll die Studie [Meaningful Identifier Names: The Case of Single-Letter Variables](https://www.cs.huji.ac.il/w~feit/papers/SingleLetter17ICPC.pdf) repliziert werden.
Die Studie untersucht, wie lang die Bezeichner in den Programmiersprachen C, Java, JavaScript, PHP, und Perl sind und wie häufig Einbuchstabenbezeichner sind.
Dazu werden Projekte von GitHub analysiert.
Bei [GitHub](https://github.com/sarahgin/Meaningful-Identifier-Names-The-Case-of-Single-Letter-Variables) stehen die Programme zur Verfügung, die zur Durchführung der Studie genutzt wurden.
Dabei werden kleine Python-Skripte genutzt und ein paar sprachspezifische Skripte zur Extraktion der Variablen aus Programmen in den verschiedenen Programmiersprachen.
Bei der Replikation sollen insbesondere die Ergebnisse für die Programmiersprache JavaScript genauer überprüft werden.
Die Ergebnisse für die Programmiersprache JavaScript lassen vermuten, dass ggf. minifizierte JavaScript-Dateien mit analysiert wurden.
Das folgende Zitat stammt aus der Original-Publikation.

> This (together with the fact that single-letter variables are very common as shown in Figure 1) may indicate that the dataset includes some minified code that was not identified correctly and removed by our filter.

Daher soll nach der Replikation insbesondere ein Konzept entwickelt werden, um minifizierte JavaScript-Module auszuschließen.

**Voraussetzungen:** Kenntnisse in Python  
**Geeignet als:** Bachelorarbeit


### Web-Anwendung zur Datenvisualisierung

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
**Geeignet als:** Bachelorarbeit


<!-- ### Typinformationen für Elm-Projekte

In dieser Arbeit soll eine bestehende Anwendung, die Elm-Projekte von GitHub sammelt und analysiert, verbessert werden.
Dazu soll

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

## Programming Feedback

<!-- ### Redundante Fälle in `case`-Ausdrücken

Um Studierenden Rückmeldungen zur Ihren Programmierabgaben in der Programmiersprache Elm zu geben, wird die Bibliothek [elm-review](https://github.com/jfmengels/elm-review/tree/2.13.2) genutzt.
In dieser Arbeit soll eine Regel für die Bibliothek `elm-review` entwickelt werden, die anmerkt, wenn ein Fall eines `case`-Ausdruckes redundant ist.
Ein Fall ist redundant, wenn man den Fall entfernen kann, ohne dass sich das Verhalten der Funktion verändert.
Die folgende Definition enthält eine Regel, die redundant ist.

```elm
snocList : List a -> a -> List a
snocList list element =
    case list of
        [] ->
            [ element ]

        [ head ] ->
            [ head, element ]

        head :: rest ->
            head :: snocList rest element
```

Wenn die zweite Regel aus dieser Definition entfernt wird, verändert sich das Verhalten dieser Funktion nicht.
Wenn die Funktion mit einer Liste der Form `[ head ]` aufgerufen wird, wird die dritte Regeln genommen, falls die zweite Regel nicht existiert.
In diesem Fall wird der Aufruf `snocList [] element` durchgeführt.
Dieser Aufruf liefert als Ergebnis `[ element ]`.
Somit erhalten wir von der dritten Regeln als Ergebnis `head :: [ element ]`, was identisch zu `[ head, element ]` ist.
Daher kann in dieser Definition die zweite Regel entfernt werden.
-->

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

<!-- Um zu überprüfen, ob ein Fall entfernt werden kann, muss zuerst überprüft werden, ob es zwei _Pattern_ gibt, die sich überlappen.
In der Funktion `snocList` überlappen zum Beispiel die _Pattern_ `[ head ]` und `head :: rest`, da das zweite _Pattern_ ein Spezialfall des ersten _Pattern_ ist.
Aus den beiden _Pattern_ kann nun eine Substitution berechnet werden.
Eine Substitution beschreibt, wie man aus dem einen _Pattern_ das andere _Pattern_ erzeugen kann.
Im Fall von `snocList` besteht die Substitution aus `rest -> []`. -->


### Reimplementierungen erkennen

Um Studierenden Rückmeldungen zur Ihren Programmierabgaben in der Programmiersprache Elm zu geben, wird die Bibliothek [elm-review](https://github.com/jfmengels/elm-review/tree/2.13.2) genutzt.
In dieser Arbeit soll eine Regel für die Bibliothek `elm-review` entwickelt werden, die anmerkt, wenn eine Funktion eine Reimplementierung einer vordefinierten Funktion ist.

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
Zum Beispiel nutzt die Funktion `incAll` im Unterschied zu `List.map` ein Unterstrich-_Pattern_.
Außerdem prüft die Funktion `List.map` zuerst das _Pattern_ `[]`.
Daher soll die zu prüfende Funktion zuerst normalisiert werden.
Das heißt, zuerst wird das Unterstrich-_Pattern_ durch ein konkretes _Pattern_ ersetzt.
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

Im nächsten Schritt werden die _Pattern_ in eine vorgegeben Reihenfolge gebracht und wir erhalten die folgende Definition.

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

Als Beispiele für die Erkennung von Reimplementierungen können die Funktionen `List.length`, `List.filter`, `List.any`, `List.map` und `List.concatMap` betrachtet weden.

**Voraussetzungen:** Gute Kenntnisse in Elm  
**Geeignet als:** Bachelorarbeit


## Web-Anwendungen

### Priorities

In dieser Arbeit soll eine Web-Anwendung entwickelt werden.
Die Anwendung erlaubt es eine Umfrage zu erstellen, bei der Teilnehmer\*innen aus einer vorgegebenen Liste von Optionen eine festgegebene Anzahl an Optionen auswählen können.
Die Grundstruktur der Anwendung soll sich an Diensten wie [Doodle](doodle.com) orientieren.
Außerdem kann man die gewählten Optionen in eine Prioritätenreihenfolge bringen.
Für die Anwendung muss also sowohl ein _Interface_ für die Konfigurator\*innen als auch für Teilnehmer\*innen entwickelt werden.

Die Daten werden in einem Backend gespeichert.
Die Daten können zum Beispiel mittels [Supabase](https://supabase.com) oder [PostgREST](https://postgrest.org) zur gespeichert werden.
Um die Optionen möglichst optimal auf die Teilnehmer\*innen zu verteilen, wird eine Zuordnung von Optionen zu Teilnehmer\*innen mithilfe von linearer Programmierung durchgeführt.
Da aktuell keine bessere Lösung zur Verfügung steht, kann die Zuordnung mithilfe der JavaScript-Bibliothek [glpk.js](https://github.com/hgourvest/glpk.js) berechnet werden.
Auf lange Sicht wäre es besser, einen Microservice anzubieten, der eine Instanz mittels der C-Bibliothek [GNU Linear Programming Kit](https://en.wikipedia.org/wiki/GNU_Linear_Programming_Kit) löst und das Ergebnis in geeigneter Form zurückliefert.

**Voraussetzungen:** Gute Kenntnisse in Elm  
**Geeignet als:** Bachelorarbeit
