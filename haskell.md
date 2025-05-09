---
layout: post
title: "Arbeit mit Haskell"
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
