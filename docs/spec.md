# spec.md — Campus Cafe Manager

_Fiktive Unterrichts-Spec fuer BWL-Studierende, die Smart Apps mit KI-Unterstuetzung bauen lernen._

## 1. Ausgangslage

Die Hochschule betreibt fuer ein Planspiel ein fiktives Campus-Cafe namens **Campus Cafe Lina**. Das Cafe verkauft Kaffee, Snacks und einfache Mittagsangebote. Die Studierenden sollen eine kleine Smart App bauen, die aus Beispieldaten betriebswirtschaftliche Entscheidungen vorbereitet.

Die App ist kein echtes Kassensystem. Sie ist ein Lernprojekt, das zeigt, wie man aus einer einfachen Spec, strukturierten Daten und KI-Unterstuetzung ein nutzbares Management-Tool entwickelt.

## 2. Lernziele

- Anforderungen aus einer Spec in konkrete Features uebersetzen.
- Ein kleines Datenmodell fuer Produkte, Verkaeufe, Bestand, Lieferanten, Schichten und Aktionen entwerfen.
- Kennzahlen wie Umsatz, Wareneinsatz, Rohertrag und Absatz berechnen.
- Einfache Regeln fuer Warnungen und Vorschlaege implementieren.
- KI sinnvoll nutzen: erklaeren, zusammenfassen, Hypothesen bilden, aber Berechnungen pruefbar halten.
- Ergebnisse kritisch interpretieren statt blind zu automatisieren.

## 3. Zielnutzer

| Rolle | Ziel | Typische Frage |
|---|---|---|
| Cafe-Leitung | Alltag steuern | Welche Produkte laufen gut, was muss nachbestellt werden? |
| Controlling-Studentin | Kennzahlen verstehen | Wie veraendert eine Aktion Umsatz und Rohertrag? |
| Marketing-Student | Aktion planen | Welches Produkt eignet sich fuer eine Rabattaktion? |
| Dozentin | Lernfortschritt pruefen | Ist die App fachlich nachvollziehbar und erweiterbar? |

## 4. MVP-Scope

### Muss

- Produkte mit Verkaufspreis, Wareneinsatz und Mindestbestand anzeigen.
- Wochenverkaeufe aus Beispieldaten auswerten.
- Umsatz, Absatz, Wareneinsatz und Rohertrag berechnen.
- Produkte mit niedrigem Bestand markieren.
- Eine kurze Management-Zusammenfassung erzeugen, die auf sichtbaren Zahlen basiert.

### Sollte

- Top- und Flop-Produkte anzeigen.
- Nachbestellvorschlaege mit Mindestbestand und Lieferzeit begruenden.
- Aktionsdaten mit normalen Verkaufstagen vergleichen.
- Datenfehler oder fehlende Werte sichtbar machen.

### Nicht im MVP

- Echtes Kassensystem.
- Zahlung, Rechnung, Buchhaltung oder Steuerlogik.
- Login-/Rechteverwaltung.
- Verarbeitung echter Personen-, Kunden- oder Unternehmensdaten.

## 5. Beispieldaten

Alle Daten sind fiktiv. Mengen und Preise sind bewusst klein gehalten, damit Studierende Ergebnisse manuell nachrechnen koennen.

### 5.1 Produkte

| product_id | name | category | sell_price_eur | unit_cost_eur | min_stock | current_stock | supplier_id |
|---|---|---|---:|---:|---:|---:|---|
| P-001 | Espresso | Kaffee | 2.20 | 0.42 | 80 | 140 | L-001 |
| P-002 | Cappuccino | Kaffee | 3.20 | 0.78 | 90 | 72 | L-001 |
| P-003 | Filterkaffee | Kaffee | 2.60 | 0.55 | 70 | 65 | L-001 |
| P-004 | Iced Latte | Kaffee | 3.80 | 1.05 | 50 | 34 | L-001 |
| P-005 | Buttercroissant | Backwaren | 2.40 | 0.95 | 45 | 28 | L-002 |
| P-006 | Veganes Banana Bread | Backwaren | 3.10 | 1.25 | 35 | 42 | L-002 |
| P-007 | Club Sandwich | Lunch | 5.90 | 2.70 | 30 | 18 | L-003 |
| P-008 | Falafel Wrap | Lunch | 5.40 | 2.35 | 30 | 26 | L-003 |
| P-009 | Apfelschorle | Getraenke | 2.30 | 0.82 | 60 | 55 | L-004 |
| P-010 | Wasser still | Getraenke | 1.80 | 0.45 | 80 | 96 | L-004 |

