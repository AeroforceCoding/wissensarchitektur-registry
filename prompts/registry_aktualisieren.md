# Prompt: Registry aktualisieren

## Zweck

Dieser Prompt übersetzt bestätigte Ergebnisse in konkrete Änderungen an den relevanten Registry-Dateien. Er bündelt, welche Knoten, Beziehungen, Quellen, Logs und Verlaufsdateien angepasst werden sollen.

## Eingabe

Erwartet werden bestätigte Abgleichsergebnisse, gegebenenfalls semantische Bewertungen, Governance-Entscheidungen sowie die betroffene Ziel-Domäne und die zu aktualisierenden Registerdateien.

## Prüffragen

- Welche Dateien müssen tatsächlich geändert werden?
- Welche Einträge werden neu angelegt, ergänzt oder fortgeschrieben?
- Welche Verlaufs- und Logeinträge sichern die Nachvollziehbarkeit?
- Welche Änderungen bleiben bewusst außerhalb der Registry und gehören erst in die TheBrain-Vorbereitung?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges YAML im folgenden Format erfolgen:

```yaml
registry_aktualisierung:
  domäne: m365_sharepoint
  dateiänderungen:
    - datei: domänen/m365_sharepoint/kanonische_knoten.yml
      aktion: ergänzen
      inhalt: Neuer Knoten oder Ergänzung eines bestehenden Knotens
    - datei: domänen/m365_sharepoint/verlaufsänderungen.yml
      aktion: fortschreiben
      inhalt: Dokumentation der vorgenommenen Änderung
  thebrain_vorbereitung_erforderlich: true
  hinweise:
    - Änderungen erst nach bestätigter Freigabe schreiben
```

## Direkt verwendbarer Prompt

Du erhältst bestätigte Ergebnisse aus der Wissensverarbeitung. Leite daraus die notwendigen Registry-Änderungen ab und benenne präzise, welche Dateien wie fortgeschrieben werden sollen.

Arbeite mit folgenden Regeln:

- Beschreibe nur bestätigte Änderungen.
- Halte Verlaufs- und Logdateien synchron zur fachlichen Änderung.
- Trenne Registry-Arbeit klar von späteren TheBrain-Umsetzungen.
- Antworte ausschließlich im vorgegebenen YAML-Format.

Eingabe:

```yaml
bestätigte_ergebnisse: {}
ziel_domäne: m365_sharepoint
```
