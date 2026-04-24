# Prompt-Abfolge

Diese Datei beschreibt die praktische Reihenfolge der operativen Prompts für die tägliche Arbeit mit neuen Chatinhalten.

Die kanonische Navigationsübersicht der Prompt-Bibliothek liegt in `prompts/prompt_index.md`. Die operative Arbeitsreihenfolge folgt den Phasenordnern unter `prompts/registry_workflow/`. Extern verwendbare Chat- und Repo-Anweisungen liegen getrennt unter `prompts/externe_anwendung/`.

## Standardreihenfolge

1. `prompts/registry_workflow/01_eingang/chat_extraktion.md`
2. `prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md`
3. `prompts/registry_workflow/03_pruefung/registry_abgleich.md`
4. `prompts/registry_workflow/03_pruefung/semantische_prüfung.md` nur bei Bedarf
5. `prompts/registry_workflow/04_entscheidung/governance_entscheidung.md` nur bei echter Strukturänderung
6. `prompts/registry_workflow/05_aktualisierung/registry_aktualisieren.md`
7. `prompts/registry_workflow/06_thebrain/thebrain_update_vorbereiten.md`

## Alternativer Eingangspfad für aufgabenbasierte Erkenntnisse

Wenn Wissen nicht aus einem Chat, sondern aus einer erfolgreich abgeschlossenen Aufgabe mit Screenshots, Bilddateien oder anderen Nachweisen entsteht, gilt vor dem regulären Workflow ein vorgeschalteter Eingangspfad:

1. `prompts/registry_workflow/01_eingang/artefakt_metadaten_erfassen.md`
2. `prompts/registry_workflow/01_eingang/aufgabenabschluss_verdichten.md`
3. danach `prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md` oder direkt `prompts/registry_workflow/03_pruefung/registry_abgleich.md`

## Typische Anwendungsfälle

### Neuer Chat

Ein neuer Chat wird zuerst extrahiert, dann einer Domäne zugeordnet und anschließend mit dem Register dieser Domäne abgeglichen. Nur bestätigte Ergebnisse werden in die Registry übernommen.

### Abgeschlossene Aufgabe mit Evidenz

Wenn ein Arbeitsverlauf erfolgreich abgeschlossen wurde und Screenshots oder Bilddateien als Nachweise vorliegen, werden diese zuerst als Artefakte erfasst. Danach wird der Aufgabenabschluss zu einem validierten Informationsblock verdichtet, bevor die reguläre Registry-Verarbeitung beginnt.

### Unklarer thematischer Bezug

Wenn der Schwerpunkt eines Chats nicht eindeutig ist, folgt auf die Extraktion eine besonders sorgfältige Domänen-Zuordnung. Falls keine bestehende Domäne belastbar passt, entsteht zunächst ein Domänenkandidat statt einer vorschnellen Einordnung.

### Semantische Überschneidung

Wenn ein neues Wissenselement einem bestehenden Knoten sehr ähnlich ist, wird nach dem Registry-Abgleich die semantische Prüfung eingeschoben. Ziel ist eine belastbare Entscheidung zwischen Zusammenführung, Abgrenzung oder Ergänzung.

### Neue Struktur notwendig

Wenn ein Chat auf einen neuen Standard, einen neuen Strukturknoten oder eine relevante Umstellung hinweist, folgt nach der semantischen Prüfung eine Governance-Entscheidung. Erst nach Freigabe wird die Registry angepasst.

### TheBrain-Änderung vorbereiten

Wenn die Registry bereits bestätigt aktualisiert wurde, wird daraus eine getrennte Liste für TheBrain vorbereitet. Diese Vorbereitung ist bewusst vom eigentlichen Umsetzungsstatus in TheBrain getrennt.
