# Einrichtungsstand Und Gesicherte Erkenntnisse

Stand: 2026-04-24

## Zweck

Diese Dokumentation hält fest, welche Erkenntnisse aus der bisherigen Einrichtung der Wissensarchitektur-Registry bereits belastbar genug sind, um als eigene Systemdokumentation geführt zu werden.

Die Grundlage dieser Datei ist nicht ein früherer Chatverlauf, sondern der aktuell beobachtbare Repository-Zustand: README-Dateien, Changelog, Workflow-Dokumentation, Regelwerk, Prompts, Vorlagen und agentische Struktur.

## Warum Diese Doku Nötig Ist

Zwischenzeitlich wurden Arbeitschats neu geöffnet oder nicht vollständig extrahiert. Dadurch sind Teile der ursprünglichen Entstehungsgeschichte nicht mehr direkt aus dem Chat rekonstruierbar.

Trotzdem ist die bisherige Einrichtung nicht verloren: Viele Entscheidungen und Erkenntnisse sind bereits im Repository selbst sichtbar. Diese Datei sammelt die daraus ableitbaren, dokumentationsfähigen Erkenntnisse.

## Gesicherter Befund Aus Dem Repository

### 1. Das Repository Ist Die Primärquelle

Das Repository ist als kanonische Primärquelle der Wissensarchitektur angelegt. TheBrain und mögliche weitere Systeme sind Ziel-, Navigations- oder Spiegelschichten, aber nicht führend für den kanonischen Wissensstand.

Belege im Repo:

- `README.md`
- `AGENTS.md`
- `workflows/verarbeitungslogik.md`
- `agentensystem/README.md`

Dokumentationsfähige Erkenntnis:

Die Wissensarchitektur soll nicht von verstreuten Chats, TheBrain-Knoten oder einzelnen Notizen abhängig sein. Der stabile Wissensstand wird versioniert im Repository geführt.

### 2. Der Kernworkflow Ist Explizit Definiert

Der Standardprozess für neue Wissensinhalte ist im Repo dokumentiert:

1. Chat-Extraktion
2. Domänen-Zuordnung
3. Registry-Abgleich
4. Semantische Prüfung bei Bedarf
5. Governance-Entscheidung bei Strukturwirkung
6. Registry-Aktualisierung
7. TheBrain-Update-Vorbereitung

Belege im Repo:

- `workflows/prompt_abfolge.md`
- `workflows/verarbeitungslogik.md`
- `prompts/registry_workflow/`

Dokumentationsfähige Erkenntnis:

Das System trennt Rohkommunikation, Prüfung, Registry-Änderung und Zielsystemumsetzung bewusst voneinander. Ein Chat-Extrakt ist noch kein Registry-Eintrag, und eine vorbereitete TheBrain-Änderung ist noch keine Umsetzung.

### 3. Es Gibt Drei Aktuelle Fachdomänen

Das Domänenregister enthält aktuell:

- `m365_sharepoint`
- `hr_data_hub`
- `wissenssystem_thebrain`

Beleg im Repo:

- `global/domänenregister.yml`

Dokumentationsfähige Erkenntnis:

Neue Inhalte sollen nicht beliebig abgelegt werden, sondern zuerst einer fachlich führenden Domäne zugeordnet werden. Wenn keine Domäne passt, entsteht zunächst ein Domänenkandidat und keine automatische neue Domäne.

### 4. Prompts Sind Nach Interner Und Externer Anwendung Getrennt

Die Prompt-Bibliothek trennt zwischen:

- internen Registry-Workflow-Prompts unter `prompts/registry_workflow/`
- extern verwendbaren Prompts unter `prompts/externe_anwendung/`

Belege im Repo:

- `prompts/README.md`
- `prompts/prompt_index.md`
- `prompts/registry_workflow/README.md`
- `prompts/externe_anwendung/README.md`

Dokumentationsfähige Erkenntnis:

Nicht jeder Prompt hat dieselbe Rolle. Manche Prompts steuern die kanonische Verarbeitung im Repository, andere bereiten externe Chats nur für diese Verarbeitung vor.