### 5.2 Lieferanten

| supplier_id | name | product_group | lead_time_days | min_order_value_eur |
|---|---|---|---:|---:|
| L-001 | Roesterei Nord | Kaffee | 3 | 120 |
| L-002 | Campus Baeckerei | Backwaren | 1 | 40 |
| L-003 | FreshBox GmbH | Lunch | 2 | 90 |
| L-004 | Getraenke Schulz | Getraenke | 4 | 80 |

### 5.3 Wochenverkaeufe

| date | weekday | product_id | units_sold | channel | promo_id |
|---|---|---|---:|---|---|
| 2026-04-20 | Montag | P-001 | 38 | Theke | - |
| 2026-04-20 | Montag | P-002 | 44 | Theke | - |
| 2026-04-20 | Montag | P-005 | 31 | Theke | - |
| 2026-04-20 | Montag | P-007 | 21 | Theke | - |
| 2026-04-20 | Montag | P-010 | 26 | Theke | - |
| 2026-04-21 | Dienstag | P-001 | 41 | Theke | - |
| 2026-04-21 | Dienstag | P-002 | 48 | Theke | - |
| 2026-04-21 | Dienstag | P-006 | 24 | Theke | - |
| 2026-04-21 | Dienstag | P-008 | 27 | Theke | - |
| 2026-04-21 | Dienstag | P-009 | 33 | Theke | - |
| 2026-04-22 | Mittwoch | P-003 | 36 | Theke | - |
| 2026-04-22 | Mittwoch | P-004 | 29 | Theke | A-001 |
| 2026-04-22 | Mittwoch | P-005 | 34 | Theke | - |
| 2026-04-22 | Mittwoch | P-007 | 24 | Theke | - |
| 2026-04-22 | Mittwoch | P-010 | 31 | Theke | - |
| 2026-04-23 | Donnerstag | P-001 | 45 | Theke | - |
| 2026-04-23 | Donnerstag | P-002 | 53 | Theke | - |
| 2026-04-23 | Donnerstag | P-004 | 37 | Theke | A-001 |
| 2026-04-23 | Donnerstag | P-008 | 32 | Theke | - |
| 2026-04-23 | Donnerstag | P-009 | 39 | Theke | - |
| 2026-04-24 | Freitag | P-001 | 49 | Theke | - |
| 2026-04-24 | Freitag | P-002 | 57 | Theke | - |
| 2026-04-24 | Freitag | P-004 | 43 | Theke | A-001 |
| 2026-04-24 | Freitag | P-006 | 28 | Theke | - |
| 2026-04-24 | Freitag | P-007 | 29 | Theke | - |
| 2026-04-24 | Freitag | P-010 | 35 | Theke | - |

### 5.4 Aktionen

| promo_id | name | product_id | start_date | end_date | discount_percent | goal |
|---|---|---|---|---|---:|---|
| A-001 | Iced Latte Fruehlingsaktion | P-004 | 2026-04-22 | 2026-04-24 | 15 | Nachfrage fuer kalte Kaffeegetraenke testen |
| A-002 | Lunch Bundle Test | P-007 | 2026-04-27 | 2026-04-30 | 10 | Mittagsumsatz steigern |

### 5.5 Schichten

