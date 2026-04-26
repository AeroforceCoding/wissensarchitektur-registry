# Repository-Schnittstellen

## Zweck

Diese Datei dokumentiert methodische Regeln fuer Schnittstellen zwischen der `wissensarchitektur-registry` und anderen Repositories. Sie legt keine Automatisierung, kein gemeinsames Zwischenregister und keine neue Schema-Architektur an.

Ziel ist, klare Grenzen zwischen kanonischer Wissensarchitektur, operativer Handlungslogik, Zielsystemen, Spiegeln und Agentengedächtnis zu halten.

## Grundsatz

Repository-Schnittstellen sind zuerst Bedeutungs- und Verantwortungsgrenzen.

Ein anderes Repository darf auf Wissenselemente der `wissensarchitektur-registry` verweisen, ohne diese Wissenselemente zu kopieren oder selbst kanonisch zu verwalten. Umgekehrt duerfen aus der Wissensarchitektur operative Folgeaufgaben entstehen, ohne dass diese Aufgaben dadurch selbst kanonisches Wissen werden.

## Begriffsklaerung

Folgende Entscheidungen gelten vorlaeufig:

- `Time-Intelligence-registry` wird vorerst nicht als eigenes Repository gefuehrt.
- Zeitintelligenz wird vorerst als Faehigkeit der `action-intelligence-registry` verstanden.
- Der technische Name dieses Repositories bleibt vorerst `wissensarchitektur-registry`.
- `Wissensmanagement` darf als fachlicher Oberbegriff verwendet werden, aber nicht als zweiter technischer Repo-Name.
- Als Kurzbezeichnung darf `Wissensregistry` verwendet werden.
- Wenn in anderen Repositories oder Dokumenten `wissensmanagement-registry` auftaucht, ist das vorerst als unscharfer fachlicher Begriff zu behandeln, nicht als bestaetigter Repo-Name.

## Schnittstelle zur action-intelligence-registry

Die `wissensarchitektur-registry` bleibt kanonische Primaerquelle fuer Wissen. Sie verwaltet Wissensdomaenen, Konzepte, Quellen, semantische Beziehungen, Registry-Regeln, Architekturentscheidungen, dauerhaft relevante Erkenntnisse und die Verarbeitungsschritte der Wissensarchitektur.

Die `action-intelligence-registry` bleibt operative Primaerquelle fuer Aufgaben, Projekte, naechste Handlungen, Abhaengigkeiten, Sequenzen und Zeitlogik.

Fuer die Schnittstelle gelten diese Regeln:

- Wissensbezuege sind Referenzen, keine Kopien.
- Die Wissensregistry darf operative Folgeaufgaben ausloesen, aber diese Folgeaufgaben sind nicht automatisch kanonisches Wissen.
- Aufgabenabschluss in der `action-intelligence-registry` ist keine Wissensfreigabe in der `wissensarchitektur-registry`.
- Eine Aufgabe kann auf ein Wissenselement verweisen, ohne dieses Wissenselement zu veraendern.
- Ein Wissenselement kann eine Folgeaufgabe erzeugen, ohne selbst eine Aufgabe zu werden.
- Agentengedaechtnis bleibt methodischer Arbeitskontext, nicht kanonische Wahrheit.
- Zielsysteme und Spiegel wie TheBrain, Obsidian, OmniFocus, Kalender oder GitHub-Spiegelungen sind keine Ersatz-Primaerquellen.

## Schnittstelle zur it-infrastruktur-registry

Die `it-infrastruktur-registry` ist lokale technische Primaerquelle fuer IT-Infrastruktur. Sie hat eine andere Sicherheitsstufe als die `wissensarchitektur-registry`.

Die `wissensarchitektur-registry` darf nur abstrahierte, freigegebene und nicht-sensitive Wissensanteile aus dem IT-Infrastruktur-Repo aufnehmen.

Fuer die Schnittstelle gelten diese Regeln:

- Die `wissensarchitektur-registry` darf keine konkreten technischen Infrastrukturdetails kanonisieren.
- Die `wissensarchitektur-registry` darf den technischen Ist-Zustand des IT-Infrastruktur-Repos nicht ersetzen.
- Sicherheitsgrenzen des IT-Infrastruktur-Repos haben Vorrang vor Wissensaufnahme.
- Sensible Infrastrukturdetails duerfen nicht unkontrolliert in andere Repositories uebertragen werden.
- Eine Uebernahme in die Wissensregistry setzt bewusste Freigabe und Abstraktion durch den Anwender voraus.
- Das IT-Infrastruktur-Repo bleibt fuer lokale Infrastrukturentscheidungen, technische Konfigurationen und sicherheitsrelevante Details zustaendig.

### Zulaessige Wissensuebernahmen aus IT-Infrastruktur

Aus der `it-infrastruktur-registry` duerfen in die `wissensarchitektur-registry` nur nicht-sensitive, abstrahierte und freigegebene Inhalte uebernommen werden.

Zulaessig sind insbesondere:

- allgemeine Architekturprinzipien,
- abstrakte Sicherheitsprinzipien,
- nicht-sensitive Governance-Erkenntnisse,
- Begriffe oder Modelle,
- abstrakte Zusammenhaenge zwischen Infrastruktur und Wissensarchitektur,
- nicht-sensitive Lernnotizen,
- generische Erkenntnisse zu lokaler Wissensinfrastruktur,
- allgemeine Muster fuer lokale Repos, Agentensysteme oder spaetere RAG-/REX-Schichten.

Nicht uebernommen werden duerfen:

- Zugangsdaten,
- Tokens,
- Passwoerter,
- private Schluessel,
- interne IP-Adressen,
- vollstaendige VLAN-Plaene,
- Firewall-Regeln,
- Portfreigaben,
- VPN-Konfigurationen,
- sensible NAS-Pfade,
- Benutzer- und Rechtekonzepte mit echten Details,
- Angriffsflachen,
- Sicherheitsluecken im Detail,
- konkrete Netzwerk- oder Expositionsinformationen.

## Schnittstelle zur human-system-interface-registry

Die `human-system-interface-registry` ist menschnahe Interface- und Orchestrierungsschicht fuer den Repo-Verbund. Sie dokumentiert Rollen, Schnittstellen, Sicherheitsgrenzen, Uebergaben, Orchestrierungsstufen, spaetere Multi-Repo-Abfragen und konsolidierte Antwortlogik.

Sie ist keine Wissensdatenbank, kein Aufgabenmanager, keine IT-Dokumentation und keine technische Synchronisationsinstanz.

Fuer die Schnittstelle gelten diese Regeln:

- Die `human-system-interface-registry` ersetzt nicht die `wissensarchitektur-registry`.
- Sie darf keine Wissenskanonisierung uebernehmen.
- Sie darf keine Wissenselemente als kanonisch setzen.
- Die `wissensarchitektur-registry` bleibt Primaerquelle fuer Wissenselemente, Konzepte, Quellen, semantische Beziehungen und Governance-Entscheidungen.
- Uebergaben von oder zur `human-system-interface-registry` bleiben manuell und anwendergeprueft.
- Die `human-system-interface-registry` darf Orchestrierungsstufen beschreiben, aber keine Automatisierung oder Synchronisation als vorhanden behaupten, solange diese nicht freigegeben und implementiert ist.

## Abstrahierte Governance-Erkenntnis: Synchronisierungsschicht nicht freigegeben

Status: vorlaeufige, nicht-sensitive Governance-/Architekturerkenntnis aus dem `it-infrastruktur-registry`.

Kernaussage:

Die IT-Reifegradanalyse ergibt, dass automatische Synchronisierung, Docker-Orchestrierung, automatische Commits, automatischer Push und Remote-Zugriff aktuell nicht freigegeben sind. Fuer den Repo-Verbund bleibt manuelle Uebergabe die aktive Pilotstufe.

Eine lokale, rein lesende Multi-Repo-Abfrage ist nur als spaetere Zielstufe denkbar und erfordert vorher Schutzklassenfreigabe, Freigabematrix, Backup-/Restore-Minimum, Log-/Auditformat, Read-only-Pfadbegrenzung und Sicherheitskonzept.