### 5. Lange Externe Chats Werden Über Übergabeblöcke Angebunden

Für lange oder fortgeschrittene Chats gibt es den externen Prompt `chat_uebergabeblock_erzeugen.md`. Dieser erzeugt einen kompakten JSON-Übergabeblock, der anschließend intern durch die Chat-Extraktion verarbeitet wird.

Belege im Repo:

- `prompts/externe_anwendung/01_eingang/chat_uebergabeblock_erzeugen.md`
- `prompts/registry_workflow/01_eingang/chat_extraktion.md`
- `workflows/prompt_abfolge.md`

Dokumentationsfähige Erkenntnis:

Das System berücksichtigt, dass alte oder lange Chatverläufe oft nicht vollständig kopierbar sind. Ein Übergabeblock ersetzt aber keine Registry-Entscheidung, sondern ist nur eine vorbereitete Eingabe.

### 6. Offene Probleme Haben Einen Eigenen Pfad

Nicht abgeschlossene Sessions werden nicht künstlich als erfolgreiche Erkenntnis verarbeitet. Dafür gibt es die Problemspur.

Belege im Repo:

- `prompts/registry_workflow/01_eingang/session_problemspur_erfassen.md`
- `vorlagen/problemspur_vorlage.json`
- `workflows/prompt_abfolge.md`

Dokumentationsfähige Erkenntnis:

Das System trennt erfolgreiche Wissensextraktion von offenen Problemen. Offene Probleme können dokumentiert, auf Zweckdienlichkeit geprüft und später in Aufgaben oder Untersuchungen überführt werden.

### 7. Es Gibt Eine Klare Formatentscheidung

Die Formatlogik lautet:

- YAML für Konfiguration, Steuerung, Agentenregeln und menschlich gepflegte Metadaten
- JSON für stabile maschinenlesbare Datenobjekte
- JSONL für fortlaufende Ereignisse, Logs und Extraktionspakete
- Markdown für Erklärung, Architektur, Prompts und Dokumentation

Beleg im Repo:

- `agentensystem/regelwerk/formatlogik.md`

Dokumentationsfähige Erkenntnis:

Das Repository soll nicht durch beliebige Formatmischung wachsen. Die Formatentscheidung ist eine Architekturregel für spätere Automatisierung, Validierung und Exporte.

### 8. Repository-Schichten Sind Bereits Definiert

Das Repo unterscheidet zwischen:

- Registry-Daten
- Konfiguration und Steuerung
- Prompts
- Automatisierung
- Laufzeitumgebung
- Dokumentation

Beleg im Repo:

- `agentensystem/regelwerk/repository_schichten.md`

Dokumentationsfähige Erkenntnis:

Die Struktur ist bewusst so vorbereitet, dass GitHub Actions, Docker Compose, Kubernetes, lokale LLMs, RAG-Systeme und mehrere Agenten später ergänzt werden können, ohne jetzt schon implementiert zu sein.

### 9. Python Ist Als Bevorzugte Automatisierungssprache Vorgesehen

Für spätere Automatisierung wird Python als Standardsprache bevorzugt. JavaScript oder TypeScript bleibt ergänzend sinnvoll, wenn Weboberflächen, Browserintegration oder Node-nahe Zielsysteme entstehen.

Beleg im Repo:

- `agentensystem/regelwerk/repository_schichten.md`

Dokumentationsfähige Erkenntnis:

Die nächste technische Ausbaustufe sollte wahrscheinlich bei Validierung, Transformation, JSON/JSONL-Verarbeitung, RAG-Indexierung oder Exporten mit Python beginnen.

### 10. Agentische Rollen Sind Inhaltlich Definiert

Das Agentensystem enthält sechs Rollen:

- Analyse-Agent
- Architektur-Agent
- Umsetzungs-Agent
- Prüf-Agent
- Dokumentations-Agent
- Freigabe-/Kontroll-Agent

Belege im Repo:

