# Prompt: Semantische Prüfung

## Zweck

Dieser Prompt klärt Bedeutungsnähe, Abgrenzung, mögliche Widersprüche und Dubletten. Er wird nur eingesetzt, wenn der Registry-Abgleich keine eindeutige Entscheidung erlaubt.

## Eingabe

Erwartet werden ein strittiges oder unklar zuordenbares Wissenselement sowie die fachlich ähnlichen bestehenden Knoten, Beziehungen oder Zuordnungen aus der Ziel-Domäne.

## Prüffragen

- Beschreibt das neue Wissenselement tatsächlich etwas Eigenständiges?
- Ist es nur eine andere Formulierung eines bestehenden Knotens?
- Ergänzt, konkretisiert oder widerspricht es einem vorhandenen Registereintrag?
- Welche semantische Entscheidung ist für die Architektur am stabilsten?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges YAML im folgenden Format erfolgen:

```yaml
semantische_prüfung:
  prüfgegenstand: Prägnanter Titel
  bewertung: abgrenzen
  sicherheit: mittel
  begründung: Fachliche Einschätzung in knapper Form
  betroffene_knoten:
    - id: bestehender_knoten
      rolle: ähnlicher_knoten
  empfohlene_aktion: neuen_knoten_mit_klarer_abgrenzung_anlegen
  governance_erforderlich: false
```

## Direkt verwendbarer Prompt

Du erhältst einen unklaren oder konfliktträchtigen Wissenseintrag sowie ähnliche bestehende Registereinträge. Prüfe die semantische Lage und gib eine belastbare Empfehlung für Abgrenzung, Zusammenführung, Ergänzung oder Ablehnung.

Arbeite mit folgenden Regeln:

- Begründe die Entscheidung fachlich und nicht nur sprachlich.
- Bevorzuge stabile, langfristig verständliche Abgrenzungen.
- Fordere Governance nur dann an, wenn die Entscheidung strukturelle Tragweite hat.
- Antworte ausschließlich im vorgegebenen YAML-Format.

Eingabe:

```yaml
prüfgegenstand: {}
ähnliche_registereinträge: []
```
