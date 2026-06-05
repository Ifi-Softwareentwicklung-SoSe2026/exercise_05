<!--

author:   Volker Göhler
email:    volker.goehler@informatik.tu-freiberg.de
version:  0.0.3
language: de
narrator: Deutsch Female

edit: true
date: 2026-06-04

comment:  Übung Softwareentwicklung 05 -- User Story und UML

import: https://raw.githubusercontent.com/liascript-templates/plantUML/master/README.md

link:   https://raw.githubusercontent.com/vgoehler/LiaScript_CSS_Provider/refs/heads/main/dist/university.css

tags: [Sommersemester2026, Softwareentwicklung, Übung05]

-->

[![LiaScript Course](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://liascript.github.io/course/?https://raw.githubusercontent.com/Ifi-Softwareentwicklung-SoSe2026/exercise_05/refs/heads/main/README.md)

# Aufgabe 05

Softwareentwicklung SoSe2026
============================

## User Story

Als Benutzer eines Fußball-Wettannahmesystems
möchte ich Wetten auf die Spiele der Fußball-Weltmeisterschaft (inkl. Gruppenphase) abgeben und verwalten,
damit ich meine Prognosen für die Spiele dokumentieren und Wetten mit Quoten versehen kann.

### Akzeptanzkriterien

Turnierstruktur
--------------------

- Das System modelliert die Gruppenphase der Fußball-Weltmeisterschaft.
- Jede Gruppe enthält Mannschaften (Klasse Mannschaft mit Name).
- Jedes Spiel (Klasse Spiel) hat:

   - Zwei Mannschaften (Heim und Auswärts).
   - Ein Datum und eine Uhrzeit.
   - Ein Ergebnis (initial leer).
   - Eine eindeutige Spiel-ID.


Wettfunktionalität
--------------------

- Jedes Spiel kann Wettquoten für verschiedene Wett-Typen speichern (z. B. Siegwette, Ergebniswette).
- Eine Wette (Klasse Wette) besteht aus:

   - Einem Benutzer (Klasse Benutzer mit Name und Guthaben).
   - Einem Wett-Typ (z. B. Siegwette, Ergebniswette).
   - Einer Quote (z. B. 1.80, 3.50).
   - Einem Einsatz (Geldbetrag).

Datenpersistenz
--------------------

- Die Turniertabelle (Spiele und Mannschaften) muss in einer Datei gespeichert und geladen werden können (z. B. JSON).
- Wetten und Quoten werden ebenfalls persistent gespeichert.

Benutzerinteraktion (Konsolenanwendung)
--------------------

Das System wird über Command-Line-Parameter gesteuert:

- `new`: Initialisiert die Turniertabelle (statisch, da das Turnier vorgegeben ist).
- `print`: Gibt alle Spiele der Tabelle mit ihren IDs aus.
- `set <spielid> <Wetttyp> <Wettquote>`: Setzt eine Wettquote für ein Spiel und einen Wett-Typ.
- `get <spielid> <Wetttyp>`: Gibt die aktuelle Wettquote für ein Spiel und einen Wett-Typ aus.
- `bid <player> <spielid> <Wetttyp> <amount>`: Platziert eine Wette für einen Benutzer.
- `result <spielid> <Tore-1.Mannschaft>:<Tore-2.Mannschaft>`: Trägt das Spielergebnis ein und löst die Auswertung der Wetten aus.


### Stufenweise Implementierung

Design und Implementierung soll jeweils in einem Branch stattfinden.
Jede Stufe soll funktional sein und die vorherige Stufe erweitern.
Die Stufen sollen einzeln in main gemerged werden, damit die Funktionalität schrittweise erweitert wird.

Stufe 1 (Grundlage):
--------------------

- Modellierung der Turniertabelle (Mannschaften und Spiele).
- Speichern/Laden der Turnierdaten.
- `new` und `print` Befehle implementieren.

Stufe 2 (Erweitert):
--------------------

- Hinzufügen von Wettquoten für Spiele.
- `set` und `get` Befehle implementieren.

Stufe 3 (Fortgeschritten):
--------------------

- Platzieren von Wetten durch Benutzer (`bid`-Befehl).
- Verwaltung von Benutzer-Guthaben.
- Eingabe von Spielergebnissen und Auswertung der Wetten (`result`-Befehl).


## Aufgabe: PlantUML-Antwortfeld

Ergänzen Sie im folgenden PlantUML-Block Ihre Lösung.

- [plantUml Editor](https://pantuml.com)
- paste and copy your code! Mit Reloads verlieren Sie Ihre Eingaben, daher vorher sichern!

```text @plantUML
@startuml

class Arbeiten_Sie_hier{
    + have: string
    ~ fun: string
    - coding: string
}

@enduml
```
