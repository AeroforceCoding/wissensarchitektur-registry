# Prompt: THEBRAIN_TASK erfassen

## Zweck

Dieser Prompt überführt einen THEBRAIN_TASK-Block oder eine bereits abgeschlossene Aufgabe in einen strukturierten Eintrag für `thebrain/aufgabenregister.yml`. Ziel ist eine konsistente, nachvollziehbare Erfassung mit Ziel-Brain, Zielast, Status und Strukturwirkung.

## Eingabe

Erwartet wird:

- ein THEBRAIN_TASK-Block oder eine textlich beschriebene abgeschlossene Aufgabe,
- optional ergänzende Metadaten aus dem Repository,
- die gültigen Ziel-Brains aus `global/thebrain_ziele.yml`,
- die internen Aufgabenstatus aus `global/aufgaben_statuswerte.yml`,
- die Umsetzungsstatus aus `global/thebrain_statuswerte.yml`.

## Prüffragen

- Was ist der eigentliche Arbeitsgegenstand der Aufgabe?
- Handelt es sich um eine neue, laufende oder bereits abgeschlossene Aufgabe?
- In welchem Ziel-Brain und unter welchem Haupt- oder Unterast sollte die Aufgabe später verortet werden?
- Führt die Aufgabe zu einem Strukturupdate oder nur zu einer Ergänzung?
- Welche neuen Strukturknoten wären betroffen oder anzulegen?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges YAML im folgenden Format erfolgen:

```yaml
aufgabenregister_eintrag:
  task_id: tb_task_1234
  titel: Prägnanter Aufgabentitel
  typ: thebrain_task
  status: neu
  target_brain: wissensarchitektur_hauptbrain
  target_hauptast: Wissenssystem / TheBrain
  target_unterast: Beispiel-Unterast
  quelle_typ: Chat
  quelle_ref: intake/chat_extrakte/beispiel.yml
  zusammenfassung: Kurze fachliche Beschreibung der Aufgabe
  auswirkung: Erwartete Wirkung auf Struktur, Ordnung oder Nachvollziehbarkeit
  wiederholbar: false
  struktur_update: true
  neue_strukturknoten:
    - Beispielknoten
  duplikatprüfung_status: offen
  umsetzungsstatus_thebrain: vorgeschlagen
  erstellt_am: 2026-04-23
  zuletzt_geändert: 2026-04-23
  notizen: Kurze Zusatzhinweise
```

## Direkt verwendbarer Prompt

Du erhältst einen THEBRAIN_TASK-Block oder eine bereits abgeschlossene Aufgabe. Überführe den Inhalt in einen strukturierten Eintrag für das TheBrain-Aufgabenregister dieser Wissensarchitektur.

Arbeite mit folgenden Regeln:

- Formuliere einen klaren, kurzen Titel.
- Wähle `status` aus den internen Aufgabenstatuswerten.
- Wähle `umsetzungsstatus_thebrain` aus den TheBrain-Statuswerten.
- Nutze nur Ziel-Brains und Hauptäste, die zum Register passen oder eindeutig aus der Eingabe ableitbar sind.
- Setze `struktur_update` nur dann auf `true`, wenn sich daraus neue oder veränderte Strukturknoten ableiten.
- Antworte ausschließlich im vorgegebenen YAML-Format.

Eingabe:

```text
[Hier steht der THEBRAIN_TASK-Block oder die Aufgabenbeschreibung.]
```
