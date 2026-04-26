# Prompt-Inventar Wissensarchitektur

Datum: 2026-04-27

## Zweck

Dieses Inventar erfasst vorhandene direkt verwendbare Prompts in der `wissensarchitektur-registry` und bereitet Metadatenvorschlaege fuer den zentralen Prompt-Katalog der `human-system-interface-registry` vor.

Die `wissensarchitektur-registry` bleibt Primaerquelle ihrer eigenen Promptdateien. Eine Uebergabe bedeutet hier nur Metadatenvorschlag, keine automatische Synchronisation, keine technische Verbindung und keine Uebernahme von Prompt-Volltext.

## Suchumfang

Geprueft wurden:

- `prompts/`
- Dateien mit `prompt` im Namen
- Registry-Workflow-Prompts
- Dateien mit explizitem `# Prompt:`-Kopf

Gefunden wurden 17 direkt verwendbare Promptdateien.

Unterstuetzende Dateien ohne eigenen Uebergabeblock:

- `prompts/README.md`
- `prompts/prompt_index.md`
- `prompts/handlungsregister.yml`
- `prompts/externe_anwendung/README.md`
- `prompts/registry_workflow/README.md`
- `workflows/prompt_abfolge.md`

## Gefundene Prompts

| Nr. | Prompt | Pfad | Zweck | Workflow-Phase | Uebergabe empfohlen |
| --- | --- | --- | --- | --- | --- |
| 1 | Chat-Wissensarbeit Initial- und Zusatzanweisung | `prompts/externe_anwendung/01_eingang/chat_wissensarbeit_initialanweisung.md` | Neue oder laufende Chats auf spaetere Wissensueberfuehrung ausrichten | 01 Eingang / externe Anwendung | ja |
| 2 | Chat-Uebergabeblock erzeugen | `prompts/externe_anwendung/01_eingang/chat_uebergabeblock_erzeugen.md` | Lange externe Chats in einen kompakten Uebergabeblock verdichten | 01 Eingang / externe Anwendung | ja |
| 3 | Repository um Agentensystem erweitern | `prompts/externe_anwendung/02_repo_erweiterung/repo_um_agentensystem_erweitern.md` | Repositories um eine repo-verankerte Agentenschicht erweitern | Externe Repo-Erweiterung | ja |
| 4 | Chat-Extraktion | `prompts/registry_workflow/01_eingang/chat_extraktion.md` | Chatinhalte oder Uebergabebloecke in strukturierte Wissensextrakte ueberfuehren | 01 Eingang | ja |
| 5 | Session-Problemspur erfassen | `prompts/registry_workflow/01_eingang/session_problemspur_erfassen.md` | Offene Probleme und Blockaden aus nicht abgeschlossenen Sessions erfassen | 01 Eingang | ja |
| 6 | Artefakt-Metadaten erfassen | `prompts/registry_workflow/01_eingang/artefakt_metadaten_erfassen.md` | Screenshots oder Bildnachweise als Artefaktdatensatz erfassen | 01 Eingang | ja |
| 7 | Aufgabenabschluss verdichten | `prompts/registry_workflow/01_eingang/aufgabenabschluss_verdichten.md` | Abgeschlossene Arbeitsverlaeufe in validierbare Informationsbloecke ueberfuehren | 01 Eingang | ja |
| 8 | Wissensnotiz transformieren | `prompts/registry_workflow/01_eingang/wissensnotiz_transformieren.md` | Freie Notizen, Erkenntnisse oder Dateien in Informationsbloecke ueberfuehren | 01 Eingang | ja |
| 9 | Domaenen-Zuordnung | `prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md` | Extrahierte Wissenselemente einer fuehrenden Domaene zuordnen | 02 Zuordnung | ja |
| 10 | Registry-Abgleich | `prompts/registry_workflow/03_pruefung/registry_abgleich.md` | Neue Wissenselemente gegen bestehende Register pruefen | 03 Pruefung | ja |
| 11 | Semantische Pruefung | `prompts/registry_workflow/03_pruefung/semantische_prüfung.md` | Bedeutungsnaehe, Abgrenzung und Konflikte klaeren | 03 Pruefung | ja |
| 12 | Governance-Entscheidung | `prompts/registry_workflow/04_entscheidung/governance_entscheidung.md` | Strukturrelevante Entscheidungen vorbereiten | 04 Entscheidung | ja |
| 13 | Registry aktualisieren | `prompts/registry_workflow/05_aktualisierung/registry_aktualisieren.md` | Bestaetigte Ergebnisse in konkrete Registry-Aenderungen ueberfuehren | 05 Aktualisierung | ja |
| 14 | Aufgabenliste aktualisieren | `prompts/registry_workflow/05_aktualisierung/aufgabenliste_aktualisieren.md` | Aus Aufgabenregister und Protokollen eine Arbeitsliste ableiten | 05 Aktualisierung | ja |
| 15 | THEBRAIN_TASK erfassen | `prompts/registry_workflow/06_thebrain/thebrain_task_erfassen.md` | Neue TheBrain-Aufgaben oder abgeschlossene Faelle erfassen | 06 TheBrain | ja |
| 16 | THEBRAIN_TASK pruefen | `prompts/registry_workflow/06_thebrain/thebrain_task_prüfen.md` | Neue TheBrain-Aufgaben gegen bestehende Eintraege pruefen | 06 TheBrain | ja |
| 17 | TheBrain-Update vorbereiten | `prompts/registry_workflow/06_thebrain/thebrain_update_vorbereiten.md` | Bestaetigte Registry-Aenderungen in TheBrain-Updates uebersetzen | 06 TheBrain | ja |