Folgende Punkte sind aktuell nicht freigegeben:

- Docker-Orchestrierung fuer Repo-Synchronisation,
- automatische Synchronisation,
- automatische Commits,
- automatischer Push,
- schreibende lokale Aenderungen durch Dienste,
- Zugriff von unterwegs auf eine Orchestrierungsschicht.

Maximal als spaetere Zielstufe denkbar:

- lokale, rein lesende Multi-Repo-Abfrage,
- eng begrenzte Pfade,
- keine Schreibrechte,
- kein Commit,
- kein Push,
- keine externe Erreichbarkeit,
- keine Ausgabe sensibler Details.

Reifegradbewertung:

- Artefakt: Synchronisierungs- und Orchestrierungsschicht im Repo-Verbund.
- Reifestufe: `strukturell_vorgesehen`.
- Begruendung: Die Idee ist als spaetere Zielstufe benannt und mit Schutzbedingungen versehen, aber nicht freigegeben, nicht umgesetzt und nicht operativ nutzbar.
- Unsicherheit: gering fuer den aktuellen Nicht-Freigabestatus; mittel fuer konkrete spaetere Ausgestaltung, weil diese bewusst offen bleibt.
- Naechster sinnvoller Entwicklungsschritt: nicht bauen, nur vorbereiten; bei Bedarf Schutzklassen, Freigabematrix, Audit-/Logformat und Read-only-Grenzen als abstrakte Anforderungen klaeren.

## Minimales Referenzmodell

Fuer Verweise von operativen Aufgaben auf Wissenselemente reicht zunaechst ein schlankes Referenzmodell. Dieses Modell ist ein Beispiel fuer eine moegliche Struktur, kein produktives Schema und keine Automatisierung.

```yaml
wissensbezug:
  wissenselement_id: null
  wissensquelle_repo: "wissensarchitektur-registry"
  wissensquelle_pfad: "OFFEN"
  bezugstyp: "begruendet_auf"
  kurzbeschreibung_des_bezugs: "Diese operative Aufgabe leitet sich aus einer offenen Architekturspannung ab."
  referenzstatus: "vermutet"
  letzte_pruefung: null
  beispiel: true
```

### Feldbedeutung

- `wissenselement_id`: Optionale stabile ID eines Wissenselements, falls eine solche ID im Wissensrepo bereits existiert oder bewusst vergeben wurde.
- `wissensquelle_repo`: Repository, in dem die kanonische Wissensquelle liegt.
- `wissensquelle_pfad`: Relativer Pfad zur kanonischen Datei oder zum naechsten belegbaren Wissensartefakt.
- `bezugstyp`: Art des Bezugs zwischen operativem Objekt und Wissenselement.
- `kurzbeschreibung_des_bezugs`: Kurze menschlich lesbare Begruendung des Bezugs.
- `referenzstatus`: Status der Referenz, nicht Status des Wissenselements und nicht Status der Aufgabe.
- `letzte_pruefung`: Datum der letzten bewussten Pruefung oder `null`, wenn noch keine Pruefung erfolgt ist.
- `beispiel`: Kennzeichnet Beispielobjekte, damit sie nicht als produktive Referenz missverstanden werden.

### Vorlaeufige Bezugstypen

- `begruendet_auf`
- `betrifft`
- `setzt_um`
- `prueft`
- `erzeugt_folgeaufgabe`
- `klaerungsbedarf_zu`

### Vorlaeufige Referenzstatus

- `vermutet`
- `geprueft`
- `stabil`
- `veraltet`
- `unklar`

## Grenzen

Diese Datei fuehrt keine technische Synchronisation ein.

Sie begruendet kein gemeinsames Zwischenregister, keine neue Intake-Registry und keine Kopie operativer Aufgaben in der `wissensarchitektur-registry`.

Eine weitergehende Schema- oder Automatisierungsentscheidung darf erst vorbereitet werden, wenn einfache Referenzen wiederholt nicht mehr ausreichen und diese Spannung im Repository belegbar ist.
