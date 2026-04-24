# Formatlogik

## Zweck

Diese Datei dokumentiert die Formatentscheidung der Wissensarchitektur-Registry für YAML, JSON und JSONL. Ziel ist, Datenhaltung, Agentensteuerung, menschliche Lesbarkeit und spätere Systemexporte sauber zu trennen.

## Grundsatz

YAML und JSON sollen nicht beliebig vermischt werden. Beide Formate erhalten unterschiedliche Rollen:

- JSON oder JSONL für stabile, maschinenlesbare Datenobjekte.
- YAML für gut lesbare Konfigurationen, Agentenregeln und steuernde Metadaten.

## Begründung

JSON ist strenger, eindeutiger und besser geeignet für automatisierte Verarbeitung, Validierung, Schnittstellen und Registry-Einträge. Es reduziert Interpretationsspielraum und ist daher passend für Daten, die später von Agenten, Skripten oder Zielsystemen zuverlässig gelesen werden sollen.

YAML ist für Menschen oft besser lesbar, erlaubt Kommentare und eignet sich für Konfigurationsdateien, Prompts, Regelwerke und Einstellungen, die regelmäßig manuell gelesen oder angepasst werden. YAML ist jedoch anfälliger für Fehler durch Einrückungen und implizite Typinterpretationen.

## Rollenmodell

### JSON

JSON soll bevorzugt verwendet werden für:

- stabile Registry-Einträge,
- extrahierte Wissenselemente,
- Aufgabenabschlüsse,
- Entscheidungen,
- Nachweise,
- Problemspuren,
- maschinenverarbeitbare Datensätze,
- Schnittstellen- und Exportobjekte.

### JSONL

JSONL soll bevorzugt verwendet werden für:

- fortlaufende Logs,
- Klassifikationsverläufe,
- Änderungsereignisse,
- große Mengen gleichartiger Einzelobjekte,
- inkrementelle Verarbeitung durch Agenten oder Skripte.

### YAML

YAML darf bevorzugt verwendet werden für:

- Agentenregeln,
- Extraktionsregeln,
- Prompt-Metadaten,
- Mapping-Regeln,
- Routing- und Steuerungsdateien,
- menschlich gepflegte Konfigurationen,
- erläuternde Vorlagen, solange sie noch nicht als stabile maschinenverarbeitbare Datenhaltung dienen.

## Anwendungsregeln

1. Registry-Einträge, extrahierte Wissenselemente, Aufgabenabschlüsse, Entscheidungen, Nachweise und maschinenverarbeitbare Datensätze sollen bevorzugt als JSON oder JSONL gespeichert werden.
2. Konfigurationsdateien für Agenten, Extraktionsregeln, Prompt-Metadaten, Mapping-Regeln und Steuerungsdateien dürfen als YAML gespeichert werden.
3. Wenn eine Datei primär von Maschinen verarbeitet wird, verwende JSON.
4. Wenn eine Datei primär von Menschen gelesen, gepflegt oder kommentiert wird, verwende YAML.
5. YAML-Dateien dürfen auf JSON-Ausgabeformate verweisen, sollen aber selbst nicht die eigentliche Registry-Datenhaltung ersetzen.
6. JSON-Dateien sollen keine Kommentare enthalten. Erklärungen gehören in begleitende Markdown-Dokumentation oder in YAML-Konfigurationsdateien.
7. Für stabile Registry-Daten ist Eindeutigkeit wichtiger als maximale Lesbarkeit.

## Zielbild

- YAML = Steuerung, Konfiguration, Agentenregeln, menschlich lesbare Metadaten.
- JSON = Registry-Daten, Extraktionsergebnisse, Aufgabenobjekte, maschinenlesbare Wissenselemente.
- JSONL = fortlaufende Ereignis-, Klassifikations- und Änderungslogs.

## Übergangsregel

Das Repository enthält aktuell viele `.yml`-Dateien auch dort, wo perspektivisch JSON oder JSONL geeigneter sein kann. Diese bestehende Struktur wird durch diese Regel nicht automatisch ungültig.

Die Formatlogik gilt zunächst als Architekturentscheidung und Benennungsklarheit für neue Dateien, neue Datenhaltungen und zukünftige Migrationen. Bestehende YAML-Register bleiben gültig, bis eine eigene Migrationsentscheidung getroffen und dokumentiert wurde.

## Prüfregel für neue Artefakte

Vor dem Anlegen einer neuen strukturierten Datei ist zu prüfen:

- Ist die Datei ein stabiler Datenbestand oder ein Übergabeobjekt für Maschinen? Dann JSON oder JSONL verwenden.
- Ist die Datei eine steuernde, kommentierbare oder regelmäßig manuell gepflegte Konfiguration? Dann YAML verwenden.
- Ist die Datei erklärend, argumentierend oder analysierend? Dann Markdown verwenden.
