# Wissensarchitektur-Registry

Dieses Repository bildet die zentrale, versionierte Wissensarchitektur für die Extraktion, Domänenzuordnung, Klassifikation, semantische Prüfung und strukturierte Weiterverarbeitung von Chatinhalten. Es dient als gemeinsamer Referenzpunkt für Regeln, Register, Prompts, Vorlagen und nachvollziehbare Änderungen, damit Wissen über verschiedene Themenräume hinweg konsistent erfasst und weiterentwickelt werden kann.

## Zweck und Zielbild

Ziel ist eine belastbare Steuerungsschicht zwischen eingehenden Chatinhalten und ihrer strukturierten Verarbeitung. Aus einzelnen Aussagen, Entscheidungen, Anforderungen und offenen Punkten sollen wiederverwendbare Wissenselemente entstehen, die:

- einer fachlich passenden Domäne zugeordnet werden,
- gegen bestehende Register und kanonische Knoten abgeglichen werden,
- semantisch konsistent weiterentwickelt werden,
- Dubletten und widersprüchliche Strukturentwicklung vermeiden,
- als vorbereitete Änderungen für TheBrain nachvollziehbar bereitstehen.

Das Repository ist damit kein operatives Fachsystem, sondern das versionierte Regel- und Registry-System, das die Qualität und Nachvollziehbarkeit der Wissenspflege absichert.

Zusätzlich enthält das Repository nun eine eigene TheBrain-Schicht unter `thebrain/`, in der THEBRAIN_TASK-Blöcke, Aufgabenstatus, Ziel-Brains, Dublettenprüfungen und Umsetzungsprotokolle getrennt von den fachlichen Domänenregistern geführt werden.

## Rolle von GitHub, Codex und TheBrain

### GitHub

GitHub ist der versionierte Speicher- und Prüfkontext für diese Architektur. Hier werden Regeln, Register, Vorlagen, Änderungen und Reviews dokumentiert. Pull Requests, Merge-Prüfungen und Changelogs sorgen dafür, dass fachliche und strukturelle Entwicklung nachvollziehbar bleibt.

### Codex

Codex unterstützt die operative Verarbeitung von Chatinhalten anhand der hier hinterlegten Prompts, Regeln und Register. Dazu gehören insbesondere Extraktion, Domänenzuordnung, Registry-Abgleich, semantische Prüfung, Vorbereitung von Governance-Entscheidungen, die strukturierte Aufbereitung von Änderungsentwürfen sowie agentisches Handeln mit hoher Transparenz und klaren Bestätigungspflichten.

Für projektverankerte Analysearbeit existiert zusätzlich eine erste Agentenschicht mit `AGENTS.md`, spezialisierten Skills unter `.agents/skills/` und einer methodischen Arbeitsstruktur unter `agentensystem/`. Diese Schicht ergänzt die Wissensarchitektur, ersetzt sie aber nicht.

### TheBrain

TheBrain ist das Zielsystem für die spätere Wissensdarstellung und Beziehungspflege. Dieses Repository führt keine direkte Wissensvisualisierung aus, sondern bereitet TheBrain-Änderungen so vor, dass Knoten, Beziehungen, Etiketten und Strukturentscheidungen kontrolliert und konsistent umgesetzt werden können.

## Globale Steuerung und domänenspezifische Bereiche

Die globale Ebene enthält die allgemeinen Steuerungsregeln der Wissensarchitektur. Dazu gehören Typen, Etiketten, Beziehungstypen, Routingregeln, Domänenregister und Klassifikationslogik. Diese Inhalte gelten domänenübergreifend und schaffen eine gemeinsame Sprache.

Die domänenspezifischen Bereiche enthalten dagegen die fachliche Ausprägung einzelner Themenräume. Dort liegen kanonische Knoten, domänenspezifische Beziehungen, semantische Zuordnungen, Quellen, Verlaufsänderungen, Klassifikationsentscheidungen und vorbereitete TheBrain-Updates. So bleibt die globale Steuerung stabil, während sich Fachdomänen unabhängig weiterentwickeln können.

Für neue strukturierte Dateien gilt eine Formatlogik: YAML dient vor allem der menschlich lesbaren Steuerung, Konfiguration und Agentenregelung; JSON oder JSONL sollen für stabile maschinenlesbare Registry-Daten, Extraktionsergebnisse, Aufgabenobjekte und spätere Exporte bevorzugt werden. Die Regel ist in `agentensystem/regelwerk/formatlogik.md` dokumentiert und hebt bestehende YAML-Dateien nicht automatisch auf.

Ergänzend dazu beschreibt `agentensystem/regelwerk/repository_schichten.md` die strukturelle Rollenlogik des Repositories. Registry-Daten, Konfiguration, Prompts, Automatisierung, Laufzeitumgebung und Dokumentation sollen unterscheidbar bleiben. Die Bereiche `automation/`, `runtime/` und `docs/` sind vorbereitete Andockpunkte für spätere Ausbaustufen, enthalten aber noch keine produktive Automatisierung oder Laufzeitdefinition.

