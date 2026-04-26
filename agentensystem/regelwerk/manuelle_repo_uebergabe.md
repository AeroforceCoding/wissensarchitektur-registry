# Manuelle Repo-Uebergabe

## Zweck

Diese Datei dokumentiert Regeln fuer manuelle Repo-Uebergaben zwischen der `wissensarchitektur-registry` und anderen Repositories, insbesondere der `action-intelligence-registry`, der `it-infrastruktur-registry` und der `human-system-interface-registry`.

Ziel ist, dass der Agent erkennen kann, wann ein Wissensbefund, eine Architekturspannung oder eine Governance-Erkenntnis als operative Folgeaufgabe an die `action-intelligence-registry`, als abstrahierte Rueckgabe an die `it-infrastruktur-registry` oder als Verbund-/Schnittstellenhinweis an die `human-system-interface-registry` uebergeben werden sollte, ohne diese Uebergabe automatisch auszufuehren.

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

## Kollegiale Abschlussnaehe

Wenn ein aktueller Arbeitsschritt fast abgeschlossen ist und nur noch wenige konkrete Schritte fehlen, soll der Agent den Anwender freundlich darauf hinweisen.

Ziel ist nicht, Druck aufzubauen, sondern Abschlussklarheit herzustellen. Der Agent soll sichtbar machen, dass ein Arbeitsstand mit wenigen Handgriffen sauber abgeschlossen werden kann.

Der Agent soll Abschlussnaehe besonders markieren, wenn:

- ein Uebergabevorschlag bereits formuliert ist und nur noch manuell ins Zielrepo uebertragen werden muss,
- eine Uebergabe im Zielrepo bereits verarbeitet wurde und nur noch Commit oder Push fehlen,
- eine Regelwerksaenderung fachlich abgeschlossen ist und nur noch dokumentiert oder versioniert werden muss,
- ein Arbeitsstand zwischen zwei Repositories geklaert ist und nur noch die Bestaetigung des Anwenders fehlt.

Die Ansprache soll kollegial und knapp bleiben. Der Agent soll benennen:

- was bereits erledigt ist,
- welche ein bis drei Schritte noch fehlen,
- welche Schicht oder welches Repository davon betroffen ist,
- ob eine Anwenderaktion erforderlich ist.

Der Agent darf Abschlussnaehe nicht mit Abschluss verwechseln. Wenn Commit, Push, manuelle Uebertragung oder Verarbeitung im Zielrepo noch fehlen, muss das ausdruecklich sichtbar bleiben.

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

## Rueckgabe an it-infrastruktur-registry

Eine Rueckgabe an die `it-infrastruktur-registry` soll vorgeschlagen werden, wenn eine Wissens-, Architektur- oder Governance-Erkenntnis lokale technische Infrastrukturfolgen haben kann.

Das IT-Infrastruktur-Repo bleibt dabei die lokale technische Primaerquelle. Die Rueckgabe darf keine sensiblen Details enthalten, sondern nur abstrahierte Hinweise, die der Anwender bewusst pruefen und manuell uebertragen kann.

Eine Rueckgabe soll insbesondere vorgeschlagen werden, wenn:

- eine Wissensentscheidung lokale Infrastrukturfolgen hat,
- eine Governance-Regel technische Umsetzung im IT-Infrastruktur-Repo erfordert,
- eine Wissensarchitekturentscheidung eine lokale Repo-, Backup-, Verschluesselungs- oder Zugriffsfrage ausloest,
- eine abstrakte Erkenntnis im IT-Infrastruktur-Repo als technische Entscheidung geprueft werden sollte,
- ein TheBrain-, Obsidian-, RAG- oder Agentensystem-Konzept technische Voraussetzungen im IT-Infrastruktur-Repo betrifft.

Die Rueckgabe ist immer nur ein Vorschlag. Der Agent darf nicht behaupten, dass die Rueckgabe erfolgt, verarbeitet, committed oder gepusht wurde, solange der Anwender dies nicht bestaetigt hat.

Beispiel:

