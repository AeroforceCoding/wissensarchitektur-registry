# Prompt: Repository um Agentensystem erweitern

- Titel: Repository um Agentensystem erweitern
- Zweck: Ein bestehendes Repository um eine repo-verankerte Agentenschicht für Analyse, Arbeitsstandssicherung und methodische Steuerung ergänzen.
- Wann verwenden: Wenn ein neues oder bestehendes Repository ein leichtgewichtiges, persistentes Agentensystem für Codex erhalten soll, ohne die fachliche Primärarchitektur zu ersetzen.
- Erwartete Eingabe: Bestehende Repository-Struktur, fachlicher Kontext des Repositories, gewünschter Umfang der Agentenschicht und vorhandene Konventionen.
- Erwartete Ausgabe: Angelegte oder ergänzte Agentenstruktur mit `AGENTS.md`, Skills, `agentensystem/` und einem strukturierten Änderungsbericht.
- Nächster Schritt: Agentensystem prüfen, ersten realen Agentenlauf vorbereiten oder repo-spezifische Skills weiter ausbauen.

## Zweck

Dieser Prompt dient dazu, ein bestehendes Repository um ein methodisch sauberes Agentensystem zu erweitern. Das Agentensystem soll Codex repo-verankert arbeitsfähig machen, ohne eine zweite Primärarchitektur neben dem eigentlichen Repository-Inhalt aufzubauen.

## Eingabe

Erwartet werden:

- die bestehende Repository-Struktur,
- der fachliche Zweck des Ziel-Repositories,
- vorhandene Konventionen zu Sprache, Dateibenennung und Statuslogik,
- Hinweise darauf, welche Teile bereits existieren,
- optional bestehende Prompt-, Workflow- oder Registerstrukturen.

## Prüffragen

- Gibt es bereits eine repo-interne Agenten- oder Arbeitsstruktur?
- Welche Teile des Agentensystems fehlen noch vollständig?
- Welche Benennungen sollten an die Sprache und Logik des Ziel-Repositories angepasst werden?
- Wo dürfen technische Codex-Andockpunkte nicht umbenannt werden?
- Welche persistente Struktur ist sinnvoll, ohne das Repository mit Gedächtnisdateien zu überfrachten?
- Welche ersten Skills bringen den höchsten methodischen Nutzen?
- Welche Regeln zur Trennung von Arbeitsannahmen, bestätigten Erkenntnissen und aktuellem Arbeitsfluss sind nötig?

## Gewünschtes Ausgabeformat

Die Antwort soll nicht als YAML erfolgen, sondern als tatsächlich umgesetzte Repository-Erweiterung. Am Ende ist ein strukturierter Änderungsbericht mit diesen Punkten auszugeben:

1. Angelegte Dateien
2. Ergänzte Dateien
3. Kurzbegründung pro Datei
4. Noch offene Punkte
5. Annahmen, die vom Anwender bestätigt werden sollten

## Direkt verwendbarer Prompt

Du arbeitest im aktuellen Repository.

## Ziel

Erweitere das bestehende Repository um ein erstes, repo-verankertes Agentensystem für Codex.

Dieses Agentensystem soll:

- Codex als projektverankerten Analyse- und Architekturagenten verankern
- persistente Arbeitsstände im Repository ermöglichen
- erste spezialisierte Skills bereitstellen
- die fachliche Primärarchitektur methodisch unterstützen, nicht ersetzen
- vollständig deutsch lesbar bleiben, soweit dies nicht mit festen technischen Konventionen kollidiert

## Wichtige Konvention

Behalte technische Codex-Einstiegspunkte in ihrer erwartbaren Form bei:

- `AGENTS.md`
- `.agents/skills/`
- `SKILL.md`
- `.codex/config.toml`

Alle übrigen fachlichen Struktur- und Dateinamen sollen auf Deutsch benannt sein, soweit dies fachlich sinnvoll und technisch unkritisch ist.

## Arbeitsmodus

