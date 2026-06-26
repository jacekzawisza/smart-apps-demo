# Modus Operandi — Smart Apps Student Demo

_Projektspezifische SOLO-/Unterrichtsversion nach `github.com/jacekzawisza/modus-operandi`, eingerichtet am 26.06.2026._

## Setup

Dieses Projekt wird als kompaktes Unterrichtsprojekt gefuehrt. Es gibt eine projektverantwortliche Person, keine Team-Mission-Dokumente und keine `INBOX.md`. Ziel ist ein klarer Arbeitsmodus fuer AI-gestuetzte Iteration.

## Artefakte

| Datei / Ordner | Zweck | Pflege |
|---|---|---|
| `CLAUDE.md` | Kurzes AI-Briefing fuer Claude | selten, bei Grundsatzwechseln |
| `AGENTS.md` | Kurzes AI-Briefing fuer Codex/Agenten | selten, bei Grundsatzwechseln |
| `docs/spec.md` | Zentrale fachliche Spec und Beispieldaten | bei Scope-Aenderungen |
| `docs/backlog.md` | Feature-Registry mit stabilen IDs | bei neuen Ideen oder Statuswechseln |
| `docs/architecture.md` | Technische Wahrheit, Stack, Datenfluss | bei Architekturentscheidungen |
| `docs/decisions.md` | Chronologisches Entscheidungslog | nach relevanten Entscheidungen |
| `docs/concepts/` | Feature-Konzepte vor komplexer Umsetzung | vor groesseren Features |
| `docs/results/` | Outcome-Notizen nach fertiggestellten Uebungen | nach relevanten Unterrichtsiterationen |
| `docs/audit/` | Code-/Security-Audits | bei Reviews oder vor Releases |

## Workflow

1. **Kontext laden:** `CLAUDE.md`/`AGENTS.md`, dann `docs/spec.md`, bei Umsetzung zusaetzlich `docs/architecture.md` und `docs/backlog.md`.
2. **Aufgabe definieren:** Feature-ID aus `docs/backlog.md` verwenden oder neue ID anlegen.
3. **Plan vor Code:** Akzeptanzkriterien, betroffene Dateien, Risiken und Verifikation notieren.
4. **Umsetzen und testen:** kleinstmoeglichen Lernnutzen bauen, keine unnoetige Plattformlogik.
5. **Session abschliessen:** Docs aktualisieren, Entscheidungen loggen, Backlog-Status anpassen, Tests/Checks nennen.

## Unterrichtsdisziplin

- `docs/spec.md` bleibt die operative Quelle fuer Aufgaben, Daten und Produktannahmen.
- Neue Feature-Wuensche bekommen sofort eine stabile `SAD-NNN` ID im Backlog.
- Offene Fragen muessen entweder in `docs/spec.md`, `docs/backlog.md` oder einer Concept-Notiz sichtbar bleiben.
- KI-generierte Vorschlaege werden fachlich geprueft und nicht als automatische Wahrheit behandelt.

## SOLO-Abweichungen von der Team-Methodik

- Kein `docs/team/`.
- Keine Mission-Dokumente pro Person.
- Keine `docs/INBOX.md`, solange nicht mehrere Maschinen/Worktrees parallel dieselben Docs bearbeiten.
- Keine formalen Team-Rituale; stattdessen: nach relevanter Arbeit kurzer Doku-Sync.

## Projektprinzipien

- BWL-Bezug vor Technikshow.
- Kleine, erklaerbare Datenmodelle statt grosser Plattformarchitektur.
- Fiktive Daten statt echter Personen- oder Unternehmensdaten.
- Berechnungen im Code nachvollziehbar halten, auch wenn KI beim Erklaeren hilft.
- Ergebnisse nach Unterrichtsnutzung dokumentieren, damit Folgefeatures aus echten Beobachtungen entstehen.
