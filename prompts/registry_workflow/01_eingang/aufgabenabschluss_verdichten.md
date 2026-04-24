# Prompt: Aufgabenabschluss verdichten

- Titel: Aufgabenabschluss verdichten
- Zweck: Einen erfolgreich abgeschlossenen Arbeitsverlauf mit Evidenz zu einem validierten Informationsblock zusammenführen.
- Handlung: Eingang vorbereiten (`eingang_vorbereiten`)
- Wann verwenden: Wenn eine Aufgabe fachlich abgeschlossen ist und aus Verlauf, Ergebnis und Nachweisen ein integrationsfähiger Wissensblock entstehen soll.
- Erwartete Eingabe: Aufgabenbeschreibung, Abschlussstatus, Artefakt-Referenzen, bekannte Domänen- und Kontextbezüge.
- Erwartete Ausgabe: Ein JSON-`informationsblock` mit Befunden, Interpretationen, Hypothesen und empfohlener Folgeaktion.
- Nächster Schritt: `prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md` oder `prompts/registry_workflow/03_pruefung/registry_abgleich.md`

## Zweck

Dieser Prompt verdichtet einen erfolgreich abgeschlossenen Aufgabenverlauf zu einem validierbaren Informationsblock. Er trennt Nachweise, gesicherte Befunde, Interpretationen und Hypothesen, damit erst danach der reguläre Registry-Workflow startet.

## Eingabe

Erwartet werden:

- eine abgeschlossene Aufgabe oder Ergebniszusammenfassung,
- vorhandene Artefakt-Referenzen,
- bekannte Kontext- oder Aufgabenbezüge,
- optional vorhandene Domänenhinweise,
- die Vorlage eines Informationsblocks aus `vorlagen/informationsblock_vorlage.json`.

## Prüffragen

- Welche Aussagen gelten als gesichert?
- Welche Aussagen sind nur Interpretation oder Hypothese?
- Welche Artefakte stützen welche Befunde?
- Welche offenen Punkte bleiben trotz Aufgabenerfolg bestehen?
- Welcher Workflow-Schritt folgt logisch als Nächstes?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges JSON im folgenden Format erfolgen:

```json
{
  "informationsblock": {
    "informationsblock_id": "ib_2026_0001",
    "titel": "Prägnanter Titel des verdichteten Falls",
    "herkunft_typ": "abgeschlossene_aufgabe",
    "herkunft_ref": "tb_task_0042",
    "führende_domäne": "m365_sharepoint",
    "domänenhinweise": [

    ],
    "kontext_refs": [

    ],
    "kurzbeschreibung": "Kurzbeschreibung des validierten Falls",
    "gesicherte_befunde": [

    ],
    "interpretationen": [

    ],
    "hypothesen": [

    ],
    "offene_punkte": [

    ],
    "artefakt_refs": [

    ],
    "verwandte_repo_objekte": [

    ],
    "empfohlener_nächster_workflow_schritt": "registry_abgleich",
    "strukturrelevanz": "mittel",
    "validierungsstand": "geprüft",
    "erstellt_am": "2026-04-23",
    "zuletzt_geändert": "2026-04-23",
    "notizen": ""
  }
}
```

## Direkt verwendbarer Prompt

Du erhältst einen erfolgreich abgeschlossenen Aufgabenverlauf mit Nachweisen. Verdichte ihn zu einem validierbaren Informationsblock für die Wissensarchitektur-Registry.

Arbeite mit folgenden Regeln:

- Trenne strikt zwischen gesichertem Befund, Interpretation und Hypothese.
- Nutze Artefakte nur als Nachweise und nicht als Ersatz für fachliche Aussagen.
- Benenne offene Punkte auch dann, wenn die Aufgabe insgesamt erfolgreich abgeschlossen wurde.
- Leite den nächsten Workflow-Schritt nur aus dem tatsächlich vorliegenden Reifegrad ab.
- Antworte ausschließlich im vorgegebenen JSON-Format.

Eingabe:

```json
{
  "abgeschlossene_aufgabe": {
  },
  "artefakt_refs": [

  ],
  "kontext_hinweise": [

  ],
  "domänenhinweise": [

  ]
}
```
