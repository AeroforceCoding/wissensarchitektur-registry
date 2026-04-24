# Systemsimulation Und Anwenderhandlungen

## Zweck

Diese Dokumentation beschreibt den aktuellen Stand der Wissensarchitektur-Registry anhand einer simulierten Verarbeitung eines neuen Eintrags. Sie zeigt, welche Schritte das System bereits vorbereiten kann, wann Agentenrollen sinnvoll zusammenspielen und an welchen Stellen der Anwender nach aktuellem Kenntnisstand handeln oder entscheiden muss.

Die Datei ist als menschlich lesbare Referenz gedacht. Sie kann später als Grundlage für eine TheBrain-Navigationssicht dienen. Die kanonische Primärquelle bleibt das Repository.

## Simulierter Eingang

Beispiel:

Ein externer Arbeitschat enthält die Erkenntnis, dass SharePoint-Berechtigungsentscheidungen nicht nur technisch, sondern als Teil einer Informationsarchitektur dokumentiert werden sollten. Im Chat wurde außerdem entschieden, dass unklare Berechtigungsmodelle nicht direkt in TheBrain umgesetzt werden, sondern zuerst über die Registry geprüft werden sollen.

Dieser Beispielinhalt ist kein echter Registry-Eintrag. Er dient nur zur Simulation des Ablaufs.

## Ablauf Der Verarbeitung

### 1. Eingang klären

Wenn der vollständige Chat kopierbar ist, startet der Workflow mit `prompts/registry_workflow/01_eingang/chat_extraktion.md`.

Wenn der Chat zu lang oder bereits weit fortgeschritten ist, erzeugt der Anwender im externen Chat zuerst einen Übergabeblock mit `prompts/externe_anwendung/01_eingang/chat_uebergabeblock_erzeugen.md`. Dieser Übergabeblock wird anschließend intern mit der Chat-Extraktion verarbeitet.

Systemhandlung:

- passenden Eingangspfad vorschlagen
- Chat oder Übergabeblock in `chat_extrakt` überführen
- Aussagen, Entscheidungen, offene Punkte, Aufgabenhinweise und TheBrain-Hinweise trennen

Anwenderhandlung:

- Chatinhalt oder Übergabeblock bereitstellen
- bei langen Chats den externen Übergabeblock erzeugen lassen
- fehlenden Kontext ergänzen, wenn der Agent den Schwerpunkt nicht belastbar erkennt

### 2. Domäne zuordnen

Der extrahierte Inhalt wird mit `prompts/registry_workflow/02_zuordnung/domänen_zuordnung.md` gegen das Domänenregister geprüft.

Im Beispiel wäre `m365_sharepoint` wahrscheinlich die führende Domäne. `wissenssystem_thebrain` wäre nur randständig betroffen, weil TheBrain als Ziel- und Navigationsschicht erwähnt wird.

Systemhandlung:

- führende Domäne vorschlagen
- alternative Domänen benennen
- Unsicherheit und Domänenkandidaten markieren

Anwenderhandlung:

- bei unsicherer Zuordnung Richtung bestätigen
- neue Domäne nicht automatisch zulassen
- fehlende fachliche Hinweise nachreichen, falls mehrere Domänen gleich plausibel sind

### 3. Registry-Abgleich durchführen

Mit `prompts/registry_workflow/03_pruefung/registry_abgleich.md` wird geprüft, ob das neue Wissenselement bereits durch vorhandene Knoten, Beziehungen oder Zuordnungen abgedeckt ist.

Systemhandlung:

- vorhandene Treffer suchen
- Dublettengefahr markieren
- Folgeaktion vorschlagen, etwa bestehenden Knoten ergänzen oder neuen Knoten vorbereiten

Anwenderhandlung:

- bei unklarer Trefferlage fachlichen Kontext klären
- entscheiden helfen, ob ein bestehender Eintrag erweitert oder eine neue Struktur vorbereitet werden soll

### 4. Semantische Prüfung bei Bedarf

Wenn Bedeutungsnähe, Dublettengefahr oder Abgrenzung unklar sind, folgt `prompts/registry_workflow/03_pruefung/semantische_prüfung.md`.

