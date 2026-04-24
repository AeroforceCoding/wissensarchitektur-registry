# Anwenderanleitung Zum Aktuellen Systemstand

Stand: 2026-04-24

## Zweck Dieser Anleitung

Diese Anleitung beschreibt, wie ein Anwender nach aktuellem Stand mit der Wissensarchitektur-Registry arbeitet. Sie erklärt nicht die technische Innenarchitektur, sondern beantwortet die praktische Frage:

Was muss ich als Anwender tun, wenn aus einem Chat, einer Aufgabe, einem Problem oder einer Entscheidung Wissen für das System entstehen soll?

Das System ist aktuell keine vollautomatische Anwendung. Es ist eine strukturierte Wissensarchitektur im Repository, die durch Prompts, Regeln, Agentenrollen und Dokumentation gesteuert wird. Der Anwender bleibt an wichtigen Stellen die prüfende und entscheidende Instanz.

## Grundidee

Die Wissensarchitektur-Registry sammelt relevante Erkenntnisse aus Chats, Aufgaben, Problemen und Projektarbeit. Sie soll verhindern, dass wichtiges Wissen in langen Chatverläufen verschwindet.

Der Agent kann Inhalte analysieren, strukturieren, Vorschläge machen, Dateien vorbereiten und offene Punkte erkennen. Der Anwender liefert Kontext, bestätigt Richtungen, entscheidet bei Strukturwirkung und meldet externe Umsetzungen zurück.

## Schnellentscheidung: Was Liegt Vor?

Nutze diese Übersicht, um den passenden Einstieg zu wählen.

| Situation | Was der Anwender tut | Passender Systempfad |
| --- | --- | --- |
| Neuer oder kurzer Chat mit relevanten Erkenntnissen | Chatinhalt bereitstellen | Chat-Extraktion |
| Langer externer Chat | Im externen Chat Übergabeblock erzeugen lassen | Externer Übergabeblock, danach Chat-Extraktion |
| Abgeschlossene Aufgabe mit Ergebnis | Ergebnis und Nachweise bereitstellen | Aufgabenabschluss verdichten |
| Screenshot, Datei oder Nachweis | Artefakt benennen lassen und Kontext liefern | Artefakt-Metadaten erfassen |
| Nicht abgeschlossene Session oder Blockade | Ziel, Problem und Fehlversuche beschreiben | Problemspur erfassen |
| Neue Struktur, Domäne oder Standard vorgeschlagen | Entscheidung prüfen und freigeben oder ablehnen | Governance-Entscheidung |
| TheBrain soll angepasst werden | Vorbereitete Änderungen prüfen und Umsetzung zurückmelden | TheBrain-Update vorbereiten |

## Standardablauf Für Einen Chat

### 1. Eingang Bereitstellen

Der Anwender stellt den Chatinhalt oder einen kompakten Übergabeblock bereit.

Wenn der Chat kurz genug ist, kann der vollständige Inhalt direkt verarbeitet werden.

Wenn der Chat lang ist, soll der externe Chat zuerst einen Übergabeblock erzeugen. Dafür wird der Prompt `prompts/externe_anwendung/01_eingang/chat_uebergabeblock_erzeugen.md` verwendet.

Der Anwender achtet darauf:

- Der Chat oder Übergabeblock enthält den relevanten Kontext.
- Unsicherheiten werden nicht geglättet.
- TheBrain- oder Registry-Änderungen werden nicht als umgesetzt dargestellt, wenn sie nur besprochen wurden.

### 2. Chat-Extraktion Starten

Das System verarbeitet den Chat oder Übergabeblock mit `prompts/registry_workflow/01_eingang/chat_extraktion.md`.

Der Anwender muss hier nur eingreifen, wenn:

- der Kontext fehlt,
- das Thema nicht klar erkennbar ist,
- wichtige Aussagen falsch oder zu stark verkürzt wurden.

### 3. Domäne Bestätigen

Das System ordnet die extrahierten Inhalte einer Domäne zu, zum Beispiel:

- `m365_sharepoint`
- `hr_data_hub`
- `wissenssystem_thebrain`

Der Anwender muss handeln, wenn:

- mehrere Domänen ähnlich plausibel sind,
- keine bestehende Domäne richtig passt,
- eine neue Domäne vorgeschlagen wird.

