# architecture.md — Smart Apps Student Demo

_Stand: 26.06.2026_

## Architekturstatus

Noch kein finaler Implementierungsstack. Diese Datei beschreibt eine einfache Zielarchitektur fuer Unterrichtszwecke. Die konkrete Umsetzung darf je nach Kursformat variieren.

## Kernfluss

```text
Lehrende / Studierende
  -> laden oder bearbeiten fiktive Beispieldaten
  -> waehlen eine Managementfrage
  -> pruefen Dashboard, Berechnung und KI-Vorschlag

Smart App
  -> normalisiert Produkte, Verkaeufe, Bestand, Schichten und Aktionen
  -> berechnet Kennzahlen und einfache Regeln
  -> zeigt Abweichungen, Risiken und Vorschlaege
  -> erzeugt optional eine kurze Management-Zusammenfassung

Studierende
  -> vergleichen Ergebnis mit eigener betriebswirtschaftlicher Bewertung
  -> passen Annahmen, Regeln oder UI an
  -> dokumentieren Learnings im Backlog oder Result
```

## Fachliche Entitaeten

| Entitaet | Zweck | Wichtige Felder |
|---|---|---|
| Produkt | Sortiment des fiktiven Campus-Cafes | Name, Kategorie, Verkaufspreis, Wareneinsatz, Mindestbestand |
| Verkauf | Tages- oder Bon-Daten | Datum, Produkt, Menge, Umsatz, Kanal |
| Bestand | Lagerstand und Nachbestellung | Produkt, Bestand, Mindestbestand, Lieferzeit, Lieferant |
| Lieferant | einfache Einkaufsquelle | Name, Produktgruppe, Mindestbestellwert, Lieferzeit |
| Schicht | Personaleinsatz im Cafe | Datum, Zeitraum, Rolle, geplante Stunden |
| Aktion | Marketing- oder Preisexperiment | Name, Zeitraum, Produkt, Rabatt, Ziel |
| Empfehlung | System- oder KI-Vorschlag | Typ, Begruendung, Datenbasis, Status |

## Integrationen

### CSV/JSON

Beispieldaten sollen leicht als CSV oder JSON importierbar sein. Fuer den Einstieg reichen statische Dateien oder lokale Seed-Daten.

### KI-Assistenz

KI kann Managementfragen beantworten, Zusammenfassungen formulieren oder erklaeren, warum eine Kennzahl auffaellig ist. Berechnungen sollen trotzdem im Code nachvollziehbar bleiben.

### Export

Ein einfacher CSV-, Markdown- oder PDF-Export reicht fuer Unterrichtsergebnisse, z.B. eine Wochenanalyse oder Aktionsauswertung.

## Nichtfunktionale Anforderungen

- **Nachvollziehbarkeit:** Formeln, Annahmen und Datenquellen muessen sichtbar oder leicht erklaerbar sein.
- **Lernbarkeit:** Code und UI sollen klein genug bleiben, damit Studierende Aenderungen verstehen.
- **Fehlertoleranz:** Fehlende oder unplausible Daten sollen angezeigt statt still ignoriert werden.
- **Datenschutz:** Nur fiktive Daten verwenden; keine echten Studierenden-, Kunden- oder Unternehmensdaten.
- **Erweiterbarkeit:** Neue Uebungen sollen durch weitere Beispieldaten oder Feature-IDs ergaenzt werden koennen.

## Offene Architekturentscheidungen

- Frontend-Framework oder statisches HTML.
- Lokale Seed-Daten vs. kleine Datenbank.
- Art der KI-Integration: Prompt-only, API-Call oder Mock fuer Offline-Unterricht.
- Exportformat fuer Unterrichtsergebnisse.
- Umfang automatisierter Tests.

Siehe `docs/decisions.md` fuer angenommene Entscheidungen.
