---
name: prompt-explizitheitspruefung
description: Prüft, ob ein Prompt oder eine Workflow-Logik tatsächlich explizit vorliegt oder nur referenziert wird.
---

# Zweck
Verhindert, dass erwähnte Promptnamen mit operativ vorhandenen Promptinhalten verwechselt werden.

# Wann verwenden
- bei genannten Promptnamen
- bei geplanter Promptbibliothek
- wenn unklar ist, ob Volltext oder nur Struktur existiert

# Prüffragen
- existiert eine konkrete Datei?
- liegt echter Promptinhalt vor?
- nur Dateiname, Index oder Referenz?
- vollständig ausformuliert oder nur angekündigt?

# Output
- geprüfter Prompt
- explizit vorhanden / teilweise explizit / nur referenziert / offen
- Fundstellen
- Lücke oder Folgebedarf

# Grenzen
Bewertet nicht fachliche Qualität, Reife des Gesamtsystems oder Dubletten.
