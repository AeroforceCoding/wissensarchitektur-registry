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

## Architekturschichten

Die strukturelle Rollenlogik ist in `agentensystem/regelwerk/architekturschichten.md` dokumentiert. Sie trennt Registry-Daten, Konfiguration, Prompts, Automatisierung, Laufzeitumgebung und Dokumentation, damit spätere Ausbaustufen wie GitHub Actions, Docker Compose, Kubernetes, lokale LLMs, RAG-Systeme und mehrere Agenten ohne Formatbruch ergänzt werden können.

## Agentenrollen

Die grundlegenden Rollen eines späteren Multi-Agent-Systems sind in `agentensystem/regelwerk/agentenrollen.yml` maschinenlesbar beschrieben und in `agentensystem/rollen.md` erläutert. Die Rollen bilden Analyse, Architekturprüfung, Umsetzung, Prüfung, Dokumentation und Freigabe/Kontrolle ab.

Die zugehörigen Übergabe- und Ergebnisformate sind in `agentensystem/regelwerk/agenten_uebergabeformate.yml` definiert. Sie beschreiben, welche Arbeitsobjekte zwischen Rollen weitergegeben werden sollen, ohne bereits eine technische Orchestrierung oder Laufzeitumgebung zu behaupten.

Diese Rollenbeschreibung ist keine produktive Orchestrierung. Sie dient als strukturierte Grundlage für spätere Agentenprozesse und hält die Grenze zwischen Vorschlag, Umsetzung, Prüfung und menschlicher Freigabe explizit.

## Anwenderhandlungen

Die Situationen, in denen der Anwender nach aktuellem Stand aktiv handeln, entscheiden oder Evidenz nachreichen muss, sind in `agentensystem/regelwerk/anwenderhandlungen.yml` definiert. Die lesbare Gesamtsimulation dazu liegt in `docs/systemsimulation_und_anwenderhandlungen.md`.

## Wichtige Grenze

Bestätigte Erkenntnisse dürfen nicht mit Arbeitsannahmen vermischt werden. Persistente Gedächtnisdateien sind Hilfsstrukturen des Agenten und keine kanonische Primärwahrheit des Repositories.
