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

## Externer Eingangspfad für lange laufende Chats

Wenn ein Chat außerhalb dieses Repositories zu umfangreich ist, um ihn vollständig in die Chat-Extraktion zu kopieren, wird zuerst im externen Chat ein Übergabeblock erzeugt:

1. `prompts/externe_anwendung/01_eingang/chat_uebergabeblock_erzeugen.md`
2. danach `prompts/registry_workflow/01_eingang/chat_extraktion.md`

Der Übergabeblock ersetzt keine Registry-Entscheidung. Er ist nur eine kompakte Eingabe für die kanonische Chat-Extraktion.

## Alternativer Eingangspfad für aufgabenbasierte Erkenntnisse

Wenn Wissen nicht aus einem Chat, sondern aus einer erfolgreich abgeschlossenen Aufgabe mit Screenshots, Bilddateien oder anderen Nachweisen entsteht, gilt vor dem regulären Workflow ein vorgeschalteter Eingangspfad:

1. `prompts/registry_workflow/01_eingang/artefakt_metadaten_erfassen.md`
2. `prompts/registry_workflow/01_eingang/aufgabenabschluss_verdichten.md`
3. danach `prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md` oder direkt `prompts/registry_workflow/03_pruefung/registry_abgleich.md`

## Paralleler Problempfad für nicht abgeschlossene Sessions

Wenn eine Session, Aufgabe oder Untersuchung nicht abgeschlossen wurde, soll das offene Problem nicht automatisch in den Erfolgsworkflow gedrückt werden. Stattdessen kann parallel eine Problemspur erfasst werden:

1. `prompts/registry_workflow/01_eingang/session_problemspur_erfassen.md`
2. danach zweckdienlichkeitsabhängig:
   - vorhandenes Wissen im betroffenen Repo oder in der passenden Domäne abgleichen,
   - eine Untersuchung starten,
   - eine Aufgabe ableiten,
   - bewusst keine Aktion auslösen.

Dieser Pfad ist nicht blockierend. Er dient dazu, offene Probleme sichtbar und später prüfbar zu machen, ohne erfolgreiche Ergebnisse oder abgeschlossene Wissensblöcke zu überlagern.

## Eingangspfad für freie Wissensrohstoffe

Wenn Wissen nicht aus einem vollständigen Chat oder einer abgeschlossenen Aufgabe stammt, sondern aus Notizen, Einfällen, Erinnerungen, Lernergebnissen, Reflexionen, Zitaten, Word-Dateien, Bilddateien oder anderen Wissensartefakten, kann daraus ein Informationsblock vorbereitet werden:

1. `prompts/registry_workflow/01_eingang/wissensnotiz_transformieren.md`
2. danach abhängig vom Ergebnis:
   - `prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md`,
   - `prompts/registry_workflow/01_eingang/artefakt_metadaten_erfassen.md`,
   - oder eine spätere Repo-Zuordnungsprüfung, wenn das Material nicht in dieses Repository gehört.

Dieser Pfad erzeugt keinen kanonischen Registry-Eintrag. Er transformiert freie Wissensrohstoffe in einen prüfbaren Informationsblock.

## Typische Anwendungsfälle

### Neuer Chat

Ein neuer Chat wird zuerst extrahiert, dann einer Domäne zugeordnet und anschließend mit dem Register dieser Domäne abgeglichen. Nur bestätigte Ergebnisse werden in die Registry übernommen.

### Abgeschlossene Aufgabe mit Evidenz

Wenn ein Arbeitsverlauf erfolgreich abgeschlossen wurde und Screenshots oder Bilddateien als Nachweise vorliegen, werden diese zuerst als Artefakte erfasst. Danach wird der Aufgabenabschluss zu einem validierten Informationsblock verdichtet, bevor die reguläre Registry-Verarbeitung beginnt.

### Nicht abgeschlossene Session

Wenn eine Aufgabe nicht abgeschlossen wurde, wird kein Informationsblock für einen erfolgreichen Abschluss erzeugt. Stattdessen kann eine Problemspur erfasst werden, die Blockaden, Fehlversuche, Hypothesen und Zweckdienlichkeit einer späteren Lösung dokumentiert.

### Freie Wissensnotiz Oder Reflexion

Wenn ein Einfall, eine Erinnerung, ein Lernergebnis, eine Reflexion oder ein Zitat relevant erscheint, wird zuerst ein Informationsblock vorbereitet. Danach wird geprüft, welche Domäne oder welches Repository zuständig ist und ob die Information als gesichertes Wissen, Reflexionshinweis, Quelle oder offener Punkt weitergeführt werden soll.

### Unklarer thematischer Bezug

Wenn der Schwerpunkt eines Chats nicht eindeutig ist, folgt auf die Extraktion eine besonders sorgfältige Domänen-Zuordnung. Falls keine bestehende Domäne belastbar passt, entsteht zunächst ein Domänenkandidat statt einer vorschnellen Einordnung.

### Semantische Überschneidung

Wenn ein neues Wissenselement einem bestehenden Knoten sehr ähnlich ist, wird nach dem Registry-Abgleich die semantische Prüfung eingeschoben. Ziel ist eine belastbare Entscheidung zwischen Zusammenführung, Abgrenzung oder Ergänzung.

### Neue Struktur notwendig

Wenn ein Chat auf einen neuen Standard, einen neuen Strukturknoten oder eine relevante Umstellung hinweist, folgt nach der semantischen Prüfung eine Governance-Entscheidung. Erst nach Freigabe wird die Registry angepasst.

### TheBrain-Änderung vorbereiten

Wenn die Registry bereits bestätigt aktualisiert wurde, wird daraus eine getrennte Liste für TheBrain vorbereitet. Diese Vorbereitung ist bewusst vom eigentlichen Umsetzungsstatus in TheBrain getrennt.
