# Automatisierung

Dieser Bereich ist der spätere Andockpunkt für Validierung, Transformation, Import, Export und technische Verarbeitung der Wissensarchitektur.

Aktuell werden hier bewusst noch keine Skripte angelegt.

## Vorgesehene Rolle

Hier können später unter anderem entstehen:

- JSON- und JSONL-Validierung,
- Schema-Prüfungen,
- Formatmigrationen,
- Exporte in Zielsysteme,
- Importe von Chat-Extraktionspaketen,
- RAG-Index-Erzeugung,
- lokale LLM- und Agenten-Orchestrierung.

## Sprachentscheidung

Python ist die bevorzugte Standardsprache für Automatisierung in diesem Repository, weil die erwarteten Aufgaben vor allem Datenverarbeitung, Validierung, lokale LLM-/RAG-Anbindung und agentische Hintergrundprozesse betreffen.

JavaScript oder TypeScript kann später ergänzend sinnvoll sein, wenn Weboberflächen, Browsernähe oder Zielsystem-SDKs dies nahelegen.

## Grenze

Automatisierungscode darf Registry-Daten verarbeiten, soll aber nicht selbst zur kanonischen Wissensquelle werden.
