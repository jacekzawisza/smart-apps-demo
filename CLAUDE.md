# CLAUDE.md — Smart Apps Student Demo

## Projekt

Dieses Repository ist ein neutrales Demo-Projekt fuer Smart-Apps-Unterricht. Zielgruppe sind BWL-Studierende, die mit KI-Unterstuetzung Programmieren, Produktdenken und einfache Datenlogik lernen sollen.

## Was bauen wir?

Die zentrale fachliche Quelle ist `docs/spec.md`. Sie beschreibt ein fiktives Beispielprojekt: den "Campus Cafe Manager", eine kleine Smart App fuer Umsatzuebersicht, Bestandsplanung, Preis-/Aktionsideen und einfache Schichtplanung.

## Deadline

Keine feste Lieferdeadline dokumentiert. Das Projekt dient als Unterrichtsmaterial und kann je nach Kursumfang vereinfacht oder erweitert werden.

## Tech-Stack + Standards

Lies `docs/architecture.md`, bevor du Code oder Architektur aenderst. Der Stack ist bewusst offen, damit Studierende verschiedene KI-gestuetzte Umsetzungen vergleichen koennen.

## Architektur-Entscheidungen

Lies `docs/decisions.md` vor Architektur- oder Produktentscheidungen und aktualisiere es nach relevanten Entscheidungen.

## Arbeitsweise

Lies `docs/modus-operandi.md`. Dieses Projekt ist als SOLO-/Unterrichtsprojekt eingerichtet: kurze Artefakte, klare Feature-IDs, keine Team-Rituale.

## Kontextquellen

- `docs/spec.md` ist die Single Source of Truth fuer das Beispielprojekt.
- `docs/backlog.md` enthaelt Feature-Hypothesen und Uebungsaufgaben.
- `docs/architecture.md` beschreibt eine moegliche technische Zielstruktur.

## Coding-Prinzipien

**1. Think Before Coding.** Annahmen explizit machen. Bei Mehrdeutigkeit Interpretationen aufzeigen und, wenn die Entscheidung fachlich riskant ist, nachfragen.

**2. Teaching First.** Loesungen sollen nachvollziehbar sein. Keine unnötig komplexen Abstraktionen, wenn einfache Datenstrukturen fuer den Lernzweck reichen.

**3. Surgical Changes.** Nur betroffene Dateien anfassen. Kein Drive-by-Refactoring und keine ungefragten Framework-Wechsel.

**4. Goal-Driven Execution.** Vor groesseren Aenderungen Akzeptanzkriterien formulieren. Bei Bugs erst Reproduktion/Test, dann Fix.

## Projektkonventionen

- Produktsprache und Dokumentation: Deutsch.
- Feature-IDs: `SAD-001`, `SAD-002`, fortlaufend, nie wiederverwenden.
- Alle Beispieldaten sind fiktiv und duerfen keine echten Personen, Studierenden- oder Kundendaten enthalten.
- KI-Ergebnisse sind im Unterricht Assistenz und Diskussionsgrundlage, keine ungepruefte betriebswirtschaftliche Wahrheit.
- Jede Funktion soll einen klaren BWL-Bezug haben: Umsatz, Deckungsbeitrag, Bestand, Nachfrage, Preis, Personal oder Entscheidungsvorbereitung.

## Bekannte Fallen

- Zu viel Technik verdeckt den Lernzweck. Lieber kleine, testbare Workflows bauen.
- KI-generierte Analysen koennen plausibel klingen, aber falsche betriebswirtschaftliche Schluesse ziehen.
- Beispieldaten muessen konsistent sein, damit Studierende Fehler in Logik und Annahmen erkennen koennen.
- Automatisierung sollte immer erklaerbar bleiben: Eingabedaten, Berechnungsregel und Ergebnis muessen sichtbar sein.
