# Architekturschichten

## Zweck

Diese Datei beschreibt die Architekturschichten, über die Inhalte im Repository mit der größeren Wissensarchitektur verbunden werden. Ziel ist, Wissen, Regeln, Prompts, Konfiguration, Automatisierung, Laufzeitumgebung und Dokumentation so zu trennen, dass spätere Ausbaustufen mit GitHub Actions, Docker Compose, Kubernetes, lokalen LLMs, RAG-Systemen und mehreren Agenten ohne Formatbruch ergänzt werden können.

Diese Regel implementiert keine Automatisierung und keine Laufzeitumgebung. Sie legt nur fest, welche Rolle die jeweiligen Schichten im Repository und in der anschließenden Gesamtarchitektur haben und welche Formate dafür vorgesehen sind.

## Grundproblem

Die zentrale Gefahr in einem wachsenden KI-Wissenssystem ist nicht nur fehlende Dokumentation, sondern vermischte Bedeutung von Dateien. Bei jeder Datei muss erkennbar bleiben:

- Ist das Wissen?
- Ist das eine Regel?
- Ist das eine Konfiguration?
- Ist das ein Prompt?
- Ist das ein Workflow?
- Ist das eine technische Laufzeitbeschreibung?
- Ist das Automatisierungscode?
- Ist das nur Dokumentation?

Wenn diese Rollen verschwimmen, wird das Repository später schwer migrierbar, schwer validierbar und schwer durch Agenten zuverlässig nutzbar.

## Schichtenmodell

Das Schichtenmodell beschreibt die Art einer Ablage oder Datei. Ergänzend dazu gilt ein Flussmodell, das beschreibt, an welcher Stelle eines Arbeitsverlaufs ein Bereich typischerweise steht:

- Eingabe: Rohmaterial, Übergaben, Extrakte, Kandidaten und noch nicht bestätigte Zwischenstände.
- Verarbeitung: Prompts, Workflows, Prüfungen, Zuordnungen, Entscheidungen und Aktualisierungsschritte.
- Funktionen: Regeln, Handlungen, Agentenrollen, Statuslogik, Formatlogik und wiederverwendbare Steuerungslogik.
- Ausgabe: bestätigte Registerdaten, vorbereitete Zielsystemänderungen, Dokumentation, Exporte und später abrufbare Wissensstände.

Diese Begriffe sind kein zusätzlicher Zwang für Ordnernamen. Sie dienen als Orientierungsmodell, damit neue Bereiche intuitiv auffindbar bleiben: Eingehendes Material gehört in Eingabe- oder Kandidatenbereiche, Arbeitslogik in Verarbeitung oder Funktionen, bestätigte oder entnehmbare Ergebnisse in Ausgabe- oder Registerbereiche.

### Registry-Daten

Zweck: Stabile, maschinenlesbare Wissensobjekte und geprüfte Datenstände.

Typische Inhalte:

- kanonische Knoten,
- Beziehungen,
- Quellen,
- semantische Zuordnungen,
- Extraktionsergebnisse,
- Informationsblöcke,
- Problemspuren,
- Aufgabenobjekte,
- vorbereitete Zielsystemänderungen.

Bevorzugte Formate:

- JSON für stabile Einzelobjekte und Datenbestände,
- JSONL für fortlaufende Ereignisse, Logs, Extraktionspakete und Änderungsverläufe.

Aktuelle Bereiche:

- `domänen/`
- `intake/`
- `thebrain/`
- `vorlagen/`

Hinweis: Bestehende YAML-Dateien in diesen Bereichen bleiben gültig, bis eine eigene Migrationsentscheidung getroffen wurde. Neue stabile Datenobjekte sollen bevorzugt JSON oder JSONL verwenden.

### Konfiguration und Steuerung

Zweck: Menschlich lesbare Regeln und Einstellungen, die Prozesse, Agenten oder Zuordnungen steuern.

Typische Inhalte:

- Domänenregister,
- Routing-Regeln,
- Statuswerte,
- Agentenfunktionen,
- Mapping-Regeln,
- Bestätigungsregeln,
- spätere GitHub-Actions-Workflows,
- spätere Docker-Compose-Dateien,
- spätere Kubernetes-Manifeste.

Bevorzugtes Format:

- YAML.

Aktuelle Bereiche:

- `global/`
- `workflows/`
- `agentensystem/regelwerk/`
- `.agents/skills/`

Zukünftige Andockpunkte:

- `.github/workflows/` für GitHub Actions,
- `runtime/compose/` oder `compose.yml` für Docker Compose,
- `runtime/kubernetes/` für Kubernetes-Manifeste.

### Prompts

Zweck: Arbeitsanweisungen für interne Registry-Verarbeitung und externe Anwendung in Chats oder anderen Repositories.

Typische Inhalte:

- interne Registry-Workflow-Prompts,
- externe Chat-Anweisungen,
- Repo-Erweiterungsprompts,
- Prompt-Metadaten,
- erwartete Ausgabeformate.

Bevorzugtes Format:

- Markdown für Promptdateien,
- JSON für datenorientierte Prompt-Ausgaben.

Aktueller Bereich:

- `prompts/`

