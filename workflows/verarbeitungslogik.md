# Verarbeitungslogik

Die Wissensarchitektur trennt bewusst zwischen Wissensextraktion, Registry-Veränderung und tatsächlicher Umsetzung in TheBrain. Diese Trennung ist notwendig, damit Rohwissen, bestätigtes Strukturwissen und operative Zielsystempflege nicht vermischt werden.

## 1. Wissensextraktion

Die Wissensextraktion verarbeitet Chats als Eingabe und erzeugt daraus strukturierte Wissenselemente. In dieser Phase entstehen noch keine verbindlichen Registeränderungen. Ziel ist es, aus Rohkommunikation belastbare Arbeitseinheiten für die weitere Prüfung abzuleiten.

Bei aufgabenbasierten Arbeitsverläufen entsteht zusätzlich eine vorgelagerte Evidenzebene: Screenshots, Bilddateien und andere Nachweise werden zunächst benannt, mit Kontext versehen und als Artefakte referenziert. Erst nach erfolgreichem Aufgabenabschluss werden sie in einen validierten Informationsblock überführt.

## 2. Registry-Veränderung

Eine Registry-Veränderung findet erst statt, wenn Domänenzuordnung, Registerabgleich und bei Bedarf semantische oder Governance-Prüfungen abgeschlossen sind. Erst dann werden kanonische Knoten, Beziehungen, Quellen, Logs oder Verlaufsdateien aktualisiert.

Die Registry ist damit die bestätigte Wissensbasis und nicht die Ablage für ungesicherte Zwischenstände.

Ein validierter Informationsblock bildet dabei den Übergabepunkt zwischen laufender Aufgabe und regulärer Registry-Verarbeitung. Je nach Lage folgt auf ihn als nächster Schritt die Domänen-Zuordnung oder direkt der Registry-Abgleich.

## 3. Umsetzung in TheBrain

TheBrain ist ein eigenes Zielsystem mit eigener Umsetzungsebene. Aus bestätigten Registry-Änderungen werden dort ableitbare Knoten-, Beziehungs- oder Etikettenänderungen vorbereitet, aber nicht automatisch als erledigt betrachtet.

Für explizite Arbeitsaufträge oder aus Chats abgeleitete THEBRAIN_TASK-Blöcke existiert zusätzlich eine eigene Aufgabenlogik unter `thebrain/`. Dort werden Ziel-Brains, Aufgabenstatus, Dublettenprüfungen und Umsetzungsprotokolle geführt, bevor oder während konkrete Änderungen in TheBrain nachverfolgt werden.

Jedes TheBrain-Update erhält daher einen eigenen Umsetzungsstatus, zum Beispiel:

- `vorbereitet`
- `zur_prüfung`
- `freigegeben`
- `umgesetzt`
- `zurückgestellt`

So bleibt jederzeit nachvollziehbar, ob eine Änderung nur fachlich vorbereitet, bereits freigegeben oder tatsächlich im Zielsystem umgesetzt wurde.

## Konsequenz für die Praxis

Ein Chat kann also vollständig extrahiert und fachlich eingeordnet sein, ohne dass bereits eine Registry-Datei geändert wurde. Ebenso kann eine Registry-Änderung bestätigt vorliegen, obwohl die Umsetzung in TheBrain noch aussteht. Genau diese Trennung macht die Wissensarchitektur revisionsfähig und kontrollierbar.

## 4. Agentisches Handeln

Der Agent soll mit hoher Autonomie arbeiten, aber nicht verdeckt. Reversible, nicht-destruktive Schritte wie Einordnung, Benennung, Metadatenableitung, Artefakt-Entwürfe oder Informationsblock-Entwürfe dürfen autonom vorbereitet werden. Strukturrelevante, destruktive oder extern wirksame Schritte werden dagegen nur nach ausdrücklicher Bestätigung ausgeführt.

Die konkrete Handlungslogik dafür ist in `global/agentische_funktionen.yml`, `global/bestätigungsregeln.yml` und `workflows/agentisches_handeln.md` beschrieben.
