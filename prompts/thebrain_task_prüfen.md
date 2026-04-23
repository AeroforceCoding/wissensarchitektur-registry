# Prompt: THEBRAIN_TASK prüfen

## Zweck

Dieser Prompt prüft einen neuen THEBRAIN_TASK gegen das bestehende TheBrain-Aufgabenregister und bewertet, ob die Aufgabe bereits vorhanden, nur ähnlich, ergänzend oder tatsächlich neu ist.

## Eingabe

Erwartet werden:

- ein neuer strukturierter oder unstrukturierter THEBRAIN_TASK,
- das aktuelle `thebrain/aufgabenregister.yml`,
- optional bestehende Prüfungen aus `thebrain/zuordnungsprüfungen.yml`.

## Prüffragen

- Gibt es bereits einen Eintrag mit gleicher Bedeutung?
- Gibt es eine bestehende Aufgabe mit gleichem Kern, aber anderem Detaillierungsgrad?
- Ist die neue Aufgabe nur ergänzend zu einem bestehenden Eintrag?
- Liegt lediglich eine teilweise Überschneidung vor?
- Welche Zuordnung oder Folgeaktion ist fachlich am sinnvollsten?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges YAML im folgenden Format erfolgen:

```yaml
task_prüfung:
  eingangs_task_ref: neuer_task_oder_extern
  bewertung: ähnlich
  bereits_vorhanden: false
  ähnliche_einträge:
    - task_ref: tb_task_0001
      ähnlichkeitstyp: gleicher_kern_mehr_detail
      begründung: Die bestehende Aufgabe deckt den Kern bereits ab, der neue Task ergänzt nur Details.
      confidence: mittel
  empfohlene_zuordnung:
    aktion: bestehende_aufgabe_erweitern
    ziel_task_ref: tb_task_0001
    begründung: Neue Informationen passen als Ergänzung zum bestehenden Eintrag.
```

## Direkt verwendbarer Prompt

Du erhältst einen neuen THEBRAIN_TASK und das bestehende TheBrain-Aufgabenregister. Prüfe, ob die Aufgabe bereits vorhanden, nur ähnlich, ergänzend oder neu ist, und leite daraus eine belastbare Zuordnungsempfehlung ab.

Arbeite mit folgenden Regeln:

- Beurteile nicht nur den Wortlaut, sondern die fachliche Bedeutung.
- Verwende als `ähnlichkeitstyp` nur sinnvolle Werte wie `gleiche_bedeutung`, `gleicher_kern_mehr_detail`, `ergänzend`, `teilweise_überschneidung`, `möglicher_doppelter_task` oder `neue_aufgabe`.
- Markiere `bereits_vorhanden` nur dann mit `true`, wenn ein bestehender Eintrag den neuen Task inhaltlich bereits ausreichend abdeckt.
- Formuliere die empfohlene Zuordnung als konkrete Folgeaktion.
- Antworte ausschließlich im vorgegebenen YAML-Format.

Eingabe:

```yaml
neuer_task: {}
aufgabenregister: {}
zuordnungsprüfungen: {}
```
