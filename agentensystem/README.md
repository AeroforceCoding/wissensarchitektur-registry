# Agentensystem

Dieser Bereich verankert Codex als projektbezogenen Analyseagenten im Repository. Er ersetzt die Primärarchitektur nicht, sondern ergänzt sie um methodische Arbeitsmittel für Analyse, Arbeitsstände und vorsichtige Fortführung zwischen Läufen.

## Warum es diesen Bereich gibt

Die Wissensarchitektur selbst bleibt die kanonische Primärstruktur. Der Agentenbereich dient nur dazu, Arbeitsstände, methodische Regeln, Skills und Vorlagen so zu organisieren, dass wiederkehrende Architekturarbeit anschlussfähig bleibt.

## Methodische Trennung

Der Bereich trennt bewusst zwischen:

- Regeln und Einstiegsvorgaben
- Skills
- Gedächtnis
- Regelwerk
- Vorlagen

## Formatlogik

Für neue strukturierte Artefakte gilt die Formatentscheidung aus `agentensystem/regelwerk/formatlogik.md`: JSON oder JSONL für stabile maschinenlesbare Datenobjekte, YAML für menschlich lesbare Konfigurationen, Agentenregeln und steuernde Metadaten.

Bestehende YAML-Register bleiben gültig, bis eine eigene Migrationsentscheidung getroffen wurde. Die Formatlogik dient zunächst der Benennungsklarheit und der Orientierung für neue Registry-Daten, Exporte und agentische Verarbeitung.

## Wichtige Grenze

Bestätigte Erkenntnisse dürfen nicht mit Arbeitsannahmen vermischt werden. Persistente Gedächtnisdateien sind Hilfsstrukturen des Agenten und keine kanonische Primärwahrheit des Repositories.
