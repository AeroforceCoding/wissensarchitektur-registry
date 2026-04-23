# Prompt: Domänen-Zuordnung

## Zweck

Dieser Prompt ordnet extrahierte Wissenselemente der fachlich passendsten Domäne zu. Er dient der gezielten Weiterleitung in das richtige Register und vermeidet vorschnelle Mehrfachablagen.

## Eingabe

Erwartet wird ein strukturierter Chat-Extrakt sowie das aktuelle Domänenregister aus `global/domänenregister.yml`. Wenn die Zuordnung unsicher ist, soll die Unsicherheit ausdrücklich benannt werden.

## Prüffragen

- Welche bestehende Domäne passt am besten zum Schwerpunkt des Wissenselements?
- Gibt es einen klar dominierenden Themenraum oder mehrere konkurrierende?
- Welche Schlüsselbegriffe und Themen aus dem Domänenregister stützen die Zuordnung?
- Ist ein Domänenkandidat notwendig, weil keine bestehende Domäne belastbar passt?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges YAML im folgenden Format erfolgen:

```yaml
domänen_zuordnung:
  führende_domäne: m365_sharepoint
  sicherheit: hoch
  begründung: Kurze fachliche Begründung
  alternative_domänen:
    - name: wissenssystem_thebrain
      rolle: randständig
      begründung: Warum diese Domäne nicht führend ist
  domänenkandidat_erforderlich: false
  betroffene_wissenselemente:
    - titel: Prägnanter Titel
      zuordnung: m365_sharepoint
```

## Direkt verwendbarer Prompt

Du erhältst einen strukturierten Chat-Extrakt und das Domänenregister dieser Wissensarchitektur. Ordne jedes Wissenselement der fachlich passendsten Domäne zu und benenne Unsicherheiten offen.

Arbeite mit folgenden Regeln:

- Bevorzuge eine führende Domäne, wenn der Schwerpunkt klar erkennbar ist.
- Nutze alternative Domänen nur ergänzend und begründet.
- Schlage nur dann einen Domänenkandidaten vor, wenn keine bestehende Domäne tragfähig passt.
- Antworte ausschließlich im vorgegebenen YAML-Format.

Eingabe:

```yaml
chat_extrakt: {}
domänenregister: {}
```
