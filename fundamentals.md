---
layout: post
title: Grundlagen
date: 2025-01-20
---

Diese Seite erklärt ein paar Grundbegriffe, die zum Beispiel in den [Projektthemen](student-projects.md) immer wieder auftauchen.


### Parser

Ein Parser ist eine Anwendung bzw. Bibliothek, die eine Zeichenkette (_String_) als Eingabe erhält.
Der Parser übernimmt zwei Aufgaben.
Zum einen überprüft der Parser, ob die Zeichenkette einem vorgegebenen Format entspricht.
Falls die Zeichenkette nicht dem Format entspricht, liefert der Parser einen Fehler als Ergebnis.
Falls die Zeichenkette dem Format entspricht, liefert der Parser einen Wert des strukturierten Datentyps als Ergebnis, der die Struktur der Zeichenkette abbildet.
Im Fall einer objektorientierten Programmiersprache liefert der Parser zum Beispiel eine Objektstruktur als Ergebnis.
Im Fall einer Programmiersprache wie Elm oder Haskell liefert der Parser einen Wert eines algebraischen Datentyps.
Parser werden für die Verarbeitung von formalen Dateiformaten verwendet, etwa wenn eine JSON-, XML- oder YAML-Datei verarbeitet werden soll.
Ein Parser wird aber auch verwendet, wenn ein Programm in einer Programmiersprache verarbeitet werden soll.
So enthält zum Beispiel jeder Compiler einen Parser.
Wenn im weitesten Sinne eine Programmiersprache durch einen Parser verarbeitet wird, ist das Ergebnis ein abstrakter Syntaxbaum.


### Abstrakter Syntaxbaum (AST)

Ein abstrakter Syntaxbaum (_Abstract Syntax Tree_) ist ein strukturierter Datentyp, der die Struktur der Syntax einer Sprache abbildet.
Dabei bezieht sich der Begriff _abstrakt_ auf den Umstand, dass einige Aspekte der konkreten Syntax in der strukturierten Darstellung nicht mehr enthalten sind.
Zum Beispiel werden Leerzeichen, die in der konkreten Syntax vorkommen, im abstrakten Syntaxbaum nicht mehr repräsentiert.
Außerdem wird die Klammerung, die in der abstrakten Syntax explizit dargestellt werden muss, in der abstrakten Syntax durch die Schachtelung der Datenstruktur repräsentiert.
Wir betrachten das folgende sehr einfache Java-Programm.

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

Wenn wir das obige Java-Programm durch einen Parser verarbeiten lassen, erhalten wir zum Beispiel etwas vereinfacht die folgende Baumstruktur.

```
CompilationUnit
|
├── empty list of imports
|
└── ClassDeclaration
    |
    ├── "HelloWorld"
    |
    └── MethodDeclaration
        |
        ├── "main"
        |
        ├── Parameter
        |   |
        |   ├── "args"
        |   |
        |   └── ArrayType
        |       |
        |       |
        ...     ...
```

Das obige Diagramm stellt eine Baumstruktur dar.
Jeder Knoten dieser Baumstruktur wird dabei durch eine Java-Klasse repräsentiert.
Zum Beispiel wird der Knoten `CompilationUnit` durch die folgende Java-Klasse repräsentiert.
```java
public class CompilationUnit extends Node {

    private List<ImportDeclaration> imports;

    private List<TypeDeclaration> types;

    ...
}
```
Das heißt, jede `CompilationUnit` besitzt eine Liste von Importen und eine Liste von Typdeklarationen.
In unserem Beispiel enthält die Datei keine Importe, daher ist die Liste der Importe leer.
Die Datei enthält aber eine Deklaration einer Klasse, daher hat die Liste `types` der `CompilationUnit` einen Eintrag vom Typ `ClassDeclaration`.
Eine `ClassDeclaration` ist wiederum wie folgt definiert.
```java
public class ClassDeclaration extends TypeDeclaration {

    private String name;

    private List<BodyDeclaration> declarations;

    ...
}
```
Das heißt, eine `ClassDeclaration` enthält eine Liste von `BodyDeclaration`s, also etwa Deklarationen von Attributen und Methoden.
Diese Liste enthält in unserem Beispiel eine `MethodDeclaration` und die `MethodDeclaration` enthält einen `String,` nämlich den Namen der Methode und eine Liste von Parametern.
Ein Parameter besteht aus einem Namen, ebenfalls in der Form eines `String` und jeweils einen Typ.

<!-- ### Concrete Syntax Tree (CST)

Ein _Concrete Syntax Tree_ (konkreter Syntaxbaum) ist ein strukturierter Datentyp, der die Struktur der Syntax einer Sprache abbildet.
Dabei bezieht sich das _Concrete_ auf den Umstand, dass alle oder die meisten Aspekte der Syntax auch in der Datenstruktur repräsentiert sind.
Ein Beispiel ist etwa, dass Klammern in einem abstrakten Syntaxbaum durch die Struktur des Datentyps  -->