## Prompt-Uebergabevorschlaege

### 1. Chat-Wissensarbeit Initial- und Zusatzanweisung

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "chat_wissensarbeit_initialanweisung"
  titel: "Chat-Wissensarbeit Initial- und Zusatzanweisung"
  quelle_pfad: "prompts/externe_anwendung/01_eingang/chat_wissensarbeit_initialanweisung.md"
  zweck: "Einen neuen oder laufenden Chat so ausrichten, dass relevante Inhalte spaeter per Chat-Extraktion in die Wissensarchitektur ueberfuehrt werden koennen."
  wann_verwenden: "Zu Beginn eines Chats mit Wissensarbeitsbezug oder als Zusatzanweisung in fortgeschrittenen Chatverlaeufen."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 2. Chat-Uebergabeblock erzeugen

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "chat_uebergabeblock_erzeugen"
  titel: "Chat-Uebergabeblock erzeugen"
  quelle_pfad: "prompts/externe_anwendung/01_eingang/chat_uebergabeblock_erzeugen.md"
  zweck: "Einen langen oder fortgeschrittenen Arbeitschat in einen kompakten Block fuer spaetere Registry-Verarbeitung verdichten."
  wann_verwenden: "Wenn der vollstaendige Chatverlauf zu umfangreich fuer direktes Kopieren in die Chat-Extraktion ist."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 3. Repository um Agentensystem erweitern

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "repo_um_agentensystem_erweitern"
  titel: "Repository um Agentensystem erweitern"
  quelle_pfad: "prompts/externe_anwendung/02_repo_erweiterung/repo_um_agentensystem_erweitern.md"
  zweck: "Ein bestehendes Repository um eine repo-verankerte Agentenschicht fuer Analyse, Arbeitsstandssicherung und methodische Steuerung ergaenzen."
  wann_verwenden: "Wenn ein neues oder bestehendes Repository ein leichtgewichtiges, persistentes Agentensystem fuer Codex erhalten soll."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 4. Chat-Extraktion

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "chat_extraktion"
  titel: "Chat-Extraktion"
  quelle_pfad: "prompts/registry_workflow/01_eingang/chat_extraktion.md"
  zweck: "Neue Chatinhalte oder externe Uebergabebloecke in einen strukturierten Wissensextrakt ueberfuehren."
  wann_verwenden: "Wenn ein Chat, Gespraechsausschnitt oder externer Uebergabeblock erstmals in die Wissensarchitektur aufgenommen werden soll."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 5. Session-Problemspur erfassen

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "session_problemspur_erfassen"
  titel: "Session-Problemspur erfassen"
  quelle_pfad: "prompts/registry_workflow/01_eingang/session_problemspur_erfassen.md"
  zweck: "Nach einer nicht abgeschlossenen oder problembehafteten Session offene Probleme, Blockaden und Pruefbedarfe strukturiert erfassen."
  wann_verwenden: "Wenn eine Aufgabe in einem Chat, Agentenlauf oder Repo-Kontext nicht abgeschlossen wurde."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 6. Artefakt-Metadaten erfassen

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "artefakt_metadaten_erfassen"
  titel: "Artefakt-Metadaten erfassen"
  quelle_pfad: "prompts/registry_workflow/01_eingang/artefakt_metadaten_erfassen.md"
  zweck: "Einen Screenshot oder eine Bilddatei in einen referenzierbaren Artefaktdatensatz ueberfuehren."
  wann_verwenden: "Wenn ein Screenshot, Bildnachweis oder aehnliches Artefakt erstmals benannt und eingeordnet werden soll."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 7. Aufgabenabschluss verdichten

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "aufgabenabschluss_verdichten"
  titel: "Aufgabenabschluss verdichten"
  quelle_pfad: "prompts/registry_workflow/01_eingang/aufgabenabschluss_verdichten.md"
  zweck: "Einen abgeschlossenen Arbeitsverlauf mit Evidenz zu einem validierbaren Informationsblock zusammenfuehren."
  wann_verwenden: "Wenn eine Aufgabe fachlich abgeschlossen ist und in Repo-Wissen ueberfuehrt werden soll."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 8. Wissensnotiz transformieren

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "wissensnotiz_transformieren"
  titel: "Wissensnotiz transformieren"
  quelle_pfad: "prompts/registry_workflow/01_eingang/wissensnotiz_transformieren.md"
  zweck: "Notizen, Erkenntnisse, Lernergebnisse, Reflexionen, Zitate oder Dateien in einen integrationsfaehigen Informationsblock ueberfuehren."
  wann_verwenden: "Wenn Wissen nicht primaer aus einem Chat oder abgeschlossenen Aufgabenverlauf stammt."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 9. Domaenen-Zuordnung

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "domaenen_zuordnung"
  titel: "Domaenen-Zuordnung"
  quelle_pfad: "prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md"
  zweck: "Extrahierte Wissenselemente einer fachlich fuehrenden Domaene zuordnen."
  wann_verwenden: "Direkt nach der Chat-Extraktion und vor dem domaenenspezifischen Registerabgleich."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 10. Registry-Abgleich

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "registry_abgleich"
  titel: "Registry-Abgleich"
  quelle_pfad: "prompts/registry_workflow/03_pruefung/registry_abgleich.md"
  zweck: "Neue Wissenselemente gegen bestehende Domaenenregister pruefen und Dubletten vermeiden."
  wann_verwenden: "Nach der Domaenen-Zuordnung, sobald eine Ziel-Domaene feststeht."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 11. Semantische Pruefung

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "semantische_pruefung"
  titel: "Semantische Pruefung"
  quelle_pfad: "prompts/registry_workflow/03_pruefung/semantische_prüfung.md"
  zweck: "Bedeutungsnaehe, Abgrenzung und moegliche Konflikte zwischen Wissenselementen klaeren."
  wann_verwenden: "Wenn der Registry-Abgleich keine eindeutige Einordnung erlaubt oder Dublettengefahr besteht."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 12. Governance-Entscheidung

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "governance_entscheidung"
  titel: "Governance-Entscheidung"
  quelle_pfad: "prompts/registry_workflow/04_entscheidung/governance_entscheidung.md"
  zweck: "Strukturrelevante Aenderungen, Standards und Konfliktlagen verbindlich entscheiden."
  wann_verwenden: "Wenn Pruefung und Abgleich nicht ausreichen und eine belastbare Strukturentscheidung noetig ist."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 13. Registry aktualisieren

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "registry_aktualisieren"
  titel: "Registry aktualisieren"
  quelle_pfad: "prompts/registry_workflow/05_aktualisierung/registry_aktualisieren.md"
  zweck: "Bestaetigte Ergebnisse in konkrete Aenderungen der Registry-Dateien uebersetzen."
  wann_verwenden: "Nach abgeschlossenem Abgleich, optionaler semantischer Pruefung und gegebenenfalls Governance-Entscheidung."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 14. Aufgabenliste aktualisieren

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "aufgabenliste_aktualisieren"
  titel: "Aufgabenliste aktualisieren"
  quelle_pfad: "prompts/registry_workflow/05_aktualisierung/aufgabenliste_aktualisieren.md"
  zweck: "Aus Aufgabenregister und Protokollen eine uebersichtliche Arbeitsliste fuer TheBrain-Aufgaben ableiten."
  wann_verwenden: "Wenn eine aktuelle Sicht auf offene, umsetzungsreife oder dublettenverdaechtige Aufgaben benoetigt wird."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 15. THEBRAIN_TASK erfassen

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "thebrain_task_erfassen"
  titel: "THEBRAIN_TASK erfassen"
  quelle_pfad: "prompts/registry_workflow/06_thebrain/thebrain_task_erfassen.md"
  zweck: "Neue TheBrain-Aufgaben oder abgeschlossene Faelle in das Aufgabenregister ueberfuehren."
  wann_verwenden: "Wenn ein THEBRAIN_TASK-Block oder eine sonstige TheBrain-relevante Aufgabe erstmals strukturiert erfasst werden soll."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 16. THEBRAIN_TASK pruefen

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "thebrain_task_pruefen"
  titel: "THEBRAIN_TASK pruefen"
  quelle_pfad: "prompts/registry_workflow/06_thebrain/thebrain_task_prüfen.md"
  zweck: "Neue TheBrain-Aufgaben gegen bestehende Eintraege pruefen und dedupliziert zuordnen."
  wann_verwenden: "Nach der Erfassung eines neuen TheBrain-Tasks und vor einer endgueltigen Registerfortschreibung."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

