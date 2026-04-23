# Prompt-Abfolge

Diese Datei beschreibt die praktische Reihenfolge der operativen Prompts für die tägliche Arbeit mit neuen Chatinhalten.

## Standardreihenfolge

1. `chat_extraktion.md`
2. `domänen_zuordnung.md`
3. `registry_abgleich.md`
4. `semantische_prüfung.md` nur bei Bedarf
5. `governance_entscheidung.md` nur bei echter Strukturänderung
6. `registry_aktualisieren.md`
7. `thebrain_update_vorbereiten.md`

## Typische Anwendungsfälle

### Neuer Chat

Ein neuer Chat wird zuerst extrahiert, dann einer Domäne zugeordnet und anschließend mit dem Register dieser Domäne abgeglichen. Nur bestätigte Ergebnisse werden in die Registry übernommen.

### Unklarer thematischer Bezug

Wenn der Schwerpunkt eines Chats nicht eindeutig ist, folgt auf die Extraktion eine besonders sorgfältige Domänen-Zuordnung. Falls keine bestehende Domäne belastbar passt, entsteht zunächst ein Domänenkandidat statt einer vorschnellen Einordnung.

### Semantische Überschneidung

Wenn ein neues Wissenselement einem bestehenden Knoten sehr ähnlich ist, wird nach dem Registry-Abgleich die semantische Prüfung eingeschoben. Ziel ist eine belastbare Entscheidung zwischen Zusammenführung, Abgrenzung oder Ergänzung.

### Neue Struktur notwendig

Wenn ein Chat auf einen neuen Standard, einen neuen Strukturknoten oder eine relevante Umstellung hinweist, folgt nach der semantischen Prüfung eine Governance-Entscheidung. Erst nach Freigabe wird die Registry angepasst.

### TheBrain-Änderung vorbereiten

Wenn die Registry bereits bestätigt aktualisiert wurde, wird daraus eine getrennte Liste für TheBrain vorbereitet. Diese Vorbereitung ist bewusst vom eigentlichen Umsetzungsstatus in TheBrain getrennt.
