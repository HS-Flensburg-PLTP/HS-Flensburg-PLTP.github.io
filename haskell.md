---
layout: post
title: "Arbeit mit Haskell"
---

Auf dieser Seite werden die Werkzeuge vorgestellt, die zur Arbeit mit Haskell im Rahmen eines Projektes oder einer Abschlussarbeit verwendet werden sollten.

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

### GHC

Um Haskell-Code in Maschinencode zu übersetzen, wird ein Compiler benötigt.
Der am weitesten verbreitete Compiler ist der Glasgow Haskell Compiler (GHC).

### HLS (Haskell Language Server)

Der Haskell Language Server (HLS) wird genutzt, um in einer IDE Dienste wie _code completion_ oder Typinformationen anzubieten.

### Cabal und Stack

Cabal und Stack sind _build tools_.
Das heißt, diese Werkzeuge werden genutzt, um die Abhängigkeiten einer Haskell-Anwendung aufzulösen und ein Projekt zu bauen.
Cabal ist ein sehr grundlegendes Werkzeug, das in der Lage, auf Grundlage von `cabal`-Dateien Haskell-Projekte zu bauen.

Stack fügt eine weitere Abstraktionsschicht hinzu und verwendet im Hintergrund cabal.
Statt eine global installierte Version des GHC zu verwenden, ist Stack in der Lage, für ein Haskell-Projekt eine lokale Version des GHC zu verwenden.
Dadurch ist ein Projekt unabhängig von der global installierten GHC-Version.
Ansonsten basiert Stack auf kuratierten Listen von Haskell-Paketen, die garantiert zusammenarbeiten.
Das heißt, Stack stellt Listen von Versionen von Haskell-Paketen zur Verfügung, bei denen geprüft wurde, dass diese Versionen ohne Probleme zusammenarbeiten.
Dieser Ansatz kann Probleme mit Paketen, die nicht miteinander kompatibel sind, sehr stark verringern.

## Weitere Werkzeuge

### VSCode-Erweiterung / HLS-Integration

Es gibt eine VSCode-Erweiterung namens Haskell von den Entwicklern des HLS um diesen in VSCode zu verwenden.
Dafür den folgenden Schritten folgen:

1. Sicherstellen HLS ist installiert, falls dies nicht zutrifft, dies zum Beispiel mittels `ghcup tui` nachholen.
2. VSCode-Erweiterung `Haskell` installieren.

### Ormolu

[Ormolu](https://github.com/tweag/ormolu) ist ein Formatierer für Haskell-Quellcode.
Formatierer sorgen dafür, dass Code einheitlich formatiert wird.
Die VSCode-Erweiterung unterstützt Ormolu direkt und bringt auch eine Version von Ormolu direkt mit.
Ormolu muss also nicht separat installiert werden.

### HLint

HLint ist ein Linter für Haskell.
Das heißt, das Werkzeug macht Vorschläge für Verbesserungen des Haskell-Codes.
Auch [HLint](https://github.com/ndmitchell/hlint) wird direkt durch die VSCode-Erweiterung unterstützt und muss nicht separat installiert werden.

In VSCode werden Code-Stellen, zu denen HLint Vorschläge hat, farblich unterstrichen.
Die Stellen werden auch unter "Probleme" aufgelistet.
Es gibt in VSCode drei Möglichkeiten, um die durch HLint vorgeschlagenen Änderungen am Code umzusetzen.

1. Über die betroffene Stelle im Code hovern.
   Es öffnet sich ein Dialog, der das Problem zeigt.
   Auf "schnelle Problembehandlung" klicken.
   Den gewünschten Vorschlag auswählen.
2. An die betroffene Stelle im Code klicken.
   Es erscheint ein Icon am linken Rand, dieses anklicken um eine Liste an Vorschlägen zu öffnen.
   Einen von den Vorschlägen auswählen.
3. Unter "Probleme" den Eintrag auswählen und auf das Glühbirnen-Icon klicken und die gewünschte Aktion auswählen.

## Anwendungen mit Cabal / Stack installieren

Über `cabal install` / `stack install` werden ausführbare Dateien aus dem Haskell-Projekt im aktuellen Verzeichnis erzeugt.
Als Argument kann auch der Name eines Haskell-Paketes angegeben werden, das dann mit seinen Abhängigkeiten von [Hackage](https://hackage.haskell.org/) geladen wird.
Dabei können vorher mit `info` Angaben zum Haskell-Paket ausgegeben und mit `update` die Liste der bekannten Haskell-Pakete aktuell gehalten werden.

Nach erfolgreicher Installation wird der Installationspfad angegeben. Bei Cabal ist das standardmäßig der `bin`-Unterordner im Cabalverzeichnis und bei Stack: <br>
UNIX: `$HOME/.local/bin` <br>
Windows: `%APPDATA%\local\bin`

Um die Anwendungen einfach in der Konsole und in Skripten verwenden zu können, sollte dieser Pfad Teil der Umgebungsvariable `PATH` sein.
Diese enthält die Verzeichnisse, in der das System nach ausführbaren Dateien sucht.
