# Domänen

In diesem Verzeichnis liegen die domänenspezifischen Register der Wissensarchitektur. Jede Domäne bündelt die fachlichen Knoten, Beziehungen, Zuordnungen, Quellen und Verlaufsdaten für einen klar abgegrenzten Themenraum.

## Neue Domänen ergänzen

Eine neue Domäne sollte ergänzt werden, wenn eingehende Wissenselemente nicht belastbar in eine bestehende Domäne passen und sich ein stabiler, wiederkehrender Themenraum abzeichnet. Vor dem Anlegen einer neuen Domäne sollte immer das globale Domänenregister geprüft und bei Bedarf erweitert werden.

Für eine neue Domäne wird ein eigener Ordner unter `domänen/` angelegt. Der Ordnername sollte gut lesbar, deutsch geprägt und mit Unterstrichen statt Leerzeichen benannt sein.

## Pflichtdateien je Domäne

Jede Domäne muss mindestens diese Dateien enthalten:

- `kanonische_knoten.yml`
- `beziehungen.yml`
- `semantische_zuordnungen.yml`
- `verlaufsänderungen.yml`
- `quellen.yml`
- `klassifikationslog.yml`
- `thebrain_updates.yml`

## Funktion der domänenspezifischen Register

### `kanonische_knoten.yml`

Enthält die fachlich bestätigten Knoten der Domäne. Diese Datei bildet die stabilste Sicht auf das innerhalb der Domäne etablierte Wissen.

### `beziehungen.yml`

Dokumentiert, wie kanonische Knoten fachlich oder strukturell miteinander verbunden sind. Beziehungen helfen, die Domäne nicht nur als Liste, sondern als Wissensstruktur zu pflegen.

### `semantische_zuordnungen.yml`

Hält fest, wie eingehende Formulierungen, Synonyme oder Varianten auf kanonische Knoten abgebildet werden. Diese Datei ist zentral für Dublettenkontrolle und konsistente Klassifikation.

### `verlaufsänderungen.yml`

Dokumentiert die fachliche Entwicklung der Domäne in zeitlicher Reihenfolge. So bleiben Anlage, Umbenennung, Zusammenführung oder Ablösung nachvollziehbar.

### `quellen.yml`

Sammelt referenzierte Chats, Dokumente oder sonstige Herkunftshinweise, auf denen Domäneneinträge beruhen. Quellen schaffen Nachvollziehbarkeit und fachliche Rückverfolgbarkeit.

### `klassifikationslog.yml`

Hält fest, wie eingehende Wissenselemente einer Domäne oder einem kanonischen Knoten zugeordnet wurden. Dieses Log hilft bei späteren Prüfungen und Musterbildung.

### `thebrain_updates.yml`

Enthält vorbereitete Änderungen für TheBrain mit eigenem Status. Damit bleibt klar erkennbar, was fachlich beschlossen, was vorbereitet und was im Zielsystem bereits umgesetzt wurde.
