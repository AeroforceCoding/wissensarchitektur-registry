# Statuswerte

## Zweck

Diese Datei hält methodisch fest, dass Statuswerte in der Wissensarchitektur und im Agentensystem getrennt nach Schicht und Funktion betrachtet werden müssen.

## Grundsatz

Statuswerte unterschiedlicher Schichten dürfen nicht vermischt werden.

## Aktuell relevante Statusräume

- Aufgabenstatus
  Referenz: `global/aufgaben_statuswerte.yml`
- TheBrain-Umsetzungsstatus
  Referenz: `global/thebrain_statuswerte.yml`
- Artefaktstatus
  Referenz: `global/artefakt_statuswerte.yml`
- Reifegradstatus
  Referenz: `agentensystem/regelwerk/reifegrade.md`
- Arbeitsfluss im Agentensystem
  Referenz: `agentensystem/gedaechtnis/letzter_stand.md`

## Methodischer Hinweis

Ein beobachtbarer Status ist nur dann belastbar, wenn er durch den tatsächlichen Repo-Inhalt oder durch explizit dokumentierte Evidenz gestützt wird.

## Regel für den Arbeitsfluss im Agentensystem

Im `letzter_stand.md` wird der aktuelle Arbeitsfluss in diesen Bereichen geführt:

- `Backlog`
- `Naechste_Schritte`
- `In_Arbeit`
- `Abgeschlossen`

Für `Abgeschlossen` gilt ausdrücklich:

- `Abgeschlossen` ist Quelle möglicher Übernahme.
- `Abgeschlossen` bedeutet nicht automatisch bestätigte Erkenntnis.
- Eine Übernahme in `agentensystem/gedaechtnis/bestaetigte_erkenntnisse.md` erfolgt nur nach bewusster Prüfung und bei wiederverwendbarem Erkenntniswert.
