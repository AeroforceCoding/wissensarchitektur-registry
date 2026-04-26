# Manuelle Repo-Uebergabe

## Zweck

Diese Datei dokumentiert Regeln fuer manuelle Repo-Uebergaben zwischen der `wissensarchitektur-registry` und der `action-intelligence-registry`.

Ziel ist, dass der Agent erkennen kann, wann ein Wissensbefund, eine Architekturspannung oder eine Governance-Erkenntnis als operative Folgeaufgabe an die `action-intelligence-registry` uebergeben werden sollte, ohne diese Uebergabe automatisch auszufuehren.

Der Anwender bleibt vorerst die manuelle Uebertragungsschicht.

## Grundsatz

Der Agent darf Uebergabebedarf erkennen und einen Uebergabevorschlag vorbereiten.

Der Agent darf nicht behaupten, dass eine Uebergabe bereits erfolgt ist, solange sie nicht durch den Anwender oder durch eine spaeter bestaetigte technische Ausbaustufe belegt ist.

Technische Automatisierung, Synchronisation oder direkte Aenderungen in anderen Repositories sind nicht Bestandteil dieser Regel. Sie koennen spaeter als eigene Ausbaustufe geprueft werden, gelten aber aktuell nicht als vorhanden.

## Rolle des Anwenders

Der Anwender fungiert vorerst als Uebertragungsschicht zwischen den Repositories.

Das bedeutet:

- Der Agent bereitet einen Uebergabevorschlag vor.
- Der Anwender entscheidet, ob und wohin der Vorschlag uebernommen wird.
- Die tatsaechliche Anlage oder Aenderung in der `action-intelligence-registry` erfolgt nicht automatisch durch die `wissensarchitektur-registry`.
- Ein vorbereiteter Uebergabevorschlag ist kein Nachweis einer erfolgten Uebergabe.

## Uebergabebedarf von wissensarchitektur-registry zu action-intelligence-registry

Eine Uebergabe an die `action-intelligence-registry` soll vorgeschlagen werden, wenn mindestens einer dieser Faelle vorliegt:

- Ein Wissenselement erzeugt eine operative Folgeaufgabe.
- Eine offene Architekturspannung muss geprueft oder entschieden werden.
- Eine Quelle fehlt und soll beschafft werden.
- Eine Domaenenzuordnung ist unklar und braucht operative Klaerung.
- Ein Registry-Abgleich loest eine konkrete Pruefung oder Korrektur aus.
- Eine semantische Pruefung erzeugt eine Folgehandlung.
- Eine Governance-Entscheidung muss vorbereitet oder umgesetzt werden.
- Ein TheBrain- oder Obsidian-Update soll als Aufgabe verfolgt werden.
- Eine veraltete oder widerspruechliche Wissenslage erfordert eine Pruefung.

## Keine Uebergabe erforderlich

Keine Uebergabe ist erforderlich, wenn:

- Ein Wissenselement nur kanonisch dokumentiert wird.
- Keine operative Folgehandlung entsteht.
- Keine Pruefung, Entscheidung oder Umsetzung noetig ist.
- Nur TheBrain oder Obsidian als Ziel- oder Spiegelschicht informiert werden.
- Es sich nur um eine interne Wissensstrukturierung handelt.

## Uebergabeformat

Das folgende Format beschreibt einen minimalen Uebergabevorschlag. Es ist kein produktives Schema und keine technische Synchronisation.

```yaml
repo_uebergabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "action-intelligence-registry"
  uebergabetyp: "folgeaufgabe"
  ausloeser:
    typ: "offene_architekturspannung"
    pfad: "OFFEN"
    wissenselement_id: null
  vorschlag:
    titel: "OFFEN"
    beschreibung: "OFFEN"
    empfohlener_zielbereich: "eingang/rohe_eingaenge.yml | registry/aufgaben.yml | registry/projekte.yml | registry/fristen.yml"
  wissensbezug:
    wissensquelle_repo: "wissensarchitektur-registry"
    wissensquelle_pfad: "OFFEN"
    wissenselement_id: null
    bezugstyp: "erzeugt_folgeaufgabe"
    referenzstatus: "vermutet"
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

## Statusregel

Der Status `vorschlag` bedeutet nur, dass eine moegliche Repo-Uebergabe erkannt und formuliert wurde.

Er bedeutet nicht:

- dass die Uebergabe ausgefuehrt wurde,
- dass in der `action-intelligence-registry` bereits eine Aufgabe existiert,
- dass das betroffene Wissenselement geaendert wurde,
- dass eine Governance-Entscheidung bereits getroffen wurde.

## Grenzen

Diese Regel erzeugt keine Automatisierung, keine technische Synchronisation, kein neues Repository und keine Aenderung an anderen Repositories.

Sie begruendet auch keine grosse Struktur- oder Schema-Aenderung. Wenn Uebergabevorschlaege wiederholt auftreten, kann spaeter geprueft werden, ob ein stabileres Format oder eine technische Ausbaustufe sinnvoll ist.
