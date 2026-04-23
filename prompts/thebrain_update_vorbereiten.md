# Prompt: TheBrain-Update vorbereiten

## Zweck

Dieser Prompt erstellt aus bestätigten Registry-Änderungen eine umsetzbare, aber getrennt nachverfolgbare Liste von TheBrain-Anpassungen. Er bereitet die operative Umsetzung vor, ohne Registry und Zielsystem gleichzusetzen.

## Eingabe

Erwartet werden die bestätigten Registry-Änderungen, die Ziel-Domäne, der vorgesehene Hauptast in TheBrain und gegebenenfalls zusätzliche Hinweise zu Knoten, Beziehungen oder Etiketten.

## Prüffragen

- Welche Knoten müssen in TheBrain neu angelegt, ergänzt oder umgehängt werden?
- Welche Beziehungen, Etiketten oder Icon-Zuordnungen folgen aus der Registry?
- Welche Änderungen sind vorbereitet, aber noch nicht umgesetzt?
- Welche Schritte benötigen später eine manuelle Prüfung in TheBrain?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges YAML im folgenden Format erfolgen:

```yaml
thebrain_update_vorbereitung:
  domäne: m365_sharepoint
  ziel_ast: Wissensarchitektur/Microsoft 365 SharePoint
  updates:
    - id: tb_m365_002
      status: vorbereitet
      aktion: knoten_anlegen
      bezug_knoten_id: beispiel_knoten
      beschreibung: Knoten im Zielast anlegen und mit bestehender Struktur verbinden
      manuelle_prüfung_erforderlich: true
  umsetzungsnotizen:
    - Reihenfolge der manuellen Umsetzung beachten
```

## Direkt verwendbarer Prompt

Du erhältst bestätigte Registry-Änderungen. Bereite daraus eine eigenständig nachverfolgbare Liste von TheBrain-Updates vor.

Arbeite mit folgenden Regeln:

- Verwende einen klaren Umsetzungsstatus pro Update.
- Beschreibe die Aktion so, dass sie später manuell oder halbautomatisiert umsetzbar ist.
- Vermische keine noch unentschiedenen Strukturfragen mit vorbereiteten Updates.
- Antworte ausschließlich im vorgegebenen YAML-Format.

Eingabe:

```yaml
registry_änderungen: {}
ziel_domäne: m365_sharepoint
```
