# Prompt: Governance-Entscheidung

- Titel: Governance-Entscheidung
- Zweck: Strukturrelevante Änderungen, Standards und Konfliktlagen verbindlich entscheiden.
- Wann verwenden: Wenn Prüfung und Abgleich nicht ausreichen und eine belastbare Strukturentscheidung nötig ist.
- Erwartete Eingabe: Änderungsvorschlag, Prüfergebnisse und betroffene Registerbereiche.
- Erwartete Ausgabe: Ein YAML-`governance_entscheidung` mit Entscheidung, Auflagen und Wirksamkeit.
- Nächster Schritt: `prompts/05_aktualisierung/registry_aktualisieren.md`

## Zweck

Dieser Prompt bereitet eine belastbare Governance-Entscheidung vor, wenn eine Strukturänderung, ein neuer Standard, ein Ersatz bestehender Muster oder eine konfliktträchtige Einordnung entschieden werden muss.

## Eingabe

Erwartet werden die vorgeschlagene Änderung, das Ergebnis aus Registry-Abgleich und gegebenenfalls semantischer Prüfung sowie die betroffenen Domänen- oder Globaldateien.

## Prüffragen

- Verändert der Vorschlag eine bestehende Struktur, Regel oder Namenslogik?
- Welche Vorteile, Risiken und Folgewirkungen ergeben sich?
- Gibt es eine stabilere Alternative mit geringerem Umstellungsaufwand?
- Welche Freigabe oder Auflage ist erforderlich, bevor die Registry geändert wird?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges YAML im folgenden Format erfolgen:

```yaml
governance_entscheidung:
  entscheidungsgegenstand: Kurztitel der Strukturfrage
  entscheidung: freigeben
  auflagen:
    - Betroffene Dokumentation mitpflegen
  begründung: Knappe, nachvollziehbare Entscheidungslogik
  betroffene_bereiche:
    - global/beziehungstypen.yml
    - domänen/m365_sharepoint/kanonische_knoten.yml
  wirksam_ab: 2026-04-23
```

## Direkt verwendbarer Prompt

Du erhältst einen Änderungsvorschlag mit struktureller Tragweite. Triff oder formuliere eine Governance-Entscheidung so, dass die anschließende Registry-Aktualisierung belastbar und nachvollziehbar ist.

Arbeite mit folgenden Regeln:

- Benenne Auswirkungen auf Register, Domänen und Folgearbeit klar.
- Formuliere Auflagen nur dann, wenn sie wirklich nötig sind.
- Triff keine Entscheidung auf Basis bloßer Vermutungen.
- Antworte ausschließlich im vorgegebenen YAML-Format.

Eingabe:

```yaml
änderungsvorschlag: {}
prüfergebnisse: {}
```
