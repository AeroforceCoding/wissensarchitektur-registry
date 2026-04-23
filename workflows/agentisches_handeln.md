# Agentisches Handeln

Diese Datei beschreibt, wie der Agent innerhalb der Wissensarchitektur-Registry mit hoher Autonomie arbeiten soll, ohne dass Transparenz, Nachvollziehbarkeit oder Bestätigungssicherheit verloren gehen.

## Zielbild

Der Agent soll so viel wie möglich selbstständig vorbereiten, strukturieren, benennen, verdichten und einordnen. Gleichzeitig soll der Anwender jederzeit erkennen können:

- was der Agent gerade tut,
- auf welcher Annahme dies beruht,
- wann nur ein Vorschlag vorliegt,
- wann eine ausdrückliche Bestätigung erforderlich ist.

## Autonomiestufen

### 1. Autonom ausführbar

Diese Handlungen darf der Agent eigenständig ausführen, solange er sie transparent dokumentiert:

- Eingänge einordnen
- Dateinamen vorschlagen
- Metadaten und Schlagworte ableiten
- Artefakt- und Informationsblock-Entwürfe erzeugen
- nächsten Workflow-Schritt empfehlen
- nicht-destruktive Register- oder Prompt-Entwürfe vorbereiten

### 2. Autonom mit Hinweis

Diese Handlungen darf der Agent vorbereiten oder ausführen, muss aber klar sichtbar machen, was daraus folgt:

- bestehende Kontexte als wahrscheinlich passend markieren
- Domänen mit Unsicherheitsgrad zuordnen
- alternative Folgepfade benennen
- Artefakte als nur referenziert oder informationsblockrelevant einstufen

### 3. Bestätigung vor Ausführung

Vor diesen Handlungen ist eine ausdrückliche Bestätigung des Anwenders nötig:

- neue kanonische Strukturen anlegen
- neue Domänen einführen
- bestehende Einträge zusammenführen, ersetzen oder verwerfen
- externe Dateien tatsächlich verschieben, umbenennen oder löschen
- TheBrain-Zielzuordnungen mit geringer Sicherheit übernehmen
- destruktive Änderungen im Repository vornehmen

### 4. Stoppen und klären

Der Agent soll aktiv stoppen und klären, wenn:

- Evidenz widersprüchlich ist,
- der Aufgabenerfolg unklar bleibt,
- mehrere Strukturpfade gleich plausibel sind,
- eine falsche Entscheidung nur schwer revidierbar wäre.

## Leitprinzipien

### Transparenz vor Geschwindigkeit

Hohe Autonomie ist erwünscht, aber nie auf Kosten der Nachvollziehbarkeit. Der Agent soll immer benennen, welche Annahmen er getroffen hat.

### Vorschlag vor Strukturwirkung

Wenn eine Handlung Strukturwirkung hat, soll der Agent zunächst einen klaren Vorschlag oder Entwurf erzeugen, bevor er eine bestätigungspflichtige Änderung ausführt.

### Reversible Schritte zuerst

Der Agent soll bevorzugt solche Schritte autonom ausführen, die leicht überprüfbar, korrigierbar oder rückbaubar sind.

### Nachweis vor Kanonisierung

Screenshots, Bilddateien und andere Artefakte gelten zunächst als Evidenz. Erst nach Verdichtung in einen validierten Informationsblock dürfen sie in die reguläre Registry-Logik einfließen.

## Typischer agentischer Ablauf

1. Eingang erkennen und einordnen
2. Falls nötig Artefakte benennen und metadatieren
3. Kontext zuordnen oder vorschlagen
4. Bei abgeschlossener Aufgabe Informationsblock verdichten
5. Nächsten Workflow-Schritt bestimmen
6. Bei Strukturwirkung Bestätigung einholen
7. Erst danach Registry oder TheBrain vorbereiten

## Verweise

- `global/agentische_funktionen.yml`
- `global/bestätigungsregeln.yml`
- `global/kontext_vokabular.yml`
- `global/artefakt_statuswerte.yml`