Wichtig: Eine neue Domäne wird nicht automatisch angelegt. Sie braucht eine bewusste Entscheidung.

### 4. Registry-Abgleich Prüfen

Das System prüft, ob ein Wissenselement schon vorhanden ist oder ob es einen neuen Eintrag braucht.

Der Anwender muss handeln, wenn:

- eine Dublette möglich ist,
- unklar ist, ob ein bestehender Eintrag erweitert werden soll,
- ein neuer kanonischer Eintrag vorgeschlagen wird.

### 5. Semantische Prüfung Bei Unklarheit

Wenn die Bedeutung eines neuen Elements nicht eindeutig ist, wird eine semantische Prüfung genutzt.

Der Anwender muss handeln, wenn:

- zwei Begriffe ähnlich klingen, aber fachlich nicht dasselbe bedeuten,
- eine Zusammenführung vorgeschlagen wird,
- eine Abgrenzung fachlich bestätigt werden muss.

### 6. Governance Bei Strukturwirkung

Governance ist notwendig, wenn eine Änderung mehr ist als eine einfache Ergänzung.

Der Anwender muss entscheiden bei:

- neuer Domäne,
- neuem Standard,
- neuer kanonischer Struktur,
- Ersetzung oder Zusammenführung bestehender Einträge,
- Änderung an grundlegenden Regeln oder Namenslogiken.

Die mögliche Entscheidung lautet praktisch:

- freigeben,
- mit Auflagen freigeben,
- zurückstellen,
- blockieren.

### 7. Registry-Aktualisierung Prüfen

Erst nach Prüfung und Freigabe werden konkrete Änderungen an Registry-Dateien vorbereitet oder vorgenommen.

Der Anwender muss handeln, wenn:

- die Änderung strukturrelevant ist,
- die Evidenz nicht ausreichend ist,
- die vorgeschlagenen Dateiänderungen nicht dem beabsichtigten Wissensstand entsprechen.

### 8. TheBrain-Update Prüfen

TheBrain ist nicht die Primärquelle. TheBrain ist Ziel- und Navigationsschicht.

Das bedeutet:

- Die Registry führt den kanonischen Wissensstand.
- TheBrain kann später daraus Knoten, Beziehungen oder Navigationsstrukturen erhalten.
- Eine TheBrain-Änderung gilt nicht als umgesetzt, nur weil sie vorbereitet wurde.

Der Anwender muss handeln, wenn:

- eine vorbereitete TheBrain-Änderung tatsächlich umgesetzt werden soll,
- der Zielast in TheBrain unklar ist,
- der tatsächliche Umsetzungsstatus zurückgemeldet werden muss.

## Ablauf Bei Einer Nicht Abgeschlossenen Aufgabe

Wenn eine Aufgabe nicht abgeschlossen wurde, wird daraus nicht automatisch ein erfolgreicher Wissenseintrag.

Stattdessen wird eine Problemspur erstellt.

Der Anwender beschreibt:

- Was war das Ziel?
- Was wurde versucht?
- Was hat nicht funktioniert?
- Welche Dateien, Systeme oder Repos waren betroffen?
- Welche offenen Fragen bleiben?
- Soll das Problem weiterverfolgt werden?

Das System prüft dann:

- ob vorhandenes Wissen helfen könnte,
- ob eine Untersuchung sinnvoll ist,
- ob daraus eine Aufgabe entstehen sollte,
- ob bewusst keine Aktion notwendig ist.

Der Anwender muss besonders dann entscheiden, wenn ein Problem zwar sichtbar ist, aber nicht klar ist, ob seine Lösung aktuell zweckdienlich ist.

## Wann Muss Der Anwender Handeln?

### Eingang Bereitstellen

Der Anwender liefert Chat, Übergabeblock, Artefakt, Aufgabenabschluss oder Problemkontext.

Typische Formulierung:

> Bitte verarbeite diesen Chat für die Wissensarchitektur.

Oder:

> Erzeuge aus diesem langen Chat einen Übergabeblock für die Registry.

### Workflow-Richtung Bestätigen

Der Anwender entscheidet, welcher Pfad weiterverfolgt wird, wenn mehrere Möglichkeiten bestehen.

Typische Formulierung:

> Ordne das der Domäne `m365_sharepoint` zu und führe die alternative Domäne nur als Hinweis.

