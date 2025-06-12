---
layout: post
title: "Arbeit mit Haskell"
date: 2025-06-06
---

Auf dieser Seite werden die Werkzeuge vorgestellt, die zur Arbeit mit Haskell im Rahmen eines Projektes oder einer Abschlussarbeit verwendet werden.

## GHCup

Die wichtigsten Werkzeuge können mit GHCup installiert und gemanagt werden.
Die [Installationsanleitung von GHCup](https://www.haskell.org/ghcup/install/) beschreibt, wie GHCup auf verschiedenen Plattformen installiert werden kann.
Dort gibt es auch ein Beispielvideo, das die Installation unter Windows zeigt.

GHCup sollte verwendet werden, um die Werkzeuge GHC, cabal, Stack und HLS zu installieren und zu aktualisieren.
Das Shell-Kommando `ghcup tui` startet eine textbasierte Anwendung, in der überprüft werden kann, welche Versionen von GHCup, Stack, HLS, cabal und GHC installiert sind.
Außerdem können hier neue Versionen dieser Werkzeuge installiert werden.
Mithilfe von GHCup kann man mehrere Versionen eines Werkzeuge parallel installieren.
Das heißt, es können zum Beispiel mehrere Versionen der Anwendung cabal installiert sein.
Mit GHCup wird dann eine dieser Versionen als aktuell verwendete Version ausgewählt.

Bitte im ersten Schritt mittels GHCup die empfohlenen Versionen von GHC, cabal, Stack und HLS installieren.


### GHC

Um Haskell-Code in Maschinencode zu übersetzen, wird ein Compiler benötigt.
Der am weitesten verbreitete Compiler ist der Glasgow Haskell Compiler (GHC).

### HLS (Haskell Language Server)

Der Haskell Language Server (HLS) wird genutzt, um in einer IDE Dienste wie _code completion_ oder Typinformationen anzubieten.

### Cabal und Stack

Cabal und Stack sind _build tools_.
Das heißt, diese Werkzeuge werden genutzt, um die Abhängigkeiten einer Haskell-Anwendung aufzulösen und ein Projekt zu bauen.
Cabal ist ein sehr grundlegendes Werkzeug, das auf Grundlage `.cabal`-Dateien Haskell-Projekte baut.
In der `.cabal`-Datei ist definiert, welche _build targets_ es gibt und welche Abhängigkeiten diese jeweils haben.

Stack fügt eine weitere Abstraktionsschicht hinzu und verwendet im Hintergrund cabal.
Statt eine global installierte Version des GHC zu verwenden, ist Stack in der Lage, für ein Haskell-Projekt eine lokale Version des GHC zu verwenden.
Dadurch ist ein Projekt unabhängig von der global installierten GHC-Version.
Ansonsten basiert Stack auf kuratierten Listen von Haskell-Paketen, die garantiert zusammenarbeiten.
Das heißt, Stack stellt Listen von Versionen von Haskell-Paketen zur Verfügung, bei denen geprüft wurde, dass diese Versionen ohne Probleme zusammenarbeiten.
Dieser Ansatz kann Probleme mit Paketen, die nicht miteinander kompatibel sind, sehr stark verringern.

## Weitere Werkzeuge

### VSCode-Erweiterung / HLS-Integration

Es gibt eine VSCode-Erweiterung namens Haskell von den Entwicklern des HLS, um diesen in VSCode zu verwenden.
Dafür den folgenden Schritten folgen:

1. Sicherstellen, dass HLS installiert ist.
   Falls es nicht installiert ist, das Werkzeug mittels `ghcup tui` installieren.
2. VSCode-Erweiterung `Haskell` installieren.

### Ormolu

[Ormolu](https://github.com/tweag/ormolu) ist ein _auto formatter_ für Haskell-Quellcode.
_Auto formatter_ sorgen dafür, dass Code einheitlich formatiert wird.
Die VSCode-Erweiterung unterstützt Ormolu direkt und bringt auch eine Version von Ormolu direkt mit.
Ormolu muss also nicht separat installiert werden.

Der _auto formatter_ Ormolu sollte zur Formatierung von Haskell-Quellcode verwendet werden.

### HLint

HLint ist ein Linter für Haskell.
Das heißt, das Werkzeug macht Vorschläge für Verbesserungen des Haskell-Codes.
Auch [HLint](https://github.com/ndmitchell/hlint) wird direkt durch die VSCode-Erweiterung unterstützt und muss nicht separat installiert werden.

In VSCode werden Code-Stellen, zu denen HLint Vorschläge hat, farblich unterstrichen.
Die Stellen werden auch unter "Probleme" aufgelistet.
Es gibt in VSCode drei Möglichkeiten, um die durch HLint vorgeschlagenen Änderungen am Code umzusetzen.

1. Über die betroffene Stelle im Code _hovern_.
   Es öffnet sich ein Dialog, der das Problem zeigt.
   Auf "schnelle Problembehandlung" klicken.
   Den gewünschten Vorschlag auswählen.
2. An die betroffene Stelle im Code klicken.
   Es erscheint ein Icon am linken Rand, dieses anklicken um eine Liste an Vorschlägen zu öffnen.
   Einen von den Vorschlägen auswählen.
3. Unter "Probleme" den Eintrag auswählen und auf das Glühbirnen-Icon klicken und die gewünschte Aktion auswählen.


## Datentypen für Zeichenketten

In Haskell gibt es drei Datentypen zur Arbeit mit Zeichenketten: `String`, `Text` und `ByteString`.
Hier wird ganz kurz erläutert, wie man diese Datentypen untereinander konvertieren kann.
Der Datentyp `String` ist der ursprüngliche Datentyp zur Darstellung von Zeichenketten in Haskell.
Dabei handelt es sich um ein Typsynonym für `[Char]`, also eine Liste von Zeichen.
Diese Darstellung ist bei längeren Zeichenketten recht ineffizient, da durch die Liste eine vergleichsweise teure Zeigerstruktur im Speicher angelegt wird.
Um dieses Problem zu umgehen wurden die Typen `Text` und `ByteString` von Bibliotheken eingeführt.
Der Typ `Text` ist eine speichereffizientere Darstellung von Zeichenketten.
Beim Typ `ByteString` handelt es sich eigentlich nicht um eine Darstellung von Zeichenketten, sondern um die rohen binären Daten dahinter.
Wenn man einen `ByteString` in Form von Zeichen lesen möchte, muss man daher angeben, wie die binären Daten, interpretiert werden sollen.
Man muss also angeben, wie die Bytes in Zeichen umgewandelt werden.

Für die späteren Code-Beispiele nutzen wir die folgenden Importe.

```haskell
import Data.Text (Text)
import qualified Data.Text as Text
import qualified Data.Text.Encoding as Text.Encoding
import Data.ByteString (ByteString)
import qualified Data.ByteString as ByteString
```

Die folgende Tabelle gibt an, wie die verschiedenen Datentypen ineinander konvertiert werden können.
Wenn man einen `ByteString` in einem `String` konvertieren möchte, muss man den Umweg über den Datentyp `Text` nehmen, also zwei der Funktionen nacheinander anwenden.

| Von          | Nach         | Funktion                        |
| ------------ | ------------ | ------------------------------- |
| `String`     | `Text`       | `Text.pack`                     |
| `Text`       | `String`     | `Text.unpack`                   |
| `ByteString` | `Text`       | `Text.Encoding.decodeUtf8`      |
| `Text`       | `ByteString` | `Text.Encoding.encodeUtf8`      |

Neben den standardmäßig strikten Implementierungen von `Text` und `ByteString` stellen die Bibliotheken noch _lazy_ Varianten dieser Datentypen zur Verfügung.
Die _lazy_ Datentypen heißen auch `Text` und `ByteString`, stammen aber aus anderen Modulen, was leicht zu Verwirrung führen kann, wenn Typfehler auftreten.

Für die Arbeit mit den _lazy_ Varianten nutzen wir die folgenden Importe.

```haskell
import qualified Data.Text.Lazy as Lazy (Text)
import qualified Data.Text.Lazy as Text.Lazy
import qualified Data.Text.Lazy.Encoding as Text.Lazy.Encoding
import qualified Data.ByteString.Lazy as Lazy (ByteString)
import qualified Data.ByteString.Lazy as ByteString.Lazy
```

Die folgende Tabelle gibt an, wie die _lazy_ Varianten ineinander und in die strikten Varianten konvertiert werden können.

| Von               | Nach              | Funktion                        |
| ----------------- | ----------------- | ------------------------------- |
| `String`          | `Lazy.Text`       | `Text.Lazy.pack`                |
| `Lazy.Text`       | `String`          | `Text.Lazy.pack`                |
| `Lazy.ByteString` | `Lazy.Text`       | `Text.Lazy.Encoding.decodeUtf8` |
| `Lazy.Text`       | `Lazy.ByteString` | `Text.Lazy.Encoding.encodeUtf8` |
| `Text`            | `Lazy.Text`       | `Text.Lazy.fromStrict`          |
| `Lazy.Text`       | `Text`            | `Text.Lazy.toStrict`            |
| `ByteString`      | `Lazy.ByteString` | `ByteString.fromStrict`         |
| `Lazy.ByteString` | `ByteString`      | `ByteString.toStrict`           |
