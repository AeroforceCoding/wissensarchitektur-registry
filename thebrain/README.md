# TheBrain-Schicht

Dieses Verzeichnis ergänzt die bestehende Wissensarchitektur um eine eigene Ziel-, Status- und Aufgabenlogik für TheBrain. Es dient dazu, THEBRAIN_TASK-Blöcke und vergleichbare abgeschlossene Aufgaben strukturiert zu erfassen, gegen bestehende Einträge zu prüfen, dedupliziert nachzuverfolgen und für die spätere Umsetzung in TheBrain vorzubereiten.

## Zweck des Bereichs

Der Bereich `thebrain/` ist die operative Steuerungsschicht zwischen bestätigter Registry-Logik und konkreten TheBrain-Aufgaben. Er hält fest:

- welche Aufgaben für TheBrain bereits erfasst wurden,
- wie neue Aufgaben gegen vorhandene Einträge geprüft wurden,
- welche Änderungen tatsächlich umgesetzt oder bestätigt wurden.

## Unterschied zwischen THEBRAIN_TASK, Aufgabenregister und Umsetzungsprotokoll

### THEBRAIN_TASK

Ein THEBRAIN_TASK ist ein eingehender Arbeitsblock oder eine explizit formulierte Aufgabe. Er ist zunächst Rohinput und noch kein belastbarer Registereintrag.

### Aufgabenregister

Das Aufgabenregister in `aufgabenregister.yml` ist die strukturierte, nachverfolgbare Liste erfasster TheBrain-Aufgaben. Dort werden Ziel-Brain, Zielast, Quellenbezug, Wiederholbarkeit, Strukturwirkung und aktueller Status einheitlich festgehalten.

### Umsetzungsprotokoll

Das Umsetzungsprotokoll in `umsetzungsprotokoll.yml` dokumentiert Statuswechsel und tatsächliche Änderungen in TheBrain. Es hält fest, wann eine vorgeschlagene Änderung geprüft, umgesetzt, bestätigt oder verworfen wurde und ob sich die Zielzuordnung geändert hat.

## Wie geprüft wird, ob eine Aufgabe bereits existiert

Neue THEBRAIN_TASKs werden gegen das bestehende Aufgabenregister geprüft. Dabei werden insbesondere Titel, Zusammenfassung, Ziel-Brain, Hauptast, Unterast, Strukturwirkung und beschriebene neue Strukturknoten verglichen. Die Ergebnisse dieser Prüfung werden in `zuordnungsprüfungen.yml` dokumentiert.

Ziel der Prüfung ist nicht nur die Suche nach exakten Dubletten, sondern auch die Erkennung von:

- gleicher Bedeutung bei abweichender Formulierung,
- gleichem Kern mit zusätzlichem Detail,
- ergänzenden Aufgaben,
- teilweisen Überschneidungen,
- möglichen Doppelaufgaben.

## Wie der Umsetzungsstatus in TheBrain verfolgt wird

Die operative Umsetzung in TheBrain wird zweistufig verfolgt:

1. Im Aufgabenregister über das Feld `umsetzungsstatus_thebrain`
2. Im Umsetzungsprotokoll über nachvollziehbare Statuswechsel mit Zeitbezug

Dadurch bleibt sauber getrennt, was als Aufgabe erfasst wurde, was bereits geprüft ist und was im Zielsystem wirklich umgesetzt oder bestätigt wurde.
