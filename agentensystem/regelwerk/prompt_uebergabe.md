# Prompt-Uebergabe

## Zweck

Diese Datei regelt, wann neue oder wesentlich geaenderte Prompts aus der `wissensarchitektur-registry` als Uebergabebedarf an die `human-system-interface-registry` erkannt werden sollen.

Die `human-system-interface-registry` fuehrt den zentralen Meta-Katalog bekannter Prompts im Repo-Verbund. Die `wissensarchitektur-registry` bleibt jedoch Primaerquelle ihrer eigenen Wissensarchitektur-Prompts.

## Grundsatz

Prompts in der `wissensarchitektur-registry` bleiben hier kanonisch gepflegt.

Wenn in diesem Repository ein neuer Prompt entsteht oder ein bestehender Prompt wesentlich geaendert wird, soll der Agent einen Uebergabevorschlag an die `human-system-interface-registry` vorbereiten.

Uebergabe bedeutet aktuell nur:

- Metadatenvorschlag fuer den Prompt-Katalog,
- keine automatische technische Weitergabe,
- keine Synchronisation,
- keine Uebernahme des Prompt-Volltexts,
- keine Behauptung, dass die `human-system-interface-registry` bereits aktualisiert wurde.

Der Anwender bleibt manuelle Uebertragungs- und Freigabeschicht.

## Wann Uebergabebedarf entsteht

Ein Uebergabevorschlag soll vorbereitet werden, wenn:

- ein neuer Prompt in `prompts/` angelegt wird,
- ein bestehender Prompt einen neuen Zweck, neuen Zielkontext oder neue erwartete Ausgabe erhaelt,
- ein Prompt in eine andere Workflow-Phase verschoben oder fachlich neu eingeordnet wird,
- ein Prompt fuer andere Repositories oder den Repo-Verbund relevant wird,
- ein Prompt eine neue wiederverwendbare Handlung, Rolle oder Uebergabelogik beschreibt.

Kein Uebergabevorschlag ist erforderlich, wenn:

- nur Tippfehler, Formatierung oder kleine sprachliche Klarstellungen geaendert werden,
- der Prompt nur lokal intern erlaeutert wird und keine Metadaten im Meta-Katalog veraendert wuerden,
- der Inhalt sensibel waere und nicht als nicht-sensibler Metadatenvorschlag abstrahiert werden kann.

## Uebergabeformat

Das folgende Format beschreibt einen minimalen Metadatenvorschlag fuer den Prompt-Katalog. Es ist kein produktives Synchronisationsschema und keine technische Verbindung.

```yaml
prompt_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "human-system-interface-registry"
  prompt_id: "OFFEN"
  titel: "OFFEN"
  quelle_pfad: "OFFEN"
  zweck: "OFFEN"
  wann_verwenden: "OFFEN"
  zielkontext: "wissensarchitektur"
  sicherheitsstatus: "nicht_sensibel"
  volltext_uebernehmen: false
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

## Statusregel

Der Status `vorschlag` bedeutet nur, dass ein moeglicher Metadatenhinweis fuer den Prompt-Katalog erkannt und formuliert wurde.

Er bedeutet nicht:

- dass die `human-system-interface-registry` aktualisiert wurde,
- dass der Prompt-Volltext uebernommen wurde,
- dass eine technische Synchronisation besteht,
- dass der Prompt ausserhalb der `wissensarchitektur-registry` kanonisch geworden ist.

## Grenzen

Diese Regel erzeugt keine Aenderung an anderen Repositories, keine automatische Synchronisation, keine technische Verbindung, keine Docker-Dateien und keine TheBrain-Aenderung.

Sie erweitert nur die Erkennungsregel fuer manuelle Prompt-Metadatenuebergaben im Repo-Verbund.