- Prüfe zuerst die bestehende Repository-Struktur.
- Ergänze nur das, was für eine erste tragfähige Agentenschicht nötig ist.
- Wenn Dateien bereits existieren, ergänze möglichst statt zu überschreiben.
- Erfinde keine weiteren Repositories.
- Unterstelle keine fertige Automatisierung, wo nur Konzeptstatus vorliegt.
- Erfinde keinen Fachinhalt, der durch den vorhandenen Kontext nicht gestützt ist.
- Wo Inhalte noch nicht vollständig definiert sind, markiere sie als vorläufig, heuristisch oder ausbaufähig.

## Fachliche Grundlogik des Agentensystems

Das Agentensystem ist eine Hilfs- und Steuerungsschicht innerhalb des Repositories. Es ersetzt nicht die fachliche Primärarchitektur, sondern ergänzt sie um methodische Arbeitsmittel.

Es soll diese Grundprinzipien einhalten:

- Das Repository bleibt die kanonische Primärquelle.
- Persistentes Agentengedächtnis ist keine kanonische Wahrheit.
- Der Agent arbeitet standardmäßig zuerst im Modus Analyse.
- Unsicherheit wird ausdrücklich markiert.
- Es wird nichts als vorhanden behauptet, was nicht im Repository oder im übergebenen Kontext gestützt ist.
- Vor tieferen Strukturänderungen ist Bestätigung des Anwenders einzuholen.

## Methodische Trennung

Das Agentensystem soll mindestens diese Bereiche trennen:

- Gedächtnis
- Regelwerk
- Vorlagen

## Anzulegende oder zu ergänzende Struktur

Lege, soweit noch nicht vorhanden, diese Struktur an oder ergänze sie sinnvoll:

```text
AGENTS.md
.agents/
└─ skills/
   ├─ reifegrad-analyse/
   │  └─ SKILL.md
   ├─ prompt-explizitheitspruefung/
   │  └─ SKILL.md
   ├─ dublettenpruefung/
   │  └─ SKILL.md
   └─ statusanalyse/
      └─ SKILL.md

agentensystem/
├─ README.md
├─ gedaechtnis/
│  ├─ arbeitsgedaechtnis.md
│  ├─ bestaetigte_erkenntnisse.md
│  ├─ entscheidungen.md
│  └─ letzter_stand.md
├─ regelwerk/
│  ├─ reifegrade.md
│  ├─ statuswerte.md
│  └─ aenderungsarten.md
└─ vorlagen/
   └─ analysebericht_vorlage.md
```

## Inhaltsvorgaben

### 1. `AGENTS.md`

Lege eine repo-verankerte Agentenrolle an.

Die Datei soll mindestens festlegen:

- Rolle des Agenten als projektverankerter Analyse- und Architekturagent
- Repository als Primärquelle
- Analyse zuerst statt vorschneller Umbauten
- saubere Trennung zwischen gesichertem Befund, Reifegradbewertung, Interpretation, Hypothese, Verbesserungsvorschlag, offenem Punkt und Rückfrage
- Hinweis, dass persistentes Gedächtnis nicht mit kanonischer Wahrheit verwechselt werden darf
- Analyseausgabe mit klarer Abschnittsstruktur

### 2. Skills unter `.agents/skills/`

Lege diese ersten Skills an:

- `reifegrad-analyse`
- `prompt-explizitheitspruefung`
- `dublettenpruefung`
- `statusanalyse`

Jeder Skill soll ein kurzes `SKILL.md` mit enthalten:

- Name
- Kurzbeschreibung
- Zweck
- Wann verwenden
- Prüffragen
- Output
- Grenzen

### 3. `agentensystem/README.md`

Erkläre:

- warum es diesen Bereich gibt
- dass er die Primärarchitektur nicht ersetzt
- dass er Regeln, Skills, Gedächtnis und Vorlagen methodisch trennt
- dass bestätigte Erkenntnisse nicht mit Arbeitsannahmen vermischt werden dürfen

### 4. Gedächtnisstruktur

Lege diese Dateien an:

- `arbeitsgedaechtnis.md`
  Zweck:
  laufende Arbeitsannahmen, offene Schleifen und heuristische Beobachtungen

- `bestaetigte_erkenntnisse.md`
  Zweck:
  bestätigte, wiederverwendbare Erkenntnisse, die nach bewusster Prüfung übernommen wurden