### 17. TheBrain-Update vorbereiten

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "thebrain_update_vorbereiten"
  titel: "TheBrain-Update vorbereiten"
  quelle_pfad: "prompts/registry_workflow/06_thebrain/thebrain_update_vorbereiten.md"
  zweck: "Bestaetigte Registry-Aenderungen in konkrete, getrennt nachverfolgbare TheBrain-Updates ueberfuehren."
  wann_verwenden: "Nach der Registry-Aktualisierung, wenn aus bestaetigten Ergebnissen operative TheBrain-Aenderungen folgen."
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

## Empfehlung

Eine manuelle Uebergabe an die `human-system-interface-registry` wird empfohlen, weil dort der zentrale Meta-Katalog bekannter Prompts im Repo-Verbund gefuehrt werden soll.

Diese Empfehlung betrifft nur Metadaten. Es wurde keine automatische Weitergabe ausgefuehrt und nicht behauptet, dass die `human-system-interface-registry` aktualisiert wurde.

## Grenzen

Nicht erfolgt sind:

- keine Aenderung an anderen Repositories,
- keine automatische Synchronisation,
- keine technische Verbindung,
- keine Docker-Dateien,
- keine TheBrain-Aenderung,
- keine Registry-Aktualisierung ausserhalb dieses Inventarberichts,
- keine Uebertragung von Prompt-Volltexten.
