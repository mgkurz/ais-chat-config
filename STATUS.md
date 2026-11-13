# STATUS

Stand: 13.11.2026

## Aktueller Stand

**v2.2.0 (Tag `v2.2.0`, 13.11.2026)**, veröffentlicht über GitHub Pages. Rückweg bei Bedarf: Tag `v2.1.0` (15.09.2026).

v2.2.0 ist ein reines Redesign ins AIS.chat-CD (Muster `ki-modell-auswahl`). Prompts und Skript sind unverändert, die Zeichenzahlen unten gelten weiter.

Inhalt: eine `index.html` mit drei Meta-Prompts als JS-Konstanten, dazu Impressum und Datenschutzerklärung als Hash-gesteuerte Unterseiten in derselben Datei. Kein Build, keine externen Ressourcen, kein Tracking.

Alle drei Vorlagentypen haben fünf Felder:

| Typ | Felder 1 bis 4 | Feld 5 |
|---|---|---|
| Assistent | Name (50), Kurzbeschreibung (500), Sprachmodell, Instruktionen (10000) | Promptvorschläge, 3 bis 4 à 500 |
| Lernszenario | wie oben | Arbeitsauftrag (500) |
| Dialogpartner | wie oben | Einstiegsfrage (500) |

v2.1.0 kürzt die Prompts, damit sie samt Idee in den Chat von AIS.chat passen, und bringt die Feldlogik auf den Stand von `ais-chat-builder` v2.1.0. Zeichenzahlen:

| Prompt | v2.0.2 | v2.1.0 | ohne Platzhalterzeile | Platz für die Idee | bei doppelt gezählten Umbrüchen |
|---|---|---|---|---|---|
| Assistent | 5.685 | 4.686 | 4.549 | 1.451 | 1.363 |
| Lernszenario | 5.917 | 4.946 | 4.807 | 1.193 | 1.107 |
| Dialogpartner | 6.699 | 5.395 | 5.263 | 737 | 647 |

Versionsgeschichte in `CHANGELOG.md`: v1.0.0 (07.05.2026), v2.0.0 (19.05.2026), v2.0.1 (21.05.2026), v2.0.2 (10.09.2026), v2.1.0 (15.09.2026), v2.2.0 (13.11.2026).

Dieses Repo ist Produktionsort und Quelle der Wahrheit, die Exporte unter `~/Documents/Arbeit/MediaLab/` sind Release-Kopien (siehe `ORTE.md`). Für v2.0.2 und v2.1.0 ist kein Export angelegt.

## Offene Punkte

### 1. Umbenennung `ki-modell-auswahl` bricht Links (vorgemerkt, nicht jetzt)

Das Repo `ki-modell-auswahl` soll später in `ais-chat-modellwahl` umbenannt werden. Damit bricht `https://mgkurz.github.io/ki-modell-auswahl/`. Betroffene Stellen hier:

- `index.html`, je einmal pro Prompt im Abschnitt EMPFEHLUNGEN unter „Modellwahl prüfen“
- `README.md`, Abschnitt "Verwandte Projekte", GitHub-Link auf `mgkurz/ki-modell-auswahl`

Zu beachten: GitHub richtet nach einer Umbenennung eine Weiterleitung für die Repo-URL ein, für **GitHub Pages gilt das nicht zuverlässig**. Die Pages-URL sollte als gebrochen angenommen werden. Wenn die Umbenennung kommt, ist das hier ein Patch-Release mit neuem Tag. Achtung Längenbudget: Eine längere URL kostet beim Dialogpartner Platz für die Idee.

### 2. Prompt-Drift zu `ais-chat-builder` (erledigt mit v2.1.0)

Die Feldlogik entspricht seit v2.1.0 dem Builder v2.1.0 (04.06.2026): Block-Überschriften im Instruktionsfeld als Markdown vierter Ebene in Mixed Case, Knappheitsbausteine wortgleich im v2.1.0-Wortlaut, „Kein Markdown wie Raute oder Sternchen“ gestrichen.

Bewusste Abweichungen vom Builder, bleiben so:

- Anti-Verhalten beim Dialogpartner immer (Builder: optional). Gibt Lehrkräften ohne Vorerfahrung verlässliche Leitplanken.
- 3 bis 4 Promptvorschläge (Builder: bis zu 10, mindestens 3).
- Beim Dialogpartner nur die personenorientierte Struktur (Builder: auch eine funktionale für komplexe Lernbegleiter).
- START, IHRE EINGABE und das Angebot Hintergrundwissen gibt es nur hier.

Beim nächsten Builder-Release wieder abgleichen und dabei das Längenbudget beachten (siehe Punkt 7).

### 3. Design nicht im AIS.chat-CD (erledigt mit v2.2.0)

Erledigt: Seit v2.2.0 im AIS.chat-CD (Barlow eingebettet, Dark Purple, Mint, Logo und Pattern), Muster ist `ki-modell-auswahl`. Ausgangslage bis v2.1.0: `index.html` nutzte ein eigenes Grünschema (`--color-accent: #4a7c59`) und System-Schriften, nicht Barlow, Dark Purple und Mint aus dem AIS.chat-Styleguide. Die Typ-Akzentfarben (Lila, Beere, Grün) sind ebenfalls frei gewählt. Eine Umstellung wäre reine CSS-Arbeit ohne Struktureingriff, Schriften müssten wegen der No-CDN-Regel lokal mitgeliefert werden.

