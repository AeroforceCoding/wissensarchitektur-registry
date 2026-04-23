# Prompt: Registry-Abgleich

## Zweck

Dieser Prompt prüft, ob ein neues Wissenselement innerhalb einer Ziel-Domäne bereits durch vorhandene Knoten, Beziehungen, semantische Zuordnungen oder Quellen abgedeckt ist. Er dient der Dublettenkontrolle und der geordneten Weiterentwicklung bestehender Register.

## Eingabe

Erwartet werden:

- ein oder mehrere Wissenselemente aus dem Chat-Extrakt,
- die festgelegte Ziel-Domäne,
- die relevanten Domänendateien, insbesondere `kanonische_knoten.yml`, `beziehungen.yml` und `semantische_zuordnungen.yml`.

## Prüffragen

- Gibt es bereits einen kanonischen Knoten mit gleicher oder sehr ähnlicher Bedeutung?
- Ist eine Ergänzung eines bestehenden Knotens sinnvoller als ein neuer Eintrag?
- Besteht Dublettengefahr oder eine unklare Abgrenzung?
- Welche Beziehungen oder Quellen sollten mit geprüft werden?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges YAML im folgenden Format erfolgen:

```yaml
registry_abgleich:
  domäne: m365_sharepoint
  ergebnisse:
    - wissenselement: Prägnanter Titel
      status: bestehender_treffer
      vorhandener_knoten_id: beispiel_knoten
      begründung: Warum der Treffer passt
      empfohlene_folgeaktion: bestehenden_knoten_erweitern
  semantische_prüfung_erforderlich: false
  hinweise:
    - Kurzer Hinweis zur Weiterverarbeitung
```

## Direkt verwendbarer Prompt

Du erhältst neue Wissenselemente und die Register einer Ziel-Domäne. Prüfe, ob bereits passende kanonische Knoten, Beziehungen oder semantische Zuordnungen existieren.

Arbeite mit folgenden Regeln:

- Lege den Schwerpunkt auf Wiederverwendung vor Neuerstellung.
- Benenne Dublettengefahr ausdrücklich.
- Empfehle eine semantische Prüfung nur dann, wenn echte Unschärfe oder Konfliktpotenzial vorliegt.
- Antworte ausschließlich im vorgegebenen YAML-Format.

Eingabe:

```yaml
wissenselemente: []
domäne: m365_sharepoint
registerauszug: {}
```