Oder:

> Behandle das nicht als abgeschlossene Erkenntnis, sondern als Problemspur.

### Strukturwirkung Freigeben

Der Anwender gibt Änderungen frei, die dauerhafte Bedeutung für die Wissensarchitektur haben.

Typische Formulierung:

> Ich gebe diese Strukturänderung frei.

Oder:

> Lege noch keine neue Domäne an. Führe das vorerst als Domänenkandidat.

### Evidenz Nachreichen

Der Anwender ergänzt fehlende Nachweise oder klärt offene Fragen.

Typische Formulierung:

> Der fehlende Nachweis ist dieser Screenshot.

Oder:

> Die Entscheidung wurde nur vorgeschlagen, nicht getroffen.

### Externe Umsetzung Bestätigen

Der Anwender meldet zurück, ob eine Aktion außerhalb der Registry umgesetzt wurde.

Typische Formulierung:

> Die TheBrain-Änderung wurde umgesetzt.

Oder:

> TheBrain wurde noch nicht angepasst. Status bleibt vorbereitet.

### Bewusste Nichtverfolgung Bestätigen

Der Anwender entscheidet, dass ein offenes Problem aktuell nicht weiterbearbeitet wird.

Typische Formulierung:

> Dieses Problem wird aktuell nicht weiterverfolgt, weil der Nutzen zu gering ist.

## Was Dokumentiert Werden Sollte

Wenn der Anwender handelt, sollte das System möglichst festhalten:

- Zeitpunkt,
- Handlungsart,
- Auslöser,
- Entscheidung oder Aktion,
- betroffene Dateien oder Systeme,
- Begründung,
- Folgestatus,
- Nachweis,
- offene Punkte.

Für einzelne Anwenderhandlungen gibt es die Vorlage `vorlagen/anwenderhandlung_vorlage.json`.

Später können mehrere solche Ereignisse als JSONL-Protokoll geführt werden. Daraus kann das System lernen, wo Anwender oft unsicher sind und wo bessere Anleitungen, Prompts oder Prüfregeln nötig werden.

## Was Das System Aktuell Kann

Das System kann nach aktuellem Stand:

- relevante Chatinhalte strukturieren,
- lange externe Chats über Übergabeblöcke vorbereiten,
- Domänen vorschlagen,
- Registry-Abgleich anstoßen,
- semantische Unklarheiten sichtbar machen,
- Governance-Bedarf erkennen,
- Registry-Änderungen vorbereiten,
- TheBrain-Updates vorbereiten,
- offene Problemspuren erfassen,
- Anwenderhandlungen klassifizieren,
- Agentenrollen und Rollenübergaben beschreiben.

## Was Das System Noch Nicht Ist

Das System ist aktuell noch nicht:

- eine fertige Webanwendung,
- ein automatisch laufendes Multi-Agent-System,
- eine Kubernetes- oder Docker-Orchestrierung,
- ein API-Server,
- eine automatische TheBrain-Synchronisierung,
- ein Ersatz für menschliche Freigabe.

Der aktuelle Reifegrad ist eine strukturierte, dokumentierte und erweiterbare Grundlage.

## Merksatz Für Anwender

Wenn etwas nur analysiert, sortiert oder vorbereitet wird, kann der Agent viel selbst tun.

Wenn etwas kanonisch, strukturwirksam, extern umgesetzt oder schwer rückgängig zu machen ist, muss der Anwender prüfen und entscheiden.

## Kurze Checkliste

Vor dem Start:

- Ist es ein Chat, eine Aufgabe, ein Artefakt oder ein Problem?
- Ist der Inhalt abgeschlossen oder noch offen?
- Gibt es Nachweise?
- Ist TheBrain nur erwähnt oder tatsächlich betroffen?

Während der Verarbeitung:

- Stimmen Domäne und Kontext?
- Ist etwas nur Hypothese oder schon Entscheidung?
- Gibt es Dublettengefahr?
- Ist eine Governance-Entscheidung nötig?

Vor Abschluss:

- Wurde nur vorbereitet oder tatsächlich geändert?
- Muss der Anwender noch etwas freigeben?
- Muss TheBrain noch manuell aktualisiert werden?
- Gibt es offene Punkte oder eine Problemspur?