| date | shift | start | end | planned_staff | notes |
|---|---|---|---|---:|---|
| 2026-04-20 | Morgen | 08:00 | 12:00 | 2 | normale Vorlesungswoche |
| 2026-04-20 | Mittag | 12:00 | 15:00 | 2 | Lunch-Peak erwartet |
| 2026-04-21 | Morgen | 08:00 | 12:00 | 2 | normale Vorlesungswoche |
| 2026-04-21 | Mittag | 12:00 | 15:00 | 2 | Lunch-Peak erwartet |
| 2026-04-22 | Morgen | 08:00 | 12:00 | 2 | Start Iced-Latte-Aktion |
| 2026-04-22 | Mittag | 12:00 | 15:00 | 2 | Aktion beobachten |
| 2026-04-23 | Morgen | 08:00 | 12:00 | 2 | hohe Nachfrage moeglich |
| 2026-04-23 | Mittag | 12:00 | 15:00 | 3 | zusaetzliche Person eingeplant |
| 2026-04-24 | Morgen | 08:00 | 12:00 | 2 | Freitag |
| 2026-04-24 | Mittag | 12:00 | 15:00 | 3 | Freitag + Aktion |

## 6. Beispiel-Kennzahlen

Die App soll mindestens diese Kennzahlen berechnen koennen:

| Kennzahl | Formel |
|---|---|
| Umsatz | `units_sold * sell_price_eur` |
| Wareneinsatz | `units_sold * unit_cost_eur` |
| Rohertrag | `Umsatz - Wareneinsatz` |
| Rohertragsquote | `Rohertrag / Umsatz` |
| Absatz | Summe `units_sold` |
| Bestandsreichweite grob | `current_stock / durchschnittlicher Tagesabsatz` |
| Nachbestellbedarf | `max(0, min_stock - current_stock)` |

Hinweis fuer Aktionen: Bei Rabattaktionen kann der rabattierte Preis genutzt werden. Beispiel: `sell_price_eur * (1 - discount_percent / 100)`.

## 7. Beispiel-Fragen fuer die App

- Welche drei Produkte haben in der Woche den hoechsten Umsatz erzielt?
- Welche Produkte liegen unter Mindestbestand?
- Wie hoch ist der gesamte Rohertrag der Woche?
- Hat die Iced-Latte-Aktion den Absatz sichtbar erhoeht?
- Welches Produkt sollte zuerst nachbestellt werden und warum?
- Welche Empfehlung wuerde die App der Cafe-Leitung fuer die naechste Woche geben?

## 8. Akzeptanzkriterien MVP

- Die App kann die Produkt- und Verkaufsdaten aus der Spec oder aus Seed-Dateien laden.
- Fuer jedes Produkt werden Umsatz, Absatz, Wareneinsatz und Rohertrag korrekt berechnet.
- Mindestens eine Wochenuebersicht zeigt Gesamtsummen und Top-Produkte.
- Produkte unter Mindestbestand werden klar markiert.
- Die Management-Zusammenfassung nennt konkrete Zahlen aus der Berechnung.
- KI-Text darf keine Kennzahlen erfinden, die nicht aus Daten oder Berechnungen stammen.
- Die App bleibt mit den Beispieldaten ohne externen Dienst vorfuehrbar; KI kann bei Bedarf gemockt werden.

## 9. Uebungsaufgaben fuer Studierende

1. Datenmodell skizzieren: Welche Tabellen oder Objekte braucht die App?
2. Kennzahlen implementieren und mit zwei Produkten manuell pruefen.
3. Eine Bestandswarnung bauen: `current_stock < min_stock`.
4. Eine einfache Dashboard-Ansicht entwerfen.
5. Einen Prompt fuer eine Management-Zusammenfassung formulieren.
6. Den KI-Output gegen die berechneten Zahlen validieren.
7. Eine neue Aktion ergaenzen und simulieren, wie sich Absatz oder Rohertrag veraendern koennte.

## 10. Erweiterungsideen

- CSV-Import fuer eigene Sortimente.
- Diagramm fuer Umsatz nach Wochentag.
- Ampellogik fuer Bestand: gruen, gelb, rot.
- Was-waere-wenn-Rechner fuer Preis- und Kostenveraenderungen.
- Automatische Erklaerung von Ausreissern.
- Export eines Wochenberichts als Markdown oder PDF.
