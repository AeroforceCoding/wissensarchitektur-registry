---
name: reifegrad-analyse
description: Prüft den Reifegrad von Artefakten, Logiken, Dateien oder Architekturschichten innerhalb der Wissensarchitektur.
---

# Zweck
Ordnet Artefakte methodisch nach Reifestufe ein, damit Erwähnung, Struktur, Definition und operative Nutzbarkeit nicht verwechselt werden.

# Wann verwenden
- bei unklarem Reifegrad eines Prompts, Registers oder Workflow-Schritts
- bei Spannungen zwischen behauptetem Status und tatsächlichem Inhalt
- bei Analyseberichten mit Reifegradbewertung

# Prüffragen
- nur erwähnt oder strukturell greifbar?
- expliziter Inhalt oder nur Verweis?
- teilweise oder inhaltlich definiert?
- operativ nutzbar?
- geprüft oder freigegeben?

# Reifestufen
- erwähnt
- strukturell_vorgesehen
- teilweise_definiert
- inhaltlich_definiert
- operativ_nutzbar
- überprüft
- kanonisch_freigegeben

# Output
- Artefakt
- Reifestufe
- kurze Begründung
- Unsicherheit
- nächster sinnvoller Entwicklungsschritt

# Grenzen
Entscheidet nicht über Dubletten, Statuskonsistenz oder sofortige Umsetzung.
