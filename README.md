# Wahrheitstafel-Übung

Interaktive Wahrheitstafeln nach den Konventionen von *Language, Proof and Logic*
(Barwise/Etchemendy). Studierende geben eine Formel oder ein Argument ein, füllen
die Tafel selbst aus und lassen sie prüfen — die Wahrheitswerte stehen wie bei Boole
unter dem jeweiligen Junktor.

## Funktionen

- Eigene Eingabe von Formeln; Tafel wird daraus erzeugt
- Werte unter den Junktoren, Spalte des Hauptjunktors hervorgehoben
- Prüfen (falsche Einträge rot), Leeren, Lösung zeigen
- Drei Modi, automatisch erkannt:
  - **eine Formel** → Tautologie / unerfüllbar / kontingent
  - **Prämissen `⊨` Konklusion** → Folgerung gültig / ungültig, mit Gegenbeispielzeile
  - **mehrere Formeln mit `,`** → gemeinsam erfüllbar / nicht erfüllbar
- Falsum `⊥`, atomare PL1-Formeln (`Würfel(a)`, `Größer(a,b)`, `a=b`, `a≠b`)
- Tastaturbedienung: `w` / `f` eintragen, Pfeiltasten navigieren, `Entf` löschen

## Syntax

| Eingabe | Bedeutung |
| --- | --- |
| `P`, `Q1`, `cube` | Satzbuchstaben |
| `Würfel(a)`, `Größer(a,b)` | atomare PL1-Formeln (Prädikat groß, Terme klein) |
| `a=b`, `a≠b` (auch `/=`, `!=`) | Identität |
| `⊥` (auch `#`) | Falsum |
| `,` | trennt mehrere Formeln |
| `⊨` (auch `\|=`, `∴`) | trennt Prämissen von der Konklusion |

ASCII-Eingabe wird umgesetzt: `~` → ¬, `&` oder `/\` → ∧, `\/` → ∨, `->` → →, `<->` → ↔.

### Klammerregeln

Wie im LPL-Buch, Abschnitt 3.5: ¬ bindet nur an die unmittelbar folgende Formel, und
die binären Junktoren haben **keine** Rangfolge untereinander. `A ∧ B ∧ C` und
`A ∨ B ∨ C` sind erlaubt, `A ∨ B ∧ C` dagegen nicht — dort verlangt LPL Klammern.
Äußerste Klammern dürfen entfallen; `[` und `{` gelten als Klammern.

## Veröffentlichen mit GitHub Pages

1. `index.html` in ein öffentliches Repository legen
2. Settings → Pages → Source: *Deploy from a branch*, Branch `main`, Ordner `/ (root)`
3. Nach kurzer Zeit erreichbar unter `https://BENUTZERNAME.github.io/REPOSITORY/`

Die Seite ist eine einzige Datei ohne externe Abhängigkeiten und läuft auf jedem
statischen Webspace. Es werden keine Daten gespeichert oder übertragen.
