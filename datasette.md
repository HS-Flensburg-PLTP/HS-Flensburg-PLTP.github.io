---
layout: post
title: "CSV-Dateien lokal hosten"
date: 2025-05-22
---

Zum Bereitstellen einer CSV-Datei im JSON-Format werden zwei Tools benötigt:

- [Datasette](https://datasette.io/)
- [Sqlite-utils](https://sqlite-utils.datasette.io/en/stable/)

Die beiden Tools werden folgendermaßen installiert:

```
pip install datasette sqlite-utils
```


## CSV vorbereiten

Mit `sqlite-utils` wird die CSV-Datei in eine Sqlite-Tabelle konvertiert.
Dazu dient der folgende Aufruf.

```
sqlite-utils insert <DB-Name> <Tabellenname> <CSV-Datei> --csv --detect-types
```

`<DB-Name>` steht dabei für den Namen der SQLite-Datei.
Sollte die angegebene SQLite-Datei zuvor nicht existieren, erstellt das Kommando diese.
`<Tabellenname>` steht für den Namen der Tabelle, welche aus der CSV-Datei generiert wird.
Die Option `--csv` gibt an, dass es sich um eine CSV-Datei handelt und `--detect-types` sorgt dafür, dass Typen wie z.B. `Text`, `Integer`, etc. automatisch erkannt werden.
Sollte die CSV-Datei das Zeichen `;` statt `,` zur Trennung nutzen, kann die Option `--delimiter=";"` zum Kommando hinzugefügt werden.
Sollte die CSV-Datei bereits eine Spalte besitzen, welche die Daten eindeutig differenziert (eine Spalte mit `primary keys`), wie zum Beispiel eine ID, kann man mit dem Parameter `--pk=<Spaltenname>`, `sqlite-utils` mitteilen, diese Spalte als `primary key` zu verwenden, statt automatisch eine Spalte dafür anzulegen.

Weitere Informationen zum Importieren/Konvertieren einer CSV-Datei findet man in der [Dokumentation zu `sqlite-utils`](https://sqlite-utils.datasette.io/en/stable/cli.html#cli-insert-csv-tsv).


## JSON bereitstellen

Nachdem die SQLite-Datei erstellt wurde, kann man sie mit `Datasette` lokal hosten.
Die Daten können mit folgendem Befehl bereitgestellt werden.

```
datasette serve --cors <Dateiname/Verzeichnis>
```

Die Option `--cors` sorgt dafür, dass `datasette` den _Header_ `Access-Control-Allow-Origin: *` setzt.
Dadurch erlaubt der Browser einen Zugriff auf die Daten aus einer Elm-Frontend-Anwendung heraus.
`<Dateiname/Verzeichnis>` steht für die SQLite-Datei oder ein Verzeichnis, das nur SQLite-Dateien enthält, welches man bereitstellen will.
Der Befehl stellt eine Weboberfläche bereit, mit der man durch die Daten navigieren kann.
Wenn die SQLite-Datei `test_db` heißt und die Tabelle `test_tabelle`, kann man zum Beispiel unter `http://127.0.0.1:8001/test_db/test_tabelle` diese Weboberfläche erreichen.
Wenn man der URL `.json?_shape=array` anhängt, werden die Daten als JSON ausgeliefert.
Unter der URL `http://127.0.0.1:8001/test_db/test_tabelle.json?_shape=array` erhält man zum Beispiel folgendes Ergebnis.

```JSON
[
  {
    "rowid": 1,
    "test_feld1": "test1.1",
    "test_feld2": "test1.2"
  },
  {
    "rowid": 2,
    "test_feld1": "test2.1",
    "test_feld2": "test2.2"
  },
  {
    "rowid": 3,
    "test_feld1": "test3.1",
    "test_feld2": "test3.2"
  },
  {
    "rowid": 4,
    "test_feld1": "test4.1",
    "test_feld2": "test4.2"
  }
]
```

In diesem Beispiel hat die CSV-Datei keine Spalte mit IDs bereitgestellt, weshalb `sqlite-utils` eigenständig eine entsprechende Spalte hinzugefügt hat.
Weitere JSON-Darstellungsarten werden in der [Dokumentation von Datasette](https://docs.datasette.io/en/stable/json_api.html#different-shapes) beschrieben.

Datasette verwendet standardmäßig [Pagination](https://docs.datasette.io/en/stable/json_api.html#pagination) und zeigt daher nur die ersten 100 Datensätze an.
Der _Response Header_ enthält einen Link in der Form `<http://127.0.0.1:8001/test_db/test.json?_shape=array&_next=200>; rel="next"`, der angibt, unter welcher URL die nächste Seite erreichbar ist.
Falls dieser _Response Header_ nicht existiert, ist die letzte Seite der Daten erreicht.
