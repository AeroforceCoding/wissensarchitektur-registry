# Laufzeitumgebung

Dieser Bereich ist der spätere Andockpunkt für technische Laufzeitbeschreibungen der Wissensarchitektur.

Aktuell werden hier bewusst noch keine Docker-Compose-Dateien, Kubernetes-Manifeste oder Laufzeitprofile angelegt.

## Vorgesehene Rolle

Hier können später unter anderem entstehen:

- Docker-Compose-Konfigurationen,
- Kubernetes-Manifeste,
- Laufzeitprofile für lokale Dienste,
- `.env.example`-Dateien ohne Geheimnisse,
- Hinweise für Betrieb auf Synology NAS oder anderen lokalen Hosts,
- Profile für lokale LLMs, RAG-Komponenten oder Agentenprozesse.

## Formatregel

Docker Compose und Kubernetes verwenden YAML, weil sie technische Konfigurations- und Laufzeitbeschreibungen sind. Diese YAML-Dateien sind keine Registry-Daten und dürfen nicht mit JSON-Datenobjekten der Wissensarchitektur verwechselt werden.

## Grenze

Dieser Bereich beschreibt spätere Ausführung. Er enthält nicht das kanonische Wissen selbst.
