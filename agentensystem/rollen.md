# Agentenrollen

## Zweck

Diese Datei erklärt die Rollenlogik des agentischen Systems der Wissensarchitektur-Registry. Die maschinenlesbare Rollenübersicht liegt in `agentensystem/regelwerk/agentenrollen.yml`.

Das Agentensystem ist aktuell eine strukturierte Grundlage für spätere Orchestrierung. Es gibt noch keine produktive Laufzeit, keine dauerhaft laufenden Agenten, keine Kubernetes-Konfiguration, keinen API-Server und keine automatische Multi-Agent-Steuerung.

## Rollenübersicht

Das System unterscheidet sechs grundlegende Rollen:

1. Analyse-Agent
2. Architektur-Agent
3. Umsetzungs-Agent
4. Prüf-Agent
5. Dokumentations-Agent
6. Freigabe-/Kontroll-Agent

Diese Rollen sind bewusst getrennt, damit Analyse, Architekturprüfung, Umsetzung, Qualitätssicherung, Dokumentation und Kontrolle nicht in einer unklaren Agentenhandlung vermischt werden.

## Zusammenspiel

Die fachliche Systemlogik folgt dieser Reihenfolge:

```text
Analyse-Agent
→ Architektur-Agent
→ Umsetzungs-Agent
→ Prüf-Agent
→ Dokumentations-Agent
→ Freigabe-/Kontroll-Agent
```

Diese Reihenfolge ist noch keine technische Orchestrierung. Sie beschreibt, wie spätere Agenten zusammenarbeiten sollen und welche Übergaben zwischen Rollen vorgesehen sind.

Die standardisierten Übergabe- und Ergebnisformate sind in `agentensystem/regelwerk/agenten_uebergabeformate.yml` definiert. Sie legen fest, welche Felder ein Rollenoutput mindestens enthalten soll, damit eine nachgelagerte Rolle ihn ohne Kontextverlust weiterverarbeiten kann.

## Übergabeformate

Jede Rolle erzeugt ein eigenes Ergebnisformat:

- Analyse-Agent: `analyse_ergebnis`
- Architektur-Agent: `architektur_ergebnis`
- Umsetzungs-Agent: `umsetzung_ergebnis`
- Prüf-Agent: `pruefung_ergebnis`
- Dokumentations-Agent: `dokumentation_ergebnis`
- Freigabe-/Kontroll-Agent: `freigabe_kontroll_ergebnis`

Diese Formate sind Steuerungsdefinitionen. Sie sind noch keine produktiven Nachrichtenqueues, API-Verträge oder automatischen Agentenaufrufe.

## Kontrollprinzip

Der Umsetzungs-Agent darf keine konzeptionellen Grundentscheidungen eigenmächtig treffen. Strukturrelevante, destruktive oder schwer revidierbare Änderungen benötigen eine menschliche Prüfung.

Der Freigabe-/Kontroll-Agent ersetzt keine menschliche Entscheidung. Er gibt nur eine Freigabeempfehlung aus:

- `approved_for_review`
- `needs_human_review`
- `blocked`

Dadurch bleibt klar getrennt:

- Vorschlag
- Umsetzung im erlaubten Scope
- Prüfung
- Dokumentation
- menschliche Freigabe

## Grenze Zur Laufzeit

Diese Rollenbeschreibung bereitet spätere Multi-Agent-Systeme vor, etwa lokale Agenten, Kubernetes-basierte Dauerprozesse oder RAG-gestützte Assistenzsysteme. Sie behauptet aber nicht, dass solche Systeme bereits laufen.

Solange keine Laufzeit-Orchestrierung implementiert ist, sind die Rollen eine Architektur- und Steuerungsgrundlage für Menschen, Codex-Sitzungen und spätere Automatisierung.

## Offene Punkte

- Es gibt noch keine technischen Agentenprozesse.
- Es gibt noch keine automatische Übergabe zwischen Rollen.
- Es gibt noch keine Laufzeitentscheidung für Kubernetes, Docker Compose oder lokale Dienste.

Diese offenen Punkte sind beabsichtigt und gehören zu späteren Ausbaustufen.