Systemhandlung:

- Bedeutungsnähe prüfen
- Abgrenzung, Zusammenführung, Ergänzung oder Ablehnung empfehlen
- Governance-Bedarf markieren

Anwenderhandlung:

- bei fachlicher Mehrdeutigkeit die beabsichtigte Bedeutung klären
- entscheiden, ob eine vorgeschlagene Abgrenzung zweckdienlich ist

### 5. Governance-Entscheidung bei Strukturwirkung

Wenn eine neue kanonische Struktur, ein neuer Standard, eine neue Domäne oder eine konfliktträchtige Änderung betroffen ist, folgt `prompts/registry_workflow/04_entscheidung/governance_entscheidung.md`.

Systemhandlung:

- Entscheidungsgegenstand formulieren
- betroffene Bereiche und Risiken benennen
- Auflagen und Wirksamkeit vorschlagen

Anwenderhandlung:

- Strukturwirkung freigeben, zurückstellen oder blockieren
- Auflagen bestätigen
- neue Domänen, Standards oder Zusammenführungen ausdrücklich entscheiden

### 6. Registry-Aktualisierung vorbereiten oder ausführen

Mit `prompts/registry_workflow/05_aktualisierung/registry_aktualisieren.md` werden bestätigte Ergebnisse in konkrete Dateiänderungen übersetzt.

Systemhandlung:

- betroffene Dateien und Aktionen benennen
- Änderungsentwurf erstellen
- Verlaufs- und Dokumentationshinweise vorbereiten

Anwenderhandlung:

- bei strukturrelevanten Änderungen Freigabe erteilen
- bei unsicherer Evidenz zusätzliche Nachweise liefern
- prüfen, ob die vorgeschlagene Änderung den beabsichtigten Wissensstand trifft

### 7. TheBrain-Update vorbereiten

Erst nach bestätigter Registry-Aktualisierung kann `prompts/registry_workflow/06_thebrain/thebrain_update_vorbereiten.md` eine TheBrain-Änderung vorbereiten.

Systemhandlung:

- mögliche Knoten, Beziehungen, Etiketten oder Zieläste vorbereiten
- TheBrain-Status als vorbereitet, nicht als umgesetzt führen
- manuelle Prüfpunkte benennen

Anwenderhandlung:

- TheBrain-Umsetzung manuell prüfen oder durchführen
- tatsächlichen Umsetzungsstatus zurückmelden
- Abweichungen zwischen Registry und Zielsystem dokumentieren

## Paralleler Problemfall

Wenn der Beispielchat nicht zu einem abgeschlossenen Ergebnis geführt hätte, würde nicht der Erfolgsworkflow erzwungen. Stattdessen wird mit `prompts/registry_workflow/01_eingang/session_problemspur_erfassen.md` eine Problemspur erstellt.

Systemhandlung:

- Problemkern, Fehlversuche, Hypothesen und offene Punkte trennen
- Zweckdienlichkeit der Problemlösung bewerten
- Folgepfad vorschlagen: Wissen abgleichen, Untersuchung starten, Aufgabe ableiten, später prüfen oder keine Aktion

Anwenderhandlung:

- Ziel der nicht abgeschlossenen Session erklären
- entscheiden, ob das Problem weiterverfolgt werden soll
- fehlende Evidenz oder betroffene Dateien nachreichen
- bewusste Nichtverfolgung bestätigen, wenn der Nutzen zu gering ist

## Zusammenspiel Der Agentenrollen

Die aktuelle Rollenlogik ist in `agentensystem/regelwerk/agentenrollen.yml` und `agentensystem/regelwerk/agenten_uebergabeformate.yml` beschrieben.

Für die Simulation ergibt sich diese Arbeitsteilung:

```text
Analyse-Agent
→ Architektur-Agent
→ Umsetzungs-Agent
→ Prüf-Agent
→ Dokumentations-Agent
→ Freigabe-/Kontroll-Agent
```