- `agentensystem/regelwerk/agentenrollen.yml`
- `agentensystem/rollen.md`

Dokumentationsfähige Erkenntnis:

Das System ist für spätere Multi-Agent-Arbeit vorbereitet, behauptet aber keine produktive Orchestrierung. Die Rollen trennen Analyse, Architekturprüfung, Umsetzung, Prüfung, Dokumentation und Kontrolle.

### 11. Agentische Übergabeformate Sind Definiert

Jede Agentenrolle hat ein eigenes Übergabe- oder Ergebnisformat:

- `analyse_ergebnis`
- `architektur_ergebnis`
- `umsetzung_ergebnis`
- `pruefung_ergebnis`
- `dokumentation_ergebnis`
- `freigabe_kontroll_ergebnis`

Beleg im Repo:

- `agentensystem/regelwerk/agenten_uebergabeformate.yml`

Dokumentationsfähige Erkenntnis:

Das System kann später arbeitsteilig weiterentwickelt werden, weil Rollenoutputs bereits standardisiert beschrieben sind. Diese Formate sind aber noch keine API, Queue oder Laufzeit-Orchestrierung.

### 12. Anwenderhandlungen Sind Als Eigene Systemstelle Erkannt

Es gibt eine eigene Definition dafür, wann der Anwender handeln muss:

- Eingang bereitstellen
- Workflow-Richtung bestätigen
- Strukturwirkung freigeben
- externe Umsetzung bestätigen
- Evidenz nachreichen
- bewusste Nichtverfolgung bestätigen

Belege im Repo:

- `agentensystem/regelwerk/anwenderhandlungen.yml`
- `vorlagen/anwenderhandlung_vorlage.json`
- `docs/systemsimulation_und_anwenderhandlungen.md`
- `docs/anwenderanleitung_aktueller_systemstand.md`

Dokumentationsfähige Erkenntnis:

Das System soll nicht nur Agentenhandlungen dokumentieren, sondern auch menschliche Entscheidungen und Eingriffe. Daraus können später bessere Anwenderanleitungen und Kontrollpunkte entstehen.

### 13. TheBrain Ist Als Zielschicht Vorbereitet, Nicht Als Primärquelle

TheBrain hat eigene Aufgaben- und Umsetzungslogik, bleibt aber vom kanonischen Registry-Wissen getrennt.

Belege im Repo:

- `thebrain/README.md`
- `thebrain/aufgabenregister.yml`
- `thebrain/zuordnungsprüfungen.yml`
- `thebrain/umsetzungsprotokoll.yml`
- `prompts/registry_workflow/06_thebrain/`

Dokumentationsfähige Erkenntnis:

Eine TheBrain-Änderung kann vorbereitet, geprüft, freigegeben oder umgesetzt sein. Diese Zustände dürfen nicht vermischt werden.

### 14. Es Gibt Eine Changelog-Pflicht Für Sinnvolle Erweiterungen

Das Changelog dokumentiert die Einrichtungsschritte und Erweiterungen. Zusätzlich wurde festgelegt, dass sinnvolle Erweiterungen eine kurze commitfähige Beschreibung erhalten sollen.

Beleg im Repo:

- `changelog/änderungen.md`

Dokumentationsfähige Erkenntnis:

Die Entwicklung des Systems soll nicht nur technisch, sondern auch erklärend nachvollziehbar bleiben. Changelog und Commit-Beschreibung sollen sich gegenseitig stützen.

## Ableitbare Erkenntnisse Aus Der Bisherigen Einrichtung

### 1. Das System Befindet Sich Noch In Der Initialisierungsphase

Die Struktur ist breit angelegt, aber es gibt noch keine belastbaren echten Wissenseinträge aus Chat-Extraktionen.

Ableitung:

Die vorhandene Struktur kann noch ohne große Migrationsrisiken angepasst werden. Gerade deshalb sind Formatlogik, Schichtenmodell und Rollenlogik jetzt besonders wichtig.

### 2. Die Architektur Ist Stärker Als Eine Prompt-Sammlung

