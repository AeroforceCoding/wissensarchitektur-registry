# Wissensarchitektur-Registry

Dieses Repository bildet die zentrale, versionierte Wissensarchitektur für die Extraktion, Domänenzuordnung, Klassifikation, semantische Prüfung und strukturierte Weiterverarbeitung von Chatinhalten. Es dient als gemeinsamer Referenzpunkt für Regeln, Register, Prompts, Vorlagen und nachvollziehbare Änderungen, damit Wissen über verschiedene Themenräume hinweg konsistent erfasst und weiterentwickelt werden kann.

## Zweck und Zielbild

Ziel ist eine belastbare Steuerungsschicht zwischen eingehenden Chatinhalten und ihrer strukturierten Verarbeitung. Aus einzelnen Aussagen, Entscheidungen, Anforderungen und offenen Punkten sollen wiederverwendbare Wissenselemente entstehen, die:

- einer fachlich passenden Domäne zugeordnet werden,
- gegen bestehende Register und kanonische Knoten abgeglichen werden,
- semantisch konsistent weiterentwickelt werden,
- Dubletten und widersprüchliche Strukturentwicklung vermeiden,
- als vorbereitete Änderungen für TheBrain nachvollziehbar bereitstehen.

Das Repository ist damit kein operatives Fachsystem, sondern das versionierte Regel- und Registry-System, das die Qualität und Nachvollziehbarkeit der Wissenspflege absichert.

## Rolle von GitHub, Codex und TheBrain

### GitHub

GitHub ist der versionierte Speicher- und Prüfkontext für diese Architektur. Hier werden Regeln, Register, Vorlagen, Änderungen und Reviews dokumentiert. Pull Requests, Merge-Prüfungen und Changelogs sorgen dafür, dass fachliche und strukturelle Entwicklung nachvollziehbar bleibt.

### Codex

Codex unterstützt die operative Verarbeitung von Chatinhalten anhand der hier hinterlegten Prompts, Regeln und Register. Dazu gehören insbesondere Extraktion, Domänenzuordnung, Registry-Abgleich, semantische Prüfung, Vorbereitung von Governance-Entscheidungen und die strukturierte Aufbereitung von Änderungsentwürfen.

### TheBrain

TheBrain ist das Zielsystem für die spätere Wissensdarstellung und Beziehungspflege. Dieses Repository führt keine direkte Wissensvisualisierung aus, sondern bereitet TheBrain-Änderungen so vor, dass Knoten, Beziehungen, Etiketten und Strukturentscheidungen kontrolliert und konsistent umgesetzt werden können.

## Globale Steuerung und domänenspezifische Bereiche

Die globale Ebene enthält die allgemeinen Steuerungsregeln der Wissensarchitektur. Dazu gehören Typen, Etiketten, Beziehungstypen, Routingregeln, Domänenregister und Klassifikationslogik. Diese Inhalte gelten domänenübergreifend und schaffen eine gemeinsame Sprache.

Die domänenspezifischen Bereiche enthalten dagegen die fachliche Ausprägung einzelner Themenräume. Dort liegen kanonische Knoten, domänenspezifische Beziehungen, semantische Zuordnungen, Quellen, Verlaufsänderungen, Klassifikationsentscheidungen und vorbereitete TheBrain-Updates. So bleibt die globale Steuerung stabil, während sich Fachdomänen unabhängig weiterentwickeln können.

## Operative Prompt-Reihenfolge

Die Prompts in `prompts/` bilden eine logische Verarbeitungskette:

1. `chat_extraktion.md`
   Extrahiert aus einem Chat die relevanten Wissenselemente, Aussagen, Entscheidungen, Prüfbedarfe und offenen Punkte.
2. `domänen_zuordnung.md`
   Ordnet die extrahierten Wissenselemente einer bestehenden Domäne oder einem begründeten neuen Domänenkandidaten zu.
3. `registry_abgleich.md`
   Prüft innerhalb der Ziel-Domäne, ob bereits passende kanonische Knoten, Beziehungen oder Registereinträge existieren.
4. `semantische_prüfung.md`
   Wird nur dann genutzt, wenn Bedeutungsnähe, Mehrdeutigkeit, Dublettengefahr oder mögliche Widersprüche vorliegen.
5. `governance_entscheidung.md`
   Wird nur dann aufgerufen, wenn eine echte Strukturänderung, ein neuer Standard oder eine konfliktträchtige Einordnung entschieden werden muss.
6. `registry_aktualisieren.md`
   Überführt bestätigte Ergebnisse in konkrete Registry-Änderungen.
7. `thebrain_update_vorbereiten.md`
   Formuliert daraus umsetzbare, aber noch getrennt nachverfolgbare Änderungen für TheBrain.

## Nutzen des Repositories

Der Nutzen dieser Registry liegt in drei Kernwirkungen:

- Konsistenz: Gleiche Inhalte werden nicht mehrfach und nicht widersprüchlich aufgebaut.
- Nachvollziehbarkeit: Entscheidungen, Änderungen und semantische Entwicklungen bleiben über Git nachvollziehbar.
- Skalierbarkeit: Neue Domänen, Regeln und Fachräume können ergänzt werden, ohne die Gesamtlogik der Wissensarchitektur zu verlieren.

## Grundsatz für die Pflege

Neue Inhalte sollten zuerst als strukturierte Extrakte oder Kandidaten erfasst, dann domänenspezifisch geprüft und erst nach bestätigter Einordnung in Register oder vorbereitete TheBrain-Updates übernommen werden. Dadurch bleibt die Wissensarchitektur lernfähig, aber kontrolliert.