Der Analyse-Agent erkennt Befunde, Inkonsistenzen und offene Punkte. Der Architektur-Agent prüft Schichten, Domänen, Formatlogik und Strukturwirkung. Der Umsetzungs-Agent darf nur im erlaubten Scope ändern. Der Prüf-Agent prüft Formate, Pflichtfelder und Verweise. Der Dokumentations-Agent macht Zweck, Kontext und Auswirkungen nachvollziehbar. Der Freigabe-/Kontroll-Agent markiert menschlichen Prüfbedarf, ersetzt aber keine menschliche Entscheidung.

## Situationen Mit Anwenderhandlung

Nach aktuellem Stand ist Anwenderhandlung besonders in diesen Situationen erforderlich:

- Eingang bereitstellen: Chat, Übergabeblock, Artefakt, Aufgabenabschluss oder Problemkontext liefern.
- Workflow-Richtung bestätigen: wenn mehrere plausible Folgepfade unterschiedliche Konsequenzen hätten.
- Strukturwirkung freigeben: bei neuen Domänen, Standards, kanonischen Strukturen, Zusammenführungen oder Ersetzungen.
- Evidenz nachreichen: wenn Aufgabenerfolg, Quelle oder fachlicher Kontext nicht belastbar genug ist.
- Externe Umsetzung bestätigen: wenn TheBrain, Dateisysteme oder andere Zielsysteme betroffen sind.
- Nichtverfolgung bestätigen: wenn ein offenes Problem bewusst nicht weiterbearbeitet werden soll.

Die maschinenlesbare Definition dieser Handlungsarten liegt in `agentensystem/regelwerk/anwenderhandlungen.yml`.

## Dokumentation Von Anwenderhandlungen

Anwenderhandlungen sollten künftig als fortlaufende Ereignisse dokumentiert werden, bevorzugt in JSONL. Das passt zur Formatlogik, weil es sich um wiederholbare, maschinenlesbare Ereignisse handelt.

Eine einzelne Ereignisvorlage liegt in `vorlagen/anwenderhandlung_vorlage.json`. Für ein späteres Protokoll könnten mehrere solche Objekte zeilenweise als JSONL geführt werden.

Ein späteres Ereignisobjekt sollte mindestens festhalten:

- Zeitpunkt
- Handlungsart
- Auslöser
- Entscheidung oder Aktion
- betroffene Dateien oder Systeme
- Begründung
- Folgestatus
- Nachweis
- offene Punkte

Diese Daten können später genutzt werden, um bessere Anwenderanleitungen zu erzeugen. Wiederkehrende Klärungen zeigen, wo Prompts, Übergabeformate, Rollen oder Dokumentation verbessert werden sollten.

## Reifegrad Und Status

Gesicherter Befund:

- Der Standardworkflow ist dokumentiert.
- Externe Übergabeblöcke sind vorgesehen.
- Problemspuren sind als paralleler Pfad vorgesehen.
- Agentenrollen und Rollenübergaben sind maschinenlesbar definiert.
- Anwenderhandlungen sind jetzt als eigene Regeldatei beschrieben.

Reifegrad:

- Workflow und Rollenlogik: `inhaltlich_definiert`
- Übergabeformate: `inhaltlich_definiert`
- Anwenderhandlungslogik: `inhaltlich_definiert`
- Produktive Automatisierung: `nicht_implementiert`
- Laufende Multi-Agent-Orchestrierung: `nicht_implementiert`

Statusspannung:

Das System ist als Struktur- und Steuerungsgrundlage weit genug vorbereitet, um kontrolliert erweitert zu werden. Es ist aber noch kein automatisch laufendes Wissensmanagementsystem. Menschliche Eingabe, Freigabe und externe Umsetzung bleiben im aktuellen Stand zentrale Kontrollpunkte.

## TheBrain-Übergabe

Für TheBrain kann diese Dokumentation später als Navigationsstruktur verwendet werden:

- Zweck der Wissensarchitektur
- Eingangspfade
- Workflowphasen
- Agentenrollen
- Anwenderhandlungen
- Problemspur
- Freigabe- und Kontrollpunkte
- TheBrain als Ziel- und Navigationsschicht

Dabei gilt weiterhin: TheBrain visualisiert und navigiert die Wissensarchitektur, ersetzt aber nicht die Registry als Primärquelle.
