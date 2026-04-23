# Prompt: Chat-Extraktion

## Zweck

Dieser Prompt extrahiert aus einem Chat die fachlich relevanten Wissenselemente in einer Form, die anschließend domänenspezifisch weiterverarbeitet werden kann. Er trennt Rohkommunikation von wiederverwendbarem Wissen.

## Eingabe

Als Eingabe wird ein vollständiger Chat oder ein zusammenhängender Gesprächsausschnitt mit ausreichendem Kontext erwartet. Zusätzliche Metadaten wie Datum, Beteiligte oder Arbeitskontext können ergänzt werden, sind aber nicht zwingend.

## Prüffragen

- Welche fachlich relevanten Aussagen sind im Chat enthalten?
- Welche Entscheidungen wurden bereits getroffen?
- Welche Annahmen, Risiken oder offenen Punkte sind erkennbar?
- Welche Artefakte, Quellen oder Systeme werden genannt?
- Welche Begriffe wirken domänenprägend oder strukturrelevant?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges YAML im folgenden Format erfolgen:

```yaml
chat_extrakt:
  quelle:
    typ: Chat
    datum: 2026-04-23
    kontext: Kurzbeschreibung des Gesprächskontexts
  zusammenfassung: Kurze Gesamteinordnung
  wissenselemente:
    - titel: Prägnanter Titel
      typ: Kontext
      beschreibung: Fachlich belastbare Zusammenfassung
      schlüsselbegriffe:
        - Beispielbegriff
      hinweise_domäne:
        - m365_sharepoint
      status: extrahiert
  offene_punkte:
    - Beschreibung eines offenen Punkts
  entscheidungen:
    - Beschreibung einer bereits getroffenen Entscheidung
  quellenhinweise:
    - Nennung einer relevanten Quelle oder Referenz
```

## Direkt verwendbarer Prompt

Du erhältst einen Chat oder Gesprächsausschnitt als Rohmaterial. Extrahiere daraus nur die fachlich relevanten Wissenselemente für eine spätere Aufnahme in eine Wissensarchitektur.

Arbeite mit folgenden Regeln:

- Formuliere präzise und ohne unnötige Ausschmückung.
- Trenne gesicherte Aussagen von Annahmen und offenen Punkten.
- Leite keine Strukturentscheidung vorweg, wenn der Chat dafür nicht belastbar genug ist.
- Markiere nur solche Domänenhinweise, die sich aus dem Inhalt nachvollziehbar ergeben.
- Antworte ausschließlich im vorgegebenen YAML-Format.

Zu verarbeitender Chat:

```text
[Hier steht der Chatinhalt.]
```
