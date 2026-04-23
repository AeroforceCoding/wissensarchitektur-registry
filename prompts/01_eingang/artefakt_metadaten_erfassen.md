# Prompt: Artefakt-Metadaten erfassen

- Titel: Artefakt-Metadaten erfassen
- Zweck: Einen Screenshot oder eine Bilddatei aus einer laufenden oder abgeschlossenen Aufgabe in einen referenzierbaren Artefaktdatensatz überführen.
- Wann verwenden: Wenn ein Screenshot, Bildnachweis oder ähnliches Artefakt erstmals benannt, beschrieben und dem Repo-Kontext zugeordnet werden soll.
- Erwartete Eingabe: Artefaktbeschreibung, optional Dateiverweis, Aufgabenkontext, Domänenregister, Kontextvokabular und Artefaktstatuswerte.
- Erwartete Ausgabe: Ein YAML-`artefakt_eintrag` mit Dateiname, Kontext, Bezug und Status.
- Nächster Schritt: `prompts/01_eingang/aufgabenabschluss_verdichten.md` oder Referenz als Evidenz belassen

## Zweck

Dieser Prompt erzeugt aus einem Screenshot oder einer Bilddatei einen strukturierten Artefaktdatensatz. Er dient dazu, externe Nachweise benennbar, referenzierbar und später für validierte Informationsblöcke nutzbar zu machen.

## Eingabe

Erwartet werden:

- eine Beschreibung des Artefakts oder ein Dateiverweis,
- der bekannte Aufgaben- oder Situationskontext,
- das Domänenregister aus `global/domänenregister.yml`,
- das Kontextvokabular aus `global/kontext_vokabular.yml`,
- die Artefaktstatuswerte aus `global/artefakt_statuswerte.yml`.

## Prüffragen

- Welche Domäne ist für das Artefakt fachlich führend?
- Welcher bestehende Kontext passt am besten oder sollte vorgeschlagen werden?
- Welcher kurze, navigationsfähige Dateiname ist geeignet?
- Welche Schlagworte, Referenzen und Objektbezüge sollten mitgeführt werden?
- Ist das Artefakt nur Nachweis oder bereits für eine spätere Verdichtung relevant?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges YAML im folgenden Format erfolgen:

```yaml
artefakt_eintrag:
  artefakt_id: art_2026_0001
  artefakt_typ: screenshot
  dateiname: m365_sharepoint__berechtigungspruefung__task-0042__fehlerbild__teams-admin-center.png
  dateiname_schema_version: 1
  speicherort_system: synology_nas
  speicherort_ref: screenshots/m365_sharepoint/m365_sharepoint__berechtigungspruefung__task-0042__fehlerbild__teams-admin-center.png
  domäne: m365_sharepoint
  kontext_id: ctx_0001
  kontext_slug: berechtigungspruefung
  bezug_ref: tb_task_0042
  schritt_slug: fehlerbild
  kurztitel: Teams Admin Center Rollenansicht
  kurzbeschreibung: Kurzbeschreibung des Nachweises
  schlagworte:
    - domäne|m365_sharepoint
  status: metadatiert
  validierungsstand: unvalidiert
  bezug_objekte: []
  informationsblock_refs: []
  notizen: ""
```

## Direkt verwendbarer Prompt

Du erhältst einen Screenshot oder eine Bilddatei aus einer laufenden oder abgeschlossenen Aufgabe. Erzeuge daraus einen strukturierten Artefaktdatensatz für die Wissensarchitektur-Registry.

Arbeite mit folgenden Regeln:

- Leite die Domäne aus der bestehenden Repo-Logik ab, wenn sie erkennbar ist.
- Verwende einen kurzen, navigationsfähigen Dateinamen nach dem Muster `domäne__kontext__bezug__schritt__kurztitel.ext`.
- Verwende IDs nur dort, wo sie Zeichen sparen und die Explorer-Navigation nicht verschlechtern.
- Ordne möglichst einen bestehenden Kontext aus dem Kontextvokabular zu; schlage nur bei Bedarf einen neuen Kontext vor.
- Antworte ausschließlich im vorgegebenen YAML-Format.

Eingabe:

```yaml
artefakt_hinweis: {}
aufgabenkontext: {}
domänenregister: {}
kontext_vokabular: {}
artefakt_statuswerte: {}
```