Zwischen laufender Aufgabenbearbeitung und kanonischer Registry-Integration entsteht zusätzlich eine leichte Evidenz- und Kontextschicht. Dort werden Kontexte, Artefaktstatus und Vorlagen für validierte Informationsblöcke definiert, damit Screenshots, Bilddateien und andere Nachweise erst nach erfolgreicher Verdichtung in die eigentliche Wissensarchitektur einfließen.

Ergänzend dazu existiert eine agentische Steuerungsschicht. Sie definiert, welche vorbereitenden Schritte der Agent autonom ausführen darf, welche Annahmen er offenlegen muss und in welchen Fällen der Anwender ausdrücklich bestätigen soll.

## Operative Prompt-Reihenfolge

Die kanonische Prompt-Bibliothek liegt unter `prompts/`. Eine schnelle Übersicht bietet `prompts/prompt_index.md`. Intern genutzte Workflow-Prompts liegen unter `prompts/registry_workflow/`, extern verwendbare Chat- und Repo-Anweisungen unter `prompts/externe_anwendung/`. Die Registry-Workflow-Prompts bilden folgende logische Verarbeitungskette:

1. `prompts/registry_workflow/01_eingang/chat_extraktion.md`
   Extrahiert aus einem Chat die relevanten Wissenselemente, Aussagen, Entscheidungen, Prüfbedarfe und offenen Punkte.
2. `prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md`
   Ordnet die extrahierten Wissenselemente einer bestehenden Domäne oder einem begründeten neuen Domänenkandidaten zu.
3. `prompts/registry_workflow/03_pruefung/registry_abgleich.md`
   Prüft innerhalb der Ziel-Domäne, ob bereits passende kanonische Knoten, Beziehungen oder Registereinträge existieren.
4. `prompts/registry_workflow/03_pruefung/semantische_prüfung.md`
   Wird nur dann genutzt, wenn Bedeutungsnähe, Mehrdeutigkeit, Dublettengefahr oder mögliche Widersprüche vorliegen.
5. `prompts/registry_workflow/04_entscheidung/governance_entscheidung.md`
   Wird nur dann aufgerufen, wenn eine echte Strukturänderung, ein neuer Standard oder eine konfliktträchtige Einordnung entschieden werden muss.
6. `prompts/registry_workflow/05_aktualisierung/registry_aktualisieren.md`
   Überführt bestätigte Ergebnisse in konkrete Registry-Änderungen.
7. `prompts/registry_workflow/06_thebrain/thebrain_update_vorbereiten.md`
   Formuliert daraus umsetzbare, aber noch getrennt nachverfolgbare Änderungen für TheBrain.

Ergänzend dazu steuern `prompts/registry_workflow/06_thebrain/thebrain_task_erfassen.md`, `prompts/registry_workflow/06_thebrain/thebrain_task_prüfen.md` und `prompts/registry_workflow/05_aktualisierung/aufgabenliste_aktualisieren.md` die operative Erfassung, Prüfung und Nachverfolgung einzelner TheBrain-Aufgaben.

Für lange oder fortgeschrittene Chats außerhalb dieses Repositories kann vorgeschaltet `prompts/externe_anwendung/01_eingang/chat_uebergabeblock_erzeugen.md` verwendet werden. Dieser externe Prompt erzeugt einen kompakten Übergabeblock, der danach mit der internen Chat-Extraktion in einen kanonischen `chat_extrakt` überführt wird.

## Nutzen des Repositories

Der Nutzen dieser Registry liegt in drei Kernwirkungen:

- Konsistenz: Gleiche Inhalte werden nicht mehrfach und nicht widersprüchlich aufgebaut.
- Nachvollziehbarkeit: Entscheidungen, Änderungen und semantische Entwicklungen bleiben über Git nachvollziehbar.
- Skalierbarkeit: Neue Domänen, Regeln und Fachräume können ergänzt werden, ohne die Gesamtlogik der Wissensarchitektur zu verlieren.

## Grundsatz für die Pflege

Neue Inhalte sollten zuerst als strukturierte Extrakte oder Kandidaten erfasst, dann domänenspezifisch geprüft und erst nach bestätigter Einordnung in Register oder vorbereitete TheBrain-Updates übernommen werden. Dadurch bleibt die Wissensarchitektur lernfähig, aber kontrolliert.

Für aufgabenbasierte Erkenntnisse gilt ergänzend: Rohartefakte und Nachweise werden zunächst benannt, kontextualisiert und bei Bedarf zu einem validierten Informationsblock verdichtet. Erst dieser Block wird anschließend in die reguläre Workflow-Kette der Registry überführt.
