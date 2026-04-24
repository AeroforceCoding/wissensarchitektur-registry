# Prompt-Bibliothek

Der Bereich `prompts/` ist die kanonische, versionierte Arbeitsbibliothek für operative und strukturierende Prompts der Wissensarchitektur-Registry. Hier liegen die verbindlichen Promptfassungen, auf die sich Verarbeitung, Prüfung, Governance, TheBrain-Vorbereitung und gezielte Anwendung außerhalb dieses Repositories stützen.

## Zweck des Prompt-Bereichs

Die Prompt-Bibliothek schafft eine schnell auffindbare, logisch geordnete und einheitlich beschriebene Ablage für wiederverwendbare Arbeitsanweisungen. Sie sorgt dafür, dass operative Prompts nicht nur irgendwo referenziert, sondern als nachvollziehbare Repository-Inhalte versioniert gepflegt werden.

## Kanonische Quelle

Dieses Repository ist die Primärquelle für Promptversionen. Änderungen an Prompts sollen zuerst hier erfolgen und erst danach, wenn gewünscht, in andere Werkzeuge oder Wissensräume gespiegelt werden.

Obsidian kann später als Navigations-, Lese- oder Spiegelschicht dienen, ist aber nicht die führende Quelle für Promptstände.

## Grundstruktur

Die Prompt-Bibliothek ist zuerst nach Verwendungsort getrennt:

- `registry_workflow/`: Prompts, die innerhalb dieser Registry den kanonischen Verarbeitungsprozess steuern.
- `externe_anwendung/`: Prompts, die in anderen Chats, anderen Repositories oder angrenzenden Arbeitskontexten verwendet werden können.

Diese Trennung soll das Auffinden im Alltag erleichtern. Wer den internen Registry-Prozess fortführt, beginnt in `registry_workflow/`. Wer eine Anweisung zum Kopieren in einen anderen Chat oder ein anderes Repository sucht, beginnt in `externe_anwendung/`.

## Registry-Workflow-Phasen 01 bis 06

Innerhalb von `registry_workflow/` bleibt die fachliche Prozesslogik nach Phasen erhalten.

### `registry_workflow/01_eingang`

Prompts für die Aufnahme und Erststrukturierung neuer Inhalte, insbesondere die Chat-Extraktion, Artefakt-Metadaten und die Verdichtung abgeschlossener Aufgaben.

### `registry_workflow/02_zuordnung`

Prompts für die fachliche Verortung extrahierter Inhalte in bestehende Domänen.

### `registry_workflow/03_pruefung`

Prompts für Registerabgleich, semantische Klärung und andere prüfende Zwischenschritte vor einer strukturellen Festlegung.

### `registry_workflow/04_entscheidung`

Prompts für Governance- und Strukturentscheidungen, wenn einfache Zuordnung oder Prüfung nicht ausreichen.

### `registry_workflow/05_aktualisierung`

Prompts für konkrete Fortschreibung der Registry und abgeleitete operative Arbeitslisten.

### `registry_workflow/06_thebrain`

Prompts für die TheBrain-spezifische Aufgabenlogik, Prüfung und Update-Vorbereitung.

## Externe Anwendung

### `externe_anwendung/01_eingang`

Prompts und Anweisungen für die externe Vorbereitung der Eingangsschicht. Sie werden in neuen, laufenden oder langen Arbeitschats verwendet, damit diese Chats später besser in die Wissensarchitektur überführbar sind oder einen kompakten Übergabeblock für die interne Chat-Extraktion erzeugen.

### `externe_anwendung/repo_erweiterungen`

Prompts, die dazu dienen, andere Repositories oder angrenzende Arbeitsräume nach einem definierten Muster zu erweitern.

## Wie neue Prompts ergänzt werden sollen

Neue Prompts sollen immer:

- einer klaren Arbeitsphase zugeordnet werden,
- einem klaren Verwendungsort zugeordnet werden,
- einen einheitlichen Kopfbereich mit Titel, Zweck, Verwendung, Ein- und Ausgabe enthalten,
- in `prompt_index.md` nachgetragen werden,
- möglichst an bestehende Register, Statuswerte und Workflows anschließen,
- keine fachlichen Doppelstrukturen erzeugen, wenn bereits ein Prompt mit gleichem Zweck vorhanden ist.

## Navigation

Für die schnelle Übersicht dient `prompts/prompt_index.md`. Die eigentlichen kanonischen Inhalte liegen in den jeweiligen Verwendungsordnern und sind dort die maßgebliche Arbeitsfassung.
