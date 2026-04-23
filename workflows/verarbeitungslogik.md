# Verarbeitungslogik

Die Wissensarchitektur trennt bewusst zwischen Wissensextraktion, Registry-Veränderung und tatsächlicher Umsetzung in TheBrain. Diese Trennung ist notwendig, damit Rohwissen, bestätigtes Strukturwissen und operative Zielsystempflege nicht vermischt werden.

## 1. Wissensextraktion

Die Wissensextraktion verarbeitet Chats als Eingabe und erzeugt daraus strukturierte Wissenselemente. In dieser Phase entstehen noch keine verbindlichen Registeränderungen. Ziel ist es, aus Rohkommunikation belastbare Arbeitseinheiten für die weitere Prüfung abzuleiten.

## 2. Registry-Veränderung

Eine Registry-Veränderung findet erst statt, wenn Domänenzuordnung, Registerabgleich und bei Bedarf semantische oder Governance-Prüfungen abgeschlossen sind. Erst dann werden kanonische Knoten, Beziehungen, Quellen, Logs oder Verlaufsdateien aktualisiert.

Die Registry ist damit die bestätigte Wissensbasis und nicht die Ablage für ungesicherte Zwischenstände.

## 3. Umsetzung in TheBrain

TheBrain ist ein eigenes Zielsystem mit eigener Umsetzungsebene. Aus bestätigten Registry-Änderungen werden dort ableitbare Knoten-, Beziehungs- oder Etikettenänderungen vorbereitet, aber nicht automatisch als erledigt betrachtet.

Jedes TheBrain-Update erhält daher einen eigenen Umsetzungsstatus, zum Beispiel:

- `vorbereitet`
- `zur_prüfung`
- `freigegeben`
- `umgesetzt`
- `zurückgestellt`

So bleibt jederzeit nachvollziehbar, ob eine Änderung nur fachlich vorbereitet, bereits freigegeben oder tatsächlich im Zielsystem umgesetzt wurde.

## Konsequenz für die Praxis

Ein Chat kann also vollständig extrahiert und fachlich eingeordnet sein, ohne dass bereits eine Registry-Datei geändert wurde. Ebenso kann eine Registry-Änderung bestätigt vorliegen, obwohl die Umsetzung in TheBrain noch aussteht. Genau diese Trennung macht die Wissensarchitektur revisionsfähig und kontrollierbar.
