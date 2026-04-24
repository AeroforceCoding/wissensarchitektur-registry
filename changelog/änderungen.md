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
