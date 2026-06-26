# decisions.md — Architektur- und Produktentscheidungen

_Chronologisches Log aller relevanten Entscheidungen._

## 2026-06-26 — Campus Cafe Manager als Beispielprojekt nutzen

**Kontext:** BWL-Studierende brauchen ein kleines, greifbares Szenario mit bekannten Kennzahlen und klaren App-Funktionen.

### Entscheidung

Die Spec beschreibt den "Campus Cafe Manager": eine Smart App fuer Umsatzuebersicht, Bestandsplanung, Aktionsideen und einfache Schichtplanung in einem fiktiven Campus-Cafe.

### Alternativen verworfen

- Reines CRM-Beispiel: weniger geeignet fuer Bestands- und Deckungsbeitragslogik.
- Finanzportfolio-Beispiel: hoeheres Risiko falscher fachlicher Interpretation.
- Generischer Aufgabenplaner: zu wenig BWL-Bezug.

### Konsequenzen

- Die Beispieldaten enthalten Produkte, Verkaeufe, Bestaende, Lieferanten, Schichten und Aktionen.
- Features sollen immer einen erkennbaren Management- oder Controlling-Bezug haben.
- KI-Ausgaben werden als Vorschlaege behandelt und fachlich gegen Kennzahlen geprueft.

<!-- Vorlage fuer neue Entscheidungen:

## JJJJ-MM-TT — Titel

**Kontext:** Warum mussten wir entscheiden?

### Entscheidung
Was haben wir entschieden?

### Alternativen verworfen
- Option A: Warum nicht?

### Konsequenzen
- Positiv
- Negativ / Risiken

-->
