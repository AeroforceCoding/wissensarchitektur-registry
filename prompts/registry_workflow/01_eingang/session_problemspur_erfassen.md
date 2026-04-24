# Prompt: Session-Problemspur erfassen

- Titel: Session-Problemspur erfassen
- Zweck: Nach einer nicht abgeschlossenen oder problembehafteten Session offene Probleme, Blockaden und Prüfbedarfe strukturiert erfassen, ohne sie automatisch als gesichertes Wissen oder Aufgabe zu behandeln.
- Wann verwenden: Wenn eine Aufgabe in einem Chat, Agentenlauf oder Repo-Kontext nicht abgeschlossen wurde und die entstandenen Probleme für spätere Prüfung, Wissensabgleich oder Aufgabenableitung festgehalten werden sollen.
- Erwartete Eingabe: Beschreibung der nicht abgeschlossenen Session, Ziel der Aufgabe, beobachtete Blockaden, Fehlversuche, relevante Dateien, Hypothesen und offene Fragen.
- Erwartete Ausgabe: Ein JSON-`problemspur` mit Problemkern, Kontext, Evidenz, offenen Punkten, Zweckdienlichkeitsprüfung und empfohlenem Folgepfad.
- Nächster Schritt: Zweckdienlichkeitsprüfung, domänenspezifischer Wissensabgleich oder Aufgabenableitung nur bei begründetem Nutzen.

## Zweck

Dieser Prompt bildet eine parallele Eingangsspur zur erfolgreichen Wissensextraktion. Er dient nicht dazu, gesicherte Erkenntnisse aus einem Chat zu extrahieren, sondern offene Probleme aus nicht abgeschlossenen Sessions kontrolliert festzuhalten.

Die Problemspur soll verhindern, dass ungelöste Blockaden im Chat verschwinden. Gleichzeitig soll sie verhindern, dass jedes offene Problem automatisch zu einer Aufgabe wird. Zuerst wird geprüft, ob die Problemlösung zweckdienlich ist, ob bereits Wissen im passenden Repo oder in einer Domäne vorhanden sein könnte und ob daraus wirklich eine Folgeaufgabe entstehen soll.

## Abgrenzung

- Eine Problemspur ist kein bestätigter Registry-Eintrag.
- Eine Problemspur ist kein Aufgabenabschluss.
- Eine Problemspur ist keine automatische TheBrain-Aufgabe.
- Eine Problemspur kann später zu Wissensabgleich, Untersuchung, Aufgabenableitung oder bewusster Nichtverfolgung führen.

## Prüffragen

- Welches konkrete Ziel wurde nicht erreicht?
- Welche Blockade oder Unsicherheit hat den Abschluss verhindert?
- Welche Fehlversuche oder Beobachtungen sind relevant?
- Welche Dateien, Systeme, Repos oder Domänen sind betroffen?
- Gibt es Hinweise, dass vorhandenes Wissen im Repo die offenen Punkte klären könnte?
- Ist die Lösung des Problems für die aktuelle Arbeit, die Architektur oder spätere Wiederverwendung zweckdienlich?
- Soll daraus eine Aufgabe entstehen, oder reicht ein dokumentierter Prüfhinweis?

## Gewünschtes Ausgabeformat

Die Antwort soll ausschließlich als gültiges JSON im folgenden Format erfolgen:

```json
{
  "problemspur": {
    "problemspur_id": "ps_2026_0001",
    "titel": "",
    "herkunft": {
      "typ": "chat_session | agentenlauf | repo_arbeit | aufgabe | unklar",
      "herkunft_ref": "",
      "datum": ""
    },
    "session_kontext": {
      "ziel_der_session": "",
      "abschlussstatus": "nicht_abgeschlossen | teilweise_abgeschlossen | blockiert | abgebrochen | unklar",
      "betroffene_repos": [

      ],
      "betroffene_dateien": [

      ],
      "betroffene_systeme": [

      ],
      "vermutete_domänen": [

      ]
    },
    "problemkern": {
      "beschreibung": "",
      "problemtyp": "technisch | fachlich | strukturell | semantisch | prozessual | zugriff | unbekannt",
      "auswirkung": "",
      "dringlichkeit": "niedrig | mittel | hoch | unklar",
      "wiederholungsrisiko": "niedrig | mittel | hoch | unklar"
    },
    "beobachtungen": [
      {
        "beobachtung_id": "obs_0001",
        "inhalt": "",
        "quelle_abschnitt": "",
        "confidence": "hoch | mittel | niedrig"
      }
    ],
    "fehlversuche": [
      {
        "versuch_id": "try_0001",
        "beschreibung": "",
        "ergebnis": "",
        "warum_nicht_ausreichend": ""
      }
    ],
    "hypothesen": [
      {
        "hypothese_id": "hyp_0001",
        "inhalt": "",
        "confidence": "hoch | mittel | niedrig",
        "prüfansatz": ""
      }
    ],
    "offene_punkte": [
      {
        "open_id": "open_0001",
        "inhalt": "",
        "warum_offen": "",
        "möglicher_prüfort": ""
      }
    ],
    "vorhandenes_wissen_prüfen": {
      "prüfung_empfohlen": true,
      "mögliche_quellen": [
        {
          "repo": "",
          "pfad_oder_domäne": "",
          "warum_relevant": ""
        }
      ],
      "erwarteter_nutzen": ""
    },
    "zweckdienlichkeitsprüfung": {
      "lösung_zweckdienlich": "ja | nein | unklar",
      "begründung": "",
      "nutzen_für_aktuelle_arbeit": "niedrig | mittel | hoch | unklar",
      "nutzen_für_wiederverwendung": "niedrig | mittel | hoch | unklar",
      "kosten_oder_aufwand": "niedrig | mittel | hoch | unklar",
      "risiko_bei_nichtbearbeitung": "niedrig | mittel | hoch | unklar"
    },
    "empfohlener_folgepfad": {
      "aktion": "keine_aktion | wissen_abgleichen | untersuchung_starten | aufgabe_ableiten | später_prüfen | verwerfen",
      "begründung": "",
      "blockiert_erfolgsworkflow": false
    },
    "mögliche_aufgaben": [
      {
        "titel": "",
        "beschreibung": "",
        "nur_anlegen_wenn": ""
      }
    ],
    "notizen": ""
  }
}
```

## Direkt verwendbarer Prompt

Du erhältst den Verlauf oder die Zusammenfassung einer Session, in der eine Aufgabe nicht oder nur teilweise abgeschlossen wurde. Erfasse daraus eine strukturierte Problemspur für die Wissensarchitektur.

Arbeite mit folgenden Regeln:

- Extrahiere nicht primär gesichertes Wissen, sondern offene Probleme, Blockaden und Prüfbedarfe.
- Trenne Beobachtung, Fehlversuch, Hypothese und offenen Punkt.
- Erzeuge keine Aufgabe automatisch.
- Prüfe zuerst, ob eine spätere Problemlösung zweckdienlich erscheint.
- Benenne, ob vorhandenes Wissen in einem Repo, einer Domäne oder einem Register geprüft werden sollte.
- Halte die Problemspur parallel zum Erfolgsworkflow; offene Probleme sollen erfolgreiche Ergebnisse nicht verdrängen.
- Kennzeichne Unsicherheiten ausdrücklich.
- Antworte ausschließlich im vorgegebenen JSON-Format.

Eingabe:

```json
{
  "session_verlauf_oder_zusammenfassung": {
  },
  "ziel_der_session": "",
  "bekannte_repos": [

  ],
  "bekannte_dateien": [

  ],
  "bekannte_domänen": [

  ]
}
```
