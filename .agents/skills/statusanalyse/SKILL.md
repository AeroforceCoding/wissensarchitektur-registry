---
name: statusanalyse
description: Prüft, ob Statuswerte, Reifestände oder Umsetzungsangaben mit dem beobachtbaren Repo-Zustand zusammenpassen.
---

# Zweck
Macht Spannungen zwischen behauptetem Status und tatsächlichem Inhalt sichtbar.

# Wann verwenden
- bei Statuswerten wie geplant, in Arbeit, operativ, geprüft, freigegeben
- bei unklarem Umsetzungsstand
- bei widersprüchlichen Statusaussagen

# Prüffragen
- wird der Status durch Repo-Inhalt gestützt?
- passt der Status zur Reifestufe?
- ist operative Nutzbarkeit behauptet, obwohl nur Struktur vorliegt?
- gibt es widersprüchliche Statusangaben?

# Output
- geprüfter Status
- konsistent / teilweise konsistent / fraglich / widersprüchlich
- kurze Begründung
- benannte Spannung
- vorsichtige Klärungsempfehlung

# Grenzen
Bewertet nicht fachliche Qualität, Dubletten oder Prompt-Explizitheit.