### Automatisierung

Zweck: Validierung, Transformation, Export, Import, Synchronisation und spätere technische Ausführung von Verarbeitungsschritten.

Typische Inhalte:

- JSON-Schema-Validierung,
- Formatmigrationen,
- Export nach TheBrain, Obsidian oder andere Zielsysteme,
- Import von Chat-Extraktionspaketen,
- RAG-Index-Erzeugung,
- lokale LLM- oder Agenten-Orchestrierung.

Bevorzugte Sprache:

- Python als Standard für Datenverarbeitung, Validierung, lokale LLM-/RAG-Anbindung und agentische Ausbaustufen.

JavaScript oder TypeScript ist sinnvoll, wenn:

- eine Weboberfläche entsteht,
- ein Node-basiertes Tooling notwendig wird,
- bestehende Zielsysteme bessere JavaScript-SDKs haben,
- UI-nahe Interaktion oder Browserintegration im Vordergrund steht.

Zukünftiger Andockpunkt:

- `automation/`

### Laufzeitumgebung

Zweck: Beschreibt, wie spätere Dienste, Agentenprozesse, lokale Modelle, RAG-Komponenten oder Synchronisationsprozesse ausgeführt werden.

Typische Inhalte:

- Docker-Compose-Konfigurationen,
- Kubernetes-Manifeste,
- Umgebungsvariablen-Vorlagen,
- Laufzeitprofile,
- lokale Dienste auf Synology NAS oder anderen Hosts.

Bevorzugte Formate:

- YAML für Docker Compose und Kubernetes,
- Markdown für Erklärung,
- `.env.example` für beispielhafte Umgebungsvariablen ohne Geheimnisse.

Zukünftiger Andockpunkt:

- `runtime/`

### Dokumentation

Zweck: Menschliche Erklärung von Architektur, Konzepten, Entscheidungen, Betriebsmodellen und Nutzung.

Bevorzugtes Format:

- Markdown.

Aktuelle Bereiche:

- `README.md`
- `changelog/`
- Bereichs-READMEs
- `agentensystem/`

Zukünftiger Andockpunkt:

- `docs/`

## Entscheidung Python vs. JavaScript

Für die nächste Automatisierungsstufe ist Python die sinnvollere Standardsprache.

Begründung:

- Python ist stark für JSON/JSONL-Verarbeitung, Validierung und Transformation.
- Python hat ein sehr gutes Ökosystem für lokale LLMs, Embeddings, RAG, Datenpipelines und Automatisierung.
- Python passt gut zu Synology- oder Server-basierten Hintergrundprozessen.
- Python ist für agentische Analyse- und Verarbeitungsskripte meist direkter als JavaScript.

JavaScript oder TypeScript sollte nicht ausgeschlossen werden, aber als ergänzende Schicht betrachtet werden:

- für Web-UIs,
- für interaktive Dashboards,
- für Browser-nahe Workflows,
- für Zielsysteme mit besserer Node-Unterstützung.

## Nicht jetzt implementieren

Folgende Dinge sind perspektivisch vorgesehen, aber aktuell nicht anzulegen, solange es keinen konkreten Bedarf gibt:

- GitHub Actions Workflows,
- Docker-Compose-Dateien,
- Kubernetes-Manifeste,
- produktive Automatisierungsskripte,
- RAG-Index-Pipelines,
- lokale LLM-Laufzeitprofile,
- Multi-Agent-Orchestrierung.

Stattdessen sollen zunächst Rollen, Pfade, Formate und Grenzen klar bleiben.

## Prüfregel für neue Dateien

Vor dem Anlegen einer neuen Datei ist zu entscheiden:

1. Enthält sie stabiles Wissen oder maschinenlesbare Daten? Dann Registry-Daten, bevorzugt JSON oder JSONL.
2. Steuert sie Verhalten, Zuordnung, Status oder Infrastruktur? Dann Konfiguration, bevorzugt YAML.
3. Ist sie eine Arbeitsanweisung an einen Menschen oder Agenten? Dann Prompt, bevorzugt Markdown mit JSON-Ausgabeformaten.
4. Führt sie Verarbeitung aus? Dann Automatisierung, bevorzugt Python.
5. Beschreibt sie technische Ausführung? Dann Laufzeitumgebung, bevorzugt YAML plus Markdown.
6. Erklärt sie Konzepte oder Entscheidungen? Dann Dokumentation, bevorzugt Markdown.

Zusätzlich ist zu prüfen, welche Flussrolle die Datei hat:

1. Eingabe: Wird hier etwas aufgenommen, zwischengespeichert oder als Kandidat geführt?
2. Verarbeitung: Wird hier etwas geprüft, zugeordnet, entschieden oder umgeformt?
3. Funktion: Definiert die Datei eine wiederverwendbare Regel, Rolle, Handlung oder Fähigkeit?
4. Ausgabe: Ist die Datei ein bestätigtes Ergebnis, eine Zielsystemvorbereitung, eine Dokumentation oder ein abrufbarer Wissensstand?

Wenn Schicht und Flussrolle auseinanderfallen, soll die Benennung oder Dokumentation diese Doppelfunktion erklären.
