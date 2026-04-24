# Änderungen

Dieses Changelog dokumentiert nachvollziehbar, wann welche Änderung an der Wissensarchitektur vorgenommen wurde.

## Struktur

Jeder Eintrag enthält:

- Datum
- Änderungstyp
- Betroffene Datei oder Domäne
- Kurzbeschreibung

## Einträge

| Datum | Änderungstyp | Betroffene Datei oder Domäne | Kurzbeschreibung |
| --- | --- | --- | --- |
| 2026-04-23 | Initialisierung | Repository gesamt | Grundstruktur der Wissensarchitektur-Registry mit globalen Registern, Prompts, Workflows, Domänen, Vorlagen und Review-Ablagen angelegt. |
| 2026-04-23 | Erweiterung | TheBrain-Schicht | Ziel-Brains, Statuswerte, Aufgabenregister, Zuordnungsprüfungen, Umsetzungsprotokoll und ergänzende Prompts für THEBRAIN_TASK-Verarbeitung angelegt. |
| 2026-04-23 | Erweiterung | Evidenz- und Kontextschicht | Globales Kontextvokabular, Artefaktstatuswerte sowie Vorlagen für Artefakte und validierte Informationsblöcke ergänzt. |
| 2026-04-23 | Erweiterung | Agentische Steuerungsschicht | Agentische Funktionen, Bestätigungsregeln, agentische Ablaufdokumentation und operative Eingangsprompts für Artefakte und Aufgabenabschlüsse ergänzt. |
| 2026-04-23 | Erweiterung | Repo-verankerte Agentenschicht | `AGENTS.md`, erste Skills unter `.agents/skills/` sowie `agentensystem/` für Gedächtnis, Verträge und Analysevorlagen ergänzt. |
| 2026-04-24 | Präzisierung | Agentensystem | Benennungen im Agentensystem auf `regelwerk`, `aenderungsarten.md` und `bestaetigte_erkenntnisse.md` geschärft sowie `letzter_stand.md` auf Kanban-Logik mit `Backlog`, `Naechste_Schritte`, `In_Arbeit` und `Abgeschlossen` umgestellt. |
| 2026-04-24 | Erweiterung | Prompt-Bibliothek | Wiederverwendbaren Strukturprompt zur Erweiterung anderer Repositories um das aktuelle Agentensystem ergänzt und im Prompt-Index verankert. |
| 2026-04-24 | Erweiterung | Prompt-Bibliothek | Initial- und Zusatzanweisung für Wissensarbeits-Chats ergänzt, damit neue und laufende Chats gezielt auf spätere Chat-Extraktion, Registry-Verarbeitung und TheBrain-Update-Vorbereitung ausgerichtet werden können. |
| 2026-04-24 | Präzisierung | Agentisches Arbeiten | Regel ergänzt, dass sinnvolle Repository-Erweiterungen einen kurzen commitfähigen Beschreibungstext erhalten, der sich am Changelog orientiert. |
| 2026-04-24 | Strukturierung | Prompt-Bibliothek | Prompt-Bibliothek nach internem `registry_workflow` und extern verwendbarer `externe_anwendung` getrennt, Pfade aktualisiert und ergänzende Bereichs-READMEs angelegt. |
| 2026-04-24 | Erweiterung | Eingangsschicht | Externen Prompt zur Erzeugung kompakter Chat-Übergabeblöcke ergänzt und interne Chat-Extraktion für Übergabeblöcke als Eingabe erweitert. |
| 2026-04-24 | Erweiterung | Problemspur | Prompt und Vorlage zur parallelen Erfassung offener Probleme aus nicht abgeschlossenen Sessions ergänzt, inklusive Zweckdienlichkeitsprüfung vor Wissensabgleich oder Aufgabenableitung. |
| 2026-04-24 | Architekturregel | Formatlogik | Formatentscheidung ergänzt: JSON oder JSONL für stabile maschinenlesbare Datenobjekte, YAML für Konfigurationen, Agentenregeln und steuernde Metadaten; bestehende YAML-Dateien bleiben bis zu einer Migrationsentscheidung gültig. |
| 2026-04-24 | Formatumstellung | Prompt-Bibliothek und Vorlagen | Datenorientierte Prompt-Ausgaben von YAML auf JSON umgestellt und Vorlagen für maschinenverarbeitbare Objekte von `.yml` nach `.json` konvertiert. |
| 2026-04-24 | Architekturregel | Repository-Schichten | Rollenlogik für Registry-Daten, Konfiguration, Prompts, Automatisierung, Laufzeitumgebung und Dokumentation ergänzt sowie vorbereitende Andockbereiche `automation/`, `runtime/` und `docs/` angelegt. |
| 2026-04-24 | Erweiterung | Agentensystem | Maschinenlesbare Übersicht der sechs grundlegenden Agentenrollen ergänzt und Rollenlogik für spätere Multi-Agent-Orchestrierung dokumentiert. |
| 2026-04-24 | Erweiterung | Agentensystem | Standardisierte Übergabe- und Ergebnisformate für die sechs Agentenrollen ergänzt und Zusammenspiel der Rollen im agentischen Ablauf dokumentiert. |
| 2026-04-24 | Erweiterung | Anwenderführung | Systemsimulation eines Registry-Eintrags ergänzt, Situationen für notwendige Anwenderhandlungen maschinenlesbar dokumentiert und JSON-Vorlage für Anwenderhandlungsereignisse angelegt. |
| 2026-04-24 | Dokumentation | Anwenderführung | Anwenderorientierte Anleitung zum aktuellen Systemstand ergänzt und als Grundlage für ein Word-Dokument vorbereitet. |
| 2026-04-24 | Dokumentation | Einrichtung | Gesicherte Erkenntnisse aus dem aktuellen Einrichtungsstand des Repositories dokumentiert, um verlorene Chatkontexte nicht zur einzigen Quelle der Entstehungsgeschichte zu machen. |
| 2026-04-24 | Präzisierung | Agentensystem | `repository_schichten.md` in `architekturschichten.md` umbenannt, damit die Datei klarer die Verbindung zwischen Repo-Inhalt und Gesamtarchitektur beschreibt. |
| 2026-04-24 | Strukturierung | Prompt-Bibliothek | Handlungsregister für Prompts ergänzt, Prompt-Index um Handlungsspalte erweitert und externe Repo-Erweiterung als eigene Handlung `repo_erweiterung_vorbereiten` einsortiert. |
| 2026-04-24 | Architekturregel | Benennungslogik | Flussmodell aus Eingabe, Verarbeitung, Funktionen und Ausgabe als zusätzliche Orientierung für Bereichs- und Kontextbenennungen ergänzt. |
| 2026-04-24 | Erweiterung | Eingangsschicht | Prompt zur Transformation freier Wissensrohstoffe wie Notizen, Einfälle, Reflexionen, Lernergebnisse, Zitate und externe Dateien in Informationsblöcke ergänzt. |
