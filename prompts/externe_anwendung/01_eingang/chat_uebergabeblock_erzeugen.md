# Prompt: Chat-Übergabeblock erzeugen

- Titel: Chat-Übergabeblock erzeugen
- Zweck: Einen langen oder fortgeschrittenen Arbeitschat in einen kompakten, übergabefähigen Block für die spätere Registry-Verarbeitung verdichten.
- Handlung: Eingang vorbereiten (`eingang_vorbereiten`)
- Wann verwenden: Wenn der vollständige Chatverlauf zu umfangreich ist, um ihn direkt in die Chat-Extraktion zu kopieren.
- Erwartete Eingabe: Laufender Chatkontext, Abschlussmarker oder Aufforderung des Anwenders, relevante Erkenntnisse für die Wissensarchitektur zu verdichten.
- Erwartete Ausgabe: Ein JSON-`wissensarchitektur_uebergabe` als kompakter Übergabeblock.
- Nächster Schritt: `prompts/registry_workflow/01_eingang/chat_extraktion.md`

## Zweck

Dieser Prompt ist für die Anwendung in einem externen oder laufenden Chat gedacht. Er ersetzt nicht die kanonische Chat-Extraktion im Repository, sondern bereitet ihr eine kompakte Eingabe vor, wenn der vollständige Chatverlauf nicht sinnvoll kopiert werden kann.

Der externe Chat soll seinen eigenen Verlauf auswerten und daraus einen übergabefähigen Block erzeugen. Dieser Block kann anschließend im Repository mit `prompts/registry_workflow/01_eingang/chat_extraktion.md` in einen kanonischen JSON-`chat_extrakt` überführt werden.

## Direkt verwendbarer Prompt

```text
Erzeuge aus dem bisherigen Verlauf dieses Chats einen kompakten Übergabeblock für die spätere Verarbeitung in der Wissensarchitektur-Registry `wissensarchitektur-registry`.

Ziel:
Der vollständige Chatverlauf ist zu umfangreich oder zu verstreut, um ihn direkt zu kopieren. Verdichte deshalb die relevanten Erkenntnisse so, dass sie anschließend mit dem Registry-Prompt `Chat-Extraktion` weiterverarbeitet werden können.

Wichtige Regeln:
- Antworte auf Deutsch.
- Erfinde nichts hinzu.
- Trenne klar zwischen gesichertem Befund, Interpretation, Hypothese, Entscheidung, offenem Punkt und Aufgabe.
- Markiere Unsicherheiten ausdrücklich.
- Behandle Registry-Änderungen nicht als bereits umgesetzt.
- Behandle TheBrain-Änderungen nicht als bereits umgesetzt, nur weil sie im Chat erwähnt wurden.
- Wenn eine Domäne nur vermutet wird, kennzeichne sie als unsicher.
- Wenn Inhalte nicht in eine bestehende Domäne passen, benenne sie nur als möglichen Domänenkandidaten.
- Fasse nicht den ganzen Chat chronologisch zusammen, sondern extrahiere das, was für die spätere Wissensarchitektur relevant ist.

Aktuell bekannte Domänen:
- `m365_sharepoint`
- `hr_data_hub`
- `wissenssystem_thebrain`

Gib ausschließlich gültiges JSON in folgender Struktur zurück:

{
  "wissensarchitektur_uebergabe": {
    "marker": "WISSENSARCHITEKTUR_EXTRAKTION_BEREIT",
    "metadaten": {
      "titel": "",
      "thema": "",
      "zeitlicher_kontext": "",
      "ausloeser_der_uebergabe": "",
      "chatstand": "abgeschlossen | zwischenstand | unklar"
    },
    "kurzkontext": "",
    "gesicherte_befunde": [],
    "interpretationen": [],
    "hypothesen": [],
    "entscheidungen": [
      {
        "inhalt": "",
        "status": "getroffen | vorgeschlagen | verworfen | unklar",
        "begruendung": ""
      }
    ],
    "offene_punkte": [
      {
        "inhalt": "",
        "warum_offen": "",
        "empfohlener_naechster_schritt": ""
      }
    ],
    "aufgabenhinweise": [
      {
        "titel": "",
        "beschreibung": "",
        "aufgabentyp": "umsetzung | pruefung | dokumentation | entscheidung | review",
        "status_hinweis": "neu | in_pruefung | geplant | abgeschlossen | unklar"
      }
    ],
    "thebrain_hinweise": [
      {
        "titel": "",
        "moegliche_einordnung": "",
        "status_hinweis": "hinweis | vorzubereiten | umgesetzt_unbestaetigt | unklar",
        "begruendung": ""
      }
    ],
    "domaenenhinweise": [
      {
        "domaene": "",
        "sicherheit": "hoch | mittel | niedrig",
        "begruendung": ""
      }
    ],
    "artefakte_und_nachweise": [
      {
        "typ": "",
        "bezeichnung": "",
        "rolle_im_chat": ""
      }
    ],
    "repo_bezuege": [
      {
        "pfad_oder_objekt": "",
        "rolle": ""
      }
    ],
    "empfohlene_folgeschritte": [
      "chat_extraktion"
    ]
  }
}
```

## Hinweise zur Weiterverarbeitung

- Der Übergabeblock ist noch kein kanonischer Registry-Eintrag.
- Der nächste Schritt ist die interne Chat-Extraktion unter `prompts/registry_workflow/01_eingang/chat_extraktion.md`.
- Der Übergabeblock kann dort anstelle eines vollständigen Chatverlaufs als Eingabe verwendet werden.