Das Repo enthält nicht nur Prompts, sondern auch:

- Register
- Statuswerte
- Vorlagen
- Workflows
- Agentenrollen
- Anwenderhandlungslogik
- Format- und Schichtenentscheidungen
- TheBrain-Vorbereitung

Ableitung:

Das System ist als Wissensinfrastruktur gedacht, nicht nur als Ablage für gute Prompts.

### 3. Die Wichtigste Schutzlogik Ist Trennung

Viele aktuelle Regeln dienen der Trennung:

- Chatwissen vs. Registry-Wissen
- Registry vs. TheBrain
- Erfolgspfad vs. Problemspur
- Prompt vs. Datenobjekt
- YAML-Steuerung vs. JSON-Daten
- Agentenvorschlag vs. menschliche Freigabe
- Vorbereitung vs. Umsetzung

Ableitung:

Die zentrale Qualität des Systems liegt weniger in einzelner Automatisierung, sondern in sauber getrennten Zuständen und Verantwortlichkeiten.

### 4. Menschliche Freigabe Ist Kein Nebenthema

Das Repo definiert mehrfach, dass Strukturwirkung, externe Zielsysteme und kanonische Änderungen menschliche Prüfung brauchen.

Ableitung:

Das System ist nicht darauf ausgelegt, dass Agenten eigenmächtig Wissen kanonisieren. Es ist auf überprüfbare Zusammenarbeit zwischen Mensch und Agent ausgelegt.

### 5. Das System Ist Für Spätere Automatisierung Vorbereitet

Die Bereiche `automation/`, `runtime/` und `docs/` sind bewusst angelegt, aber noch leer beziehungsweise erklärend.

Ableitung:

Automatisierung ist vorgesehen, aber absichtlich noch nicht implementiert. Der aktuelle Wert liegt in der Migrationsfähigkeit und in der späteren Anschlussfähigkeit.

## Noch Nicht Belegbare Annahmen

Die folgenden Punkte dürfen noch nicht als umgesetzt dokumentiert werden:

- Es gibt noch keine produktive Multi-Agent-Orchestrierung.
- Es laufen keine dauerhaften Agentenprozesse.
- Es gibt keine Kubernetes- oder Docker-Compose-Laufzeit.
- Es gibt keine automatische TheBrain-Synchronisierung.
- Es gibt noch keine vollständige RAG- oder lokale-LLM-Pipeline.
- Es gibt noch keine belastbare Menge echter extrahierter Wissenseinträge.
- Es gibt noch keine validierte Praxisroutine über viele reale Fälle hinweg.

## Dokumentationsfähige Kernaussage

Die bisherige Einrichtung hat ein versioniertes Grundsystem geschaffen, das Chatinhalte, Aufgaben, offene Probleme, Entscheidungen und Zielsystemänderungen kontrolliert in eine Wissensarchitektur überführen kann.

Der aktuelle Stand ist keine fertige Automatisierungsplattform, sondern eine bewusst strukturierte Grundlage. Sie definiert:

- wohin Wissen gehört,
- wie es geprüft wird,
- wann es kanonisch wird,
- wann der Anwender entscheiden muss,
- wie TheBrain vorbereitet wird,
- wie spätere Agenten und Automatisierung anschließen können.

## Empfohlene Weitere Dokumentation

Auf Basis dieses Einrichtungsstands sind folgende Dokumente sinnvoll:

1. Architekturüberblick für Mitentwickler
2. Anwenderanleitung für tägliche Nutzung
3. Einführende Beschreibung für fachfremde Personen
4. Betriebs- und Ausbaukonzept für spätere Automatisierung
5. TheBrain-Übergabekonzept
6. Erste Migrationsnotiz, sobald echte Registry-Daten angelegt werden

## Changelog-Bezug

Die bisherige Einrichtung ist im Changelog bis zum 2026-04-24 nachvollziehbar. Dieses Dokument fasst diese Entwicklung nicht chronologisch, sondern erkenntnisorientiert zusammen.
