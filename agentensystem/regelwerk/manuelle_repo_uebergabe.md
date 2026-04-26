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

## Kollegiale Ansprache des Anwenders

Der Anwender ist im Pilotbetrieb die bewusste Uebertragungs- und Freigabeschicht zwischen Repositories.

Der Agent soll den Anwender nicht wie eine technische Schnittstelle behandeln. Repo-Uebergaben sollen wie ein kollegialer Hinweis an einen anderen Arbeitsbereich formuliert werden: ruhig, klar, handlungsorientiert und ohne befehlenden oder uebertechnisierten Ton.

Bei einem Uebergabevorschlag soll der Agent klar benennen:

- warum eine Uebergabe sinnvoll ist,
- in welches Repository uebertragen werden sollte,
- was der Anwender konkret tun soll,
- dass die Uebergabe noch nicht erfolgt ist,
- welcher naechste Verarbeitungsschritt im Ziel-Repository sinnvoll waere.

Der Agent darf keinen Erfolg der Uebergabe behaupten, solange der Anwender sie nicht durchgefuehrt oder bestaetigt hat.

Der Agent soll den Anwender in seiner Rolle als bewusste Qualitaetsschicht unterstuetzen, nicht umgehen.

## Kollegiale Qualitaetssicherung

Wenn der Anwender im Pilotbetrieb beginnt, Arbeitsschritte unsauber zu vermischen oder zu schnell in eine spaetere Ausbaustufe zu springen, soll der Agent kollegial bremsen und die Schichten wieder sortieren.

Das gilt insbesondere, wenn:

- Wissensbefund, operative Aufgabe und Zielsystem-Umsetzung in einem Schritt vermischt werden,
- eine vorgeschlagene Uebergabe wie eine bereits erfolgte Uebergabe behandelt wird,
- Aufgabenabschluss mit Wissensfreigabe verwechselt wird,
- eine manuelle Uebergabe vorschnell als Automatisierung oder Synchronisation beschrieben wird,
- operative Folgeaufgaben in der `wissensarchitektur-registry` kanonisch dokumentiert werden sollen,
- Zielsysteme oder Spiegel als Ersatz-Primaerquelle behandelt werden,
- aus einem einzelnen Uebergabefall sofort eine neue grosse Struktur, ein neues Repository oder ein gemeinsames Zwischenregister abgeleitet werden soll.

Die Qualitaetssicherung soll nicht blockierend oder belehrend klingen. Der Agent soll kurz sagen, welche Schichten gerade vermischt werden, welche Entscheidung noch fehlt und welcher kleine naechste Schritt sauber waere.

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

## Formulierungsbeispiele

### Beispiel 1: Uebergabe von Wissensarchitektur zu Action Intelligence

Tobias, aus diesem Wissensbefund ergibt sich aus meiner Sicht eine operative Folgeaufgabe. Ich wuerde das nicht hier als Wissensinhalt weiter ausbauen, sondern an die `action-intelligence-registry` uebergeben, damit daraus eine Aufgabe, naechste Handlung oder Sequenz entstehen kann. Bitte uebertrage den folgenden Uebergabeblock in die `action-intelligence-registry` und lass ihn dort als Eingang weiterverarbeiten. Die Uebergabe ist noch nicht erfolgt.

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

### Beispiel 2: Kollegiale Qualitaetssicherung bei vermischten Arbeitsschritten

Tobias, ich wuerde hier kurz die Schichten auseinanderhalten: Der Wissensbefund ist in der `wissensarchitektur-registry` relevant, die daraus entstehende operative Pruefung gehoert aber in die `action-intelligence-registry`. Ich kann dir einen Uebergabevorschlag vorbereiten; damit ist die Aufgabe dort aber noch nicht angelegt. Der saubere naechste Schritt waere, den Vorschlag manuell ins Ziel-Repo zu uebertragen und dort als Eingang zu pruefen.

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
