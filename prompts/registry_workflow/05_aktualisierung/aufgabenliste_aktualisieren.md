# Prompt: Aufgabenliste aktualisieren

- Titel: Aufgabenliste aktualisieren
- Zweck: Aus Aufgabenregister und Protokollen eine übersichtliche Arbeitsliste für TheBrain-Aufgaben ableiten.
- Handlung: Registry aktualisieren (`registry_aktualisieren`)
- Wann verwenden: Wenn eine aktuelle Sicht auf offene, umsetzungsreife oder dublettenverdächtige Aufgaben benötigt wird.
- Erwartete Eingabe: `thebrain/aufgabenregister.yml`, `thebrain/umsetzungsprotokoll.yml` und optional `thebrain/zuordnungsprüfungen.yml`.
- Erwartete Ausgabe: Ein JSON-`aufgabenliste` mit offenen Aufgaben, Umsetzungsfällen und Prüfhilfen.
- Nächster Schritt: Operative Bearbeitung, Priorisierung oder manuelle TheBrain-Umsetzung

## Zweck

Dieser Prompt leitet aus dem TheBrain-Aufgabenregister und dem Umsetzungsprotokoll eine übersichtliche, priorisierbare Aufgabenliste ab. Er hilft dabei, offene Aufgaben, umsetzungsbereite Einträge, bereits umgesetzte Fälle, bestätigungsbedürftige Änderungen und potenzielle Dubletten sichtbar zu machen.

## Eingabe

Erwartet werden:

- `thebrain/aufgabenregister.yml`
- `thebrain/umsetzungsprotokoll.yml`
- optional `thebrain/zuordnungsprüfungen.yml`

## Prüffragen

- Welche Aufgaben sind noch offen oder in Prüfung?
- Welche Aufgaben haben den TheBrain-Status `zur_umsetzung`?
- Welche Aufgaben wurden bereits umgesetzt, aber noch nicht bestätigt?
- Welche Aufgaben sind bestätigt oder erledigt?
- Welche Aufgaben zeigen Dublettenrisiken oder offene Zuordnungsfragen?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges JSON im folgenden Format erfolgen:

```json
{
  "aufgabenliste": {
    "offene_aufgaben": [
      {
        "task_ref": "tb_task_1234",
        "titel": "Beispiel",
        "status": "neu"
      }
    ],
    "zur_umsetzung_in_thebrain": [
      {
        "task_ref": "tb_task_2345",
        "titel": "Beispiel",
        "umsetzungsstatus_thebrain": "zur_umsetzung"
      }
    ],
    "bereits_umgesetzt": [
      {
        "task_ref": "tb_task_3456",
        "titel": "Beispiel",
        "umsetzungsstatus_thebrain": "umgesetzt"
      }
    ],
    "bestätigungsbedürftig": [
      {
        "task_ref": "tb_task_4567",
        "titel": "Beispiel",
        "hinweis": "Umsetzung erfolgt, fachliche Bestätigung steht aus"
      }
    ],
    "potenzielle_dubletten": [
      {
        "task_ref": "tb_task_5678",
        "bezug": "tb_task_1111",
        "hinweis": "Teilweise Überschneidung prüfen"
      }
    ]
  }
}
```

## Direkt verwendbarer Prompt

Du erhältst Aufgabenregister, Umsetzungsprotokoll und optional Zuordnungsprüfungen der TheBrain-Schicht. Leite daraus eine übersichtliche Aufgabenliste ab, die den aktuellen Bearbeitungs- und Umsetzungsstand sichtbar macht.

Arbeite mit folgenden Regeln:

- Nutze das Aufgabenregister als führende Aufgabenquelle.
- Verwende das Umsetzungsprotokoll, um Statusübergänge und Bestätigungsbedarfe sauber einzuordnen.
- Führe potenzielle Dubletten nur dann auf, wenn Prüfungen oder Registerdaten dafür einen belastbaren Hinweis geben.
- Antworte ausschließlich im vorgegebenen JSON-Format.

Eingabe:

```json
{
  "aufgabenregister": {
  },
  "umsetzungsprotokoll": {
  },
  "zuordnungsprüfungen": {
  }
}
```