### 4. Git-Autor gewechselt (vollzogen am 10.09.2026)

Die gesamte bisherige Historie ist mit der privaten Autor-Adresse geschrieben. Lokal ist keine Mail gesetzt, global steht die dienstliche Adresse. Der nächste Commit läuft damit auf die dienstliche Adresse, die Historie bekommt einen Bruch. (Konkrete Adressen bewusst nicht hier, sie stehen in `CLAUDE.local.md` und im Impressum.)

Vollzogen mit Commit `95dc3db`, seitdem laufen alle Commits auf die dienstliche Adresse. Entschieden: Das ist so gewollt. Impressum und Verantwortung sind dienstlich, deshalb bleibt es bei der globalen dienstlichen Adresse, kein `git config --local`. Der Bruch wird in Kauf genommen, alte Commits werden nicht umgeschrieben.

### 5. Kleinigkeiten

- Die Seite trägt keine sichtbare Versionsnummer. Wer die Datei lokal gespeichert hat, kann seinen Stand nicht erkennen. Ein kleiner Vermerk im Footer würde reichen. Erledigt mit v2.2.0: „Version 2.2.0“ im Fuß. Bei jedem Release mitziehen.
- `CHANGELOG.md` ist mit v2.1.0 angelegt (erledigt).

### 6. Befunde aus dem Code-Review vom 10.09.2026 (keiner davon dringend)

Beim Review des Skriptteils gefunden, bewusst nicht in v2.0.2 mitgeändert, weil dieses Release eine reine Textkorrektur bleiben sollte. In v2.1.0 ebenfalls nicht angefasst, dort liefen nur Prompt- und Textänderungen.

- **Fallback beim Kopieren greift nicht überall.** `copyPrompt()` ruft `navigator.clipboard.writeText(...)` und fängt Fehler nur über `.catch()` am Promise ab. Fehlt die Clipboard-API ganz, wirft schon der Zugriff auf `navigator.clipboard` synchron einen TypeError, der `.catch()`-Zweig mit `execCommand('copy')` läuft dann nie. Betrifft nicht GitHub Pages (dort ist der Kontext sicher, die API vorhanden), aber möglicherweise den in der README beschriebenen Weg "index.html herunterladen und lokal öffnen" über `file://`. Fix wäre ein Guard vor dem Aufruf, etwa `if (navigator.clipboard && navigator.clipboard.writeText) { ... } else { fallback() }`. Vorher auf einem echten `file://`-Aufruf reproduzieren, der Testlauf lief über localhost und konnte den Fall nicht zeigen.
- **Kein `<noscript>`-Hinweis.** Die Prompts stehen nur im Skript und werden erst bei `DOMContentLoaded` in die Textareas geschrieben. Ohne JavaScript ist die Seite leer, ohne Erklärung. Ein kurzer Hinweis wäre ein Einzeiler. Erledigt mit v2.2.0.
- **Kein Favicon.** Der Aufruf erzeugt einen 404 auf `/favicon.ico`. Nur kosmetisch, würde aber zum AIS.chat-CD passen (Signet).
- **Toast ohne `aria-live`.** Die Meldung "Prompt kopiert!" wird von Screenreadern nicht angekündigt. Ein Attribut genügt, passt zur Vorgabe "grundlegende Konformität". Erledigt mit v2.2.0 (`role="status"`, `aria-live="polite"`).
- Offen bleiben aus diesem Punkt der Kopier-Rückfall und das Favicon.
- `togglePreview()` findet den Button über `el.nextElementSibling.querySelector(...)`. Funktioniert, hängt aber an der DOM-Reihenfolge innerhalb der Karte. Bei Umbauten am Karten-Markup daran denken. Beim Redesign v2.2.0 beachtet, die Reihenfolge ist unverändert.

### 7. Chat-Limit von AIS.chat (seit v2.1.0 eingehalten)

- Der Chat von AIS.chat nimmt derzeit höchstens 6.000 Zeichen pro Nachricht an (Stand 09/2026). Längenbudget und Begründung stehen in `CLAUDE.md`.
- Offen: Wie zählt AIS.chat Zeilenumbrüche? Die Tabelle oben rechnet beide Fälle. Wird bei der Stichprobe in AIS.chat geklärt, dann hier nachtragen.
- Für längere Ideen gibt es den Weg „Prompt unverändert absenden, Idee in der nächsten Nachricht“. Die Modusregeln im START-Abschnitt gelten deshalb fürs ganze Gespräch. Im Test hat das in 3 von 3 Fällen zur fertigen Vorlage geführt.
- Hebt AIS.chat das Limit an, den Aufklapper „Tipp für den Chat von AIS.chat“ in der Intro-Box, die README und die Regel in `CLAUDE.md` prüfen.
