# Prompt: Wissensnotiz transformieren

- Titel: Wissensnotiz transformieren
- Zweck: Notizen, Einfälle, Erinnerungen, Erkenntnisse, Lernergebnisse, Reflexionen, Zitate oder externe Dateien in einen integrationsfähigen Informationsblock überführen.
- Handlung: Eingang vorbereiten (`eingang_vorbereiten`)
- Wann verwenden: Wenn Wissen nicht primär aus einem Chat oder einem abgeschlossenen Aufgabenverlauf stammt, sondern aus freien Notizen, Dokumenten, Bildern, Zitaten, Lernmomenten oder Reflexionen.
- Erwartete Eingabe: Notiztext, Zitat, Reflexion, Lernergebnis, Dateihinweis oder Beschreibung eines externen Artefakts mit optionalem Kontext.
- Erwartete Ausgabe: Ein JSON-`informationsblock` mit Herkunft, Aussageart, Befunden, Interpretationen, Hypothesen, offenen Punkten, Domänenhinweisen und empfohlener Repo-Zuordnung.
- Nächster Schritt: `prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md` oder bei unklarer Zuständigkeit Repo-/Domänenkandidat prüfen.

## Zweck

Dieser Prompt erweitert die Eingangsschicht über Chats und Aufgaben hinaus. Er dient dazu, freie Wissensrohstoffe in eine strukturierte Form zu bringen, damit sie anschließend der Gesamtarchitektur, einer Domäne und gegebenenfalls einem passenden Repository zugeordnet werden können.

Typische Eingänge sind:

- spontane Einfälle,
- persönliche Erinnerungen,
- fachliche Erkenntnisse,
- Lernergebnisse,
- Reflexionen,
- Zitate,
- Word-Dokumente,
- Bilddateien,
- Screenshots,
- PDF-Auszüge,
- sonstige externe Wissensartefakte.

Die Transformation erzeugt noch keinen kanonischen Registry-Eintrag. Sie bereitet einen Informationsblock vor, der anschließend geprüft, zugeordnet und gegebenenfalls in eine Domäne oder ein anderes zuständiges Repository weitergeleitet werden kann.

## Abgrenzung

- Für vollständige Chatverläufe verwende zuerst `chat_extraktion.md`.
- Für abgeschlossene Aufgaben mit Nachweisen verwende zuerst `aufgabenabschluss_verdichten.md`.
- Für reine Artefakt-Metadaten verwende zuerst `artefakt_metadaten_erfassen.md`.
- Für nicht abgeschlossene oder blockierte Sessions verwende `session_problemspur_erfassen.md`.

Wenn eine Datei selbst als Nachweis relevant ist, soll sie zusätzlich als Artefakt referenziert werden. Der Informationsblock enthält dann die fachliche Verdichtung; die Datei bleibt Quelle oder Nachweis.

## Prüffragen

- Was ist der Kern der Notiz oder des Materials?
- Handelt es sich um Fakt, Interpretation, Hypothese, Reflexion, Zitat, Lernergebnis, Erinnerung oder offene Frage?
- Welche Aussage ist wiederverwendbar genug, um später in die Wissensarchitektur einzufließen?
- Welche Quelle oder welches Artefakt stützt die Aussage?
- Welche Domäne oder welches Repository könnte zuständig sein?
- Ist die Information privat, unsicher, urheberrechtlich sensibel oder nur als persönlicher Reflexionshinweis geeignet?
- Welche weitere Prüfung ist erforderlich, bevor daraus Registry-Wissen werden darf?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges JSON im folgenden Format erfolgen:

```json
{
  "informationsblock": {
    "informationsblock_id": "ib_2026_0001",
    "titel": "",
    "herkunft_typ": "notiz | einfall | erinnerung | erkenntnis | lernergebnis | reflexion | zitat | dokument | bilddatei | sonstiges",
    "herkunft_ref": "",
    "führende_domäne": "",
    "repo_zuordnung": {
      "ziel_repo": "",
      "sicherheit": "hoch | mittel | niedrig | unklar",
      "begründung": ""
    },
    "domänenhinweise": [

    ],
    "kontext_refs": [

    ],
    "kurzbeschreibung": "",
    "gesicherte_befunde": [

    ],
    "interpretationen": [

    ],
    "hypothesen": [

    ],
    "reflexionen": [

    ],
    "zitate": [
      {
        "zitat_id": "zit_0001",
        "inhalt": "",
        "quelle": "",
        "nutzungsnotiz": ""
      }
    ],
    "offene_punkte": [

    ],
    "artefakt_refs": [

    ],
    "verwandte_repo_objekte": [

    ],
    "empfohlener_nächster_workflow_schritt": "domänen_zuordnung | registry_abgleich | artefakt_metadaten_erfassen | problemspur_erfassen | repo_zuordnung_prüfen",
    "strukturrelevanz": "niedrig | mittel | hoch | unklar",
    "validierungsstand": "unvalidiert | vorgeprüft | geprüft",
    "erstellt_am": "2026-04-24",
    "zuletzt_geändert": "2026-04-24",
    "notizen": ""
  }
}
```

## Direkt verwendbarer Prompt

Du erhältst eine Notiz, einen Einfall, eine Erinnerung, ein Lernergebnis, eine Reflexion, ein Zitat oder einen Hinweis auf ein externes Dokument oder Bild. Transformiere dieses Material in einen Informationsblock für die Wissensarchitektur-Registry.

Arbeite mit folgenden Regeln:

- Antworte auf Deutsch.
- Erfinde nichts hinzu.
- Trenne Fakt, Interpretation, Hypothese, Reflexion, Zitat, Lernergebnis, Erinnerung und offenen Punkt.
- Behandle die Ausgabe nicht als kanonischen Registry-Eintrag, sondern als vorbereiteten Informationsblock.
- Wenn eine Quelle, Datei oder ein Bild als Nachweis relevant ist, führe sie als Artefakt- oder Quellenhinweis.
- Markiere Unsicherheiten ausdrücklich.
- Schlage eine Domäne oder ein zuständiges Repository nur mit Begründung vor.
- Wenn keine bestehende Domäne passt, markiere einen Domänenkandidaten statt eine neue Domäne festzulegen.
- Antworte ausschließlich im vorgegebenen JSON-Format.

Eingabe:

```json
{
  "wissensrohstoff": {
    "typ": "notiz | einfall | erinnerung | erkenntnis | lernergebnis | reflexion | zitat | dokument | bilddatei | sonstiges",
    "inhalt_oder_beschreibung": "",
    "quelle_oder_datei": "",
    "kontext": "",
    "vermutete_domäne": "",
    "vermutetes_ziel_repo": ""
  }
}
```
