# Prompt-Bibliothek

Der Bereich `prompts/` ist die kanonische, versionierte Arbeitsbibliothek für operative Prompts der Wissensarchitektur-Registry. Hier liegen die verbindlichen Promptfassungen, auf die sich Verarbeitung, Prüfung, Governance und TheBrain-Vorbereitung stützen.

## Zweck des Prompt-Bereichs

Die Prompt-Bibliothek schafft eine schnell auffindbare, logisch geordnete und einheitlich beschriebene Ablage für wiederverwendbare Arbeitsanweisungen. Sie sorgt dafür, dass operative Prompts nicht nur irgendwo referenziert, sondern als nachvollziehbare Repository-Inhalte versioniert gepflegt werden.

## Kanonische Quelle

Dieses Repository ist die Primärquelle für Promptversionen. Änderungen an Prompts sollen zuerst hier erfolgen und erst danach, wenn gewünscht, in andere Werkzeuge oder Wissensräume gespiegelt werden.

Obsidian kann später als Navigations-, Lese- oder Spiegelschicht dienen, ist aber nicht die führende Quelle für Promptstände.

## Arbeitsphasen 01 bis 06

### `01_eingang`

Prompts für die Aufnahme und Erststrukturierung neuer Inhalte, insbesondere die Chat-Extraktion, Artefakt-Metadaten und die Verdichtung abgeschlossener Aufgaben.

### `02_zuordnung`

Prompts für die fachliche Verortung extrahierter Inhalte in bestehende Domänen.

### `03_prüfung`

Prompts für Registerabgleich, semantische Klärung und andere prüfende Zwischenschritte vor einer strukturellen Festlegung.

### `04_entscheidung`

Prompts für Governance- und Strukturentscheidungen, wenn einfache Zuordnung oder Prüfung nicht ausreichen.

### `05_aktualisierung`

Prompts für konkrete Fortschreibung der Registry sowie für abgeleitete operative Arbeitslisten.

### `06_thebrain`

Prompts für die TheBrain-spezifische Aufgabenlogik, Prüfung und Update-Vorbereitung.

## Wie neue Prompts ergänzt werden sollen

Neue Prompts sollen immer:

- einer klaren Arbeitsphase zugeordnet werden,
- einen einheitlichen Kopfbereich mit Titel, Zweck, Verwendung, Ein- und Ausgabe enthalten,
- in `prompt_index.md` nachgetragen werden,
- möglichst an bestehende Register, Statuswerte und Workflows anschließen,
- keine fachlichen Doppelstrukturen erzeugen, wenn bereits ein Prompt mit gleichem Zweck vorhanden ist.

## Navigation

Für die schnelle Übersicht dient `prompts/prompt_index.md`. Die eigentlichen kanonischen Inhalte liegen in den Phasenordnern und sind dort die maßgebliche Arbeitsfassung.