```yaml
repo_rueckgabe:
  quelle_repo: "wissensarchitektur-registry"
  ziel_repo: "it-infrastruktur-registry"
  rueckgabetyp: "infrastrukturfolge_pruefen"
  sicherheitsstatus: "abstrahiert"
  ausloeser:
    wissenselement_id: null
    pfad: "OFFEN"
  rueckmeldung:
    titel: "OFFEN"
    beschreibung: "Eine abstrakte Wissens- oder Governance-Entscheidung koennte lokale Infrastrukturfolgen haben. Bitte im IT-Infrastruktur-Repo pruefen, ob daraus eine technische Entscheidung oder Aufgabe entsteht."
  status: "vorschlag"
  anwenderaktion_erforderlich: true
  automatische_uebertragung: false
```

## Uebergabe an human-system-interface-registry

Eine Uebergabe an die `human-system-interface-registry` soll vorgeschlagen werden, wenn eine Erkenntnis nicht primaer einzelnes Wissen, operative Aufgabe oder technische Infrastrukturentscheidung ist, sondern den Repo-Verbund, Schnittstellen oder Orchestrierungslogik betrifft.

Die `human-system-interface-registry` bleibt dabei menschnahe Interface- und Orchestrierungsschicht. Sie uebernimmt keine Wissenskanonisierung und richtet keine technische Synchronisation ein.

Eine Uebergabe soll insbesondere vorgeschlagen werden, wenn:

- ein neuer Repo-Verbund-Status entsteht,
- eine Orchestrierungsstufe aktualisiert werden sollte,
- eine Schnittstellenregel zwischen Repos relevant wird,
- eine Multi-Repo-Abfrage als Muster dokumentiert werden sollte,
- eine konsolidierte Antwortlogik betroffen ist,
- Sicherheitsgrenzen im Verbund aktualisiert werden sollten.

Keine Uebergabe an die `human-system-interface-registry` ist erforderlich, wenn:

- es nur um ein einzelnes Wissenselement geht,
- kein Verbund-, Schnittstellen- oder Orchestrierungsbezug besteht,
- der Inhalt besser ausschliesslich im Wissenskanon verbleibt.

Auch hier gilt: Die Uebergabe ist nur ein Vorschlag. Der Anwender bleibt manuelle Pruef-, Freigabe- und Uebertragungsschicht.

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

## Statuskette manueller Repo-Uebergaben

Manuelle Repo-Uebergaben durchlaufen im Pilotbetrieb mehrere klar getrennte Zustaende.

Die Statuskette lautet:

```text
erkannt -> vorgeschlagen -> manuell uebertragen -> im Zielrepo verarbeitet -> committed -> gepusht
```

Die einzelnen Zustaende bedeuten:

- `erkannt`: Der Agent hat moeglichen Uebergabebedarf festgestellt.
- `vorgeschlagen`: Der Agent hat einen Uebergabevorschlag formuliert.
- `manuell uebertragen`: Der Anwender hat den Vorschlag in das Zielrepo uebernommen oder die Uebernahme ausdruecklich bestaetigt.
- `im Zielrepo verarbeitet`: Das Zielrepo hat den uebertragenen Inhalt nach seiner eigenen Logik aufgenommen, geprueft oder weiterverarbeitet.
- `committed`: Die relevante Aenderung wurde im betroffenen Repository committed.
- `gepusht`: Der Commit wurde in das entfernte Repository gepusht.

Kein Zustand darf vorweggenommen werden. Insbesondere gilt:

- Aus `erkannt` folgt nicht automatisch `vorgeschlagen`.
- Aus `vorgeschlagen` folgt nicht automatisch `manuell uebertragen`.
- Aus `manuell uebertragen` folgt nicht automatisch `im Zielrepo verarbeitet`.
- Aus `committed` folgt nicht automatisch `gepusht`.

Der Agent soll in Berichten und Uebergabehinweisen den hoechsten sicher belegten Zustand nennen und offen markieren, welche naechsten Schritte noch fehlen.

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

### Beispiel 3: Kollegiale Abschlussnaehe

Tobias, wir sind hier ziemlich nah am sauberen Abschluss: Die Regel ist formuliert und im Wissensrepo dokumentiert. Offen sind nur noch die bewusste Pruefung durch dich und danach, falls du sie uebernehmen willst, Commit und Push. Die Uebergabe an ein anderes Repo ist damit noch nicht erfolgt.

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
