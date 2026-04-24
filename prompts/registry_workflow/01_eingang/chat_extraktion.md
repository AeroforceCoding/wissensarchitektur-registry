# Prompt: Chat-Extraktion

- Titel: Chat-Extraktion
- Zweck: Neue Chatinhalte in einen strukturierten Wissensextrakt für die weitere Registry-Verarbeitung überführen.
- Wann verwenden: Immer dann, wenn ein Chat oder Gesprächsausschnitt erstmals in die Wissensarchitektur aufgenommen werden soll.
- Erwartete Eingabe: Ein Chatinhalt oder Gesprächsausschnitt mit optionalem Kontext.
- Erwartete Ausgabe: Ein YAML-`chat_extrakt` mit Aussagen, Entitäten, Entscheidungen, offenen Punkten, Aufgaben- und TheBrain-Hinweisen.
- Nächster Schritt: `prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md`

## Kanonischer Prompttext

```text
Analysiere den folgenden Chatinhalt und überführe ihn in einen strukturierten Wissensextrakt für die Weiterverarbeitung innerhalb der Wissensarchitektur-Registry.

Ziel:
Der Chat soll nicht nur zusammengefasst, sondern in klar unterscheidbare Wissenselemente zerlegt werden, damit anschließend Domänenzuordnung, Registry-Abgleich, semantische Prüfung, Governance-Entscheidung und TheBrain-Update-Vorbereitung möglich werden.

Wichtige Regeln:
- Antworte auf Deutsch.
- Arbeite präzise und trenne sauber zwischen Fakt, Interpretation, Hypothese, Entscheidung, offenem Punkt und Aufgabe.
- Erfinde nichts hinzu.
- Wenn etwas unklar ist, kennzeichne es als unklar statt es zu glätten.
- Fasse nicht nur zusammen, sondern extrahiere strukturierte Einheiten.
- Formuliere so, dass die Ausgabe später in YAML-Dateien oder Prüfprozessen weiterverwendet werden kann.

Analysiere den Chat nach folgenden Kategorien:

1. Metadaten
- Titel oder Kurzbezeichnung des Chats, falls erkennbar
- thematischer Schwerpunkt
- zeitlicher Kontext, falls erkennbar
- beteiligte Systeme, Werkzeuge oder Plattformen

2. Kernaussagen
Extrahiere die wichtigsten Aussagen als einzelne Einträge.
Für jede Aussage:
- statement_id
- typ: fakt | interpretation | hypothese | entscheidung | offener_punkt
- inhalt
- confidence: hoch | mittel | niedrig
- quelle_abschnitt: kurzer Verweis auf die Stelle im Chat

3. Entitäten und Objekte
Extrahiere relevante Objekte, Systeme, Personen, Dateien, Rollen, Begriffe oder Strukturen.
Für jeden Eintrag:
- entity_id
- name
- typ
- kurze_beschreibung

4. Entscheidungen
Extrahiere getroffene oder vorgeschlagene Entscheidungen.
Für jeden Eintrag:
- decision_id
- inhalt
- status: getroffen | vorgeschlagen | verworfen | unklar
- begründung, falls erkennbar

5. Offene Punkte
Extrahiere ungeklärte Fragen, Unsicherheiten oder Prüfbedarfe.
Für jeden Eintrag:
- open_id
- inhalt
- warum_offen
- empfohlener_nächster_schritt

6. Aufgabenhinweise
Extrahiere Handlungen, die als Aufgaben verstanden werden können.
Für jeden Eintrag:
- task_hint_id
- titel
- beschreibung
- aufgabentyp: umsetzung | prüfung | dokumentation | entscheidung | review
- status_hinweis: neu | in_prüfung | geplant | unklar
- confidence

7. TheBrain-Hinweise
Extrahiere Inhalte, die wahrscheinlich zu einem THEBRAIN_TASK oder einer TheBrain-Änderung führen könnten.
Für jeden Eintrag:
- thebrain_hint_id
- titel
- mögliche_einordnung
- begründung
- confidence

8. Domänenhinweise
Schätze ein, zu welchen Domänen der Inhalt wahrscheinlich gehört.
Für jeden Eintrag:
- domäne
- begründung
- confidence

9. Artefakte und Nachweise
Extrahiere Hinweise auf Dateien, Screenshots, Dokumente, Tools, Repositories, URLs oder andere Nachweise.
Für jeden Eintrag:
- artifact_id
- typ
- bezeichnung
- rolle_im_chat

10. Kompakte Gesamteinordnung
Am Ende:
- kurzbeschreibung
- worin_der_hauptnutzen_des_chats_liegt
- welche_folgeschritte_logisch_sind

Gib das Ergebnis in genau dieser YAML-Struktur zurück:

chat_extrakt:
  metadaten:
    titel: ""
    schwerpunkt: ""
    zeitlicher_kontext: ""
    systeme_und_werkzeuge: []

  kernaussagen: []

  entitäten_und_objekte: []

  entscheidungen: []

  offene_punkte: []

  aufgabenhinweise: []

  thebrain_hinweise: []

  domänenhinweise: []

  artefakte_und_nachweise: []

  gesamteinordnung:
    kurzbeschreibung: ""
    hauptnutzen: ""
    logische_folgeschritte: []

Hier ist der zu analysierende Chatinhalt:
[CHAT HIER EINFÜGEN]
```