- `entscheidungen.md`
  Zweck:
  bestätigte agentenspezifische Entscheidungen

- `letzter_stand.md`
  Zweck:
  aktueller kompakter Arbeitsfluss des Agenten

`letzter_stand.md` soll ausdrücklich nicht als Verlaufslog, sondern als kleines Kanban-Board aufgebaut sein mit diesen Bereichen:

- `Backlog`
- `Naechste_Schritte`
- `In_Arbeit`
- `Abgeschlossen`

### 5. Regelwerk

Lege diese Dateien an:

- `reifegrade.md`
- `statuswerte.md`
- `aenderungsarten.md`

#### Reifegrade

Verwende diese Reifestufen:

- `erwähnt`
- `strukturell_vorgesehen`
- `teilweise_definiert`
- `inhaltlich_definiert`
- `operativ_nutzbar`
- `überprüft`
- `kanonisch_freigegeben`

Wenn die Stufe nicht sicher bestimmbar ist:

- wahrscheinlichste Stufe nennen
- Unsicherheit markieren
- kurz begründen

#### Statuswerte

Halte methodisch fest, dass Statuswerte nach Schicht und Funktion getrennt betrachtet werden müssen.

Berücksichtige mindestens:

- fachliche Statuswerte des Repositories
- Reifegradstatus
- Arbeitsflussstatus im Agentensystem

Integriere ausdrücklich diese Regel:

- `Abgeschlossen` ist Quelle möglicher Übernahme.
- `Abgeschlossen` bedeutet nicht automatisch bestätigte Erkenntnis.
- Eine Übernahme in `bestaetigte_erkenntnisse.md` erfolgt nur nach bewusster Prüfung und bei wiederverwendbarem Erkenntniswert.

#### Änderungsarten

Trenne methodisch verschiedene Arten von Änderungen, damit lokale Arbeitsschritte nicht mit kanonischer Strukturwirkung verwechselt werden.

Lege dafür eine kleine, ausbaufähige Startmenge an, zum Beispiel:

- `repo_änderung`
- `registry_änderung`
- `review_änderung`
- `artefakt_änderung`
- `zielsystem_vorbereitung`
- `zielsystem_umsetzung`

### 6. Vorlage

Lege `analysebericht_vorlage.md` an.

Die Vorlage soll diese Struktur abbilden:

```text
# Analysebericht

## 1. Gesicherter Befund
## 2. Reifegradbewertung
## 3. Interpretation
## 4. Erkannte Architekturspannungen
## 5. Hypothesen
## 6. Sinnvolle nächste Fähigkeiten des Agenten
## 7. Mögliche Verbesserungsrichtungen
## 8. Noch nicht belegbare Annahmen
## 9. Rückfrage an den Anwender
```

## Autonomie und Bestätigung

Das Agentensystem soll inhaltlich darauf ausgerichtet sein, dass der Agent:

- möglichst viel analytisch und vorbereitend autonom leisten darf
- seine Annahmen transparent machen muss
- bei strukturwirksamen oder destruktiven Änderungen vor Ausführung Bestätigung einholt
- offene Unsicherheit sichtbar belässt statt sie zu glätten

## Sprachregel

- Standardsprache ist Deutsch.
- Unnötig künstliche Übersetzungen sind zu vermeiden.
- Deutsche Begriffe sollen dort bevorzugt werden, wo sie die Funktion klarer machen.
- Technische Standardbegriffe und technische Andockpunkte bleiben erhalten, wenn sie notwendig und etabliert sind.

## Grenzen

- keine weiteren Repositories erfinden
- keine fertige Automatisierung unterstellen
- keine Zielsysteme oder Spiegelsysteme zur Primärquelle erklären
- persistentes Arbeitsgedächtnis nicht mit kanonischer Wahrheit verwechseln
- nur eine erste tragfähige Startstruktur anlegen, keine Vollarchitektur erzwingen

## Ausgabe am Ende

Gib einen strukturierten Änderungsbericht aus mit:

1. Angelegte Dateien
2. Ergänzte Dateien
3. Kurzbegründung pro Datei
4. Noch offene Punkte
5. Annahmen, die vom Anwender bestätigt werden sollten

Führe die Erweiterung jetzt vollständig aus.
```
