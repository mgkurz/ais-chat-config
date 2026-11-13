# CLAUDE.md

Diese Datei gibt Claude Code den Kontext und die Regeln für dieses Projekt.
Claude Code liest sie zu Beginn jeder Session automatisch.
Kommunikation, Arbeitsweise und Kenntnisstand stehen global in `~/.claude/CLAUDE.md`.

## Autor und Verantwortung

- **Autor**: Martin Kurz
- **Institution**: Hessische Lehrkräfteakademie (HLA), Dezernat II.3 Medien
- **Rolle**: Beauftragt für die Produktion von Bildungsmedien in der Lehrkräftebildung, sekundär Unterrichtsmaterialien im Kontext der Lehrkräftefortbildung
- **Kontaktdaten** (dienstliche E-Mail, GitHub): nicht im öffentlichen Repo. Sie stehen lokal in `CLAUDE.local.md` (ge-gitignored) und im Impressum des jeweiligen Artefakts.
- Die Verantwortung als Autor wird wahrgenommen, auch im Datenschutz. Transparenz ist wichtig.
- Hinweis zum Status: privat erstellt mit dienstlichem Bezug, ohne formale Anbindung an einen Datenschutzbeauftragten der HLA. Die Verantwortung liegt beim Autor.
- Jede Veröffentlichung braucht Impressum, Datenschutzerklärung und Nutzungsbedingungen.

## Projektkontext

- **Was**: Eine einzelne HTML-Seite mit drei Meta-Prompts (Assistent, Lernszenario, Dialogpartner). Lehrkräfte kopieren einen Prompt, tragen ihre Unterrichtsidee unter IHRE EINGABE ein und erhalten von einer KI die fertigen Feldtexte für eine AIS.chat-Vorlage. Die Seite selbst erzeugt nichts, sie liefert nur die Prompts.
- **Zielgruppe**: Lehrkräfte, überwiegend ohne Prompting-Vorerfahrung.
- **Einsatzkontext**: GitHub Pages, öffentlich, einzige Adresse zum Verlinken siehe `ORTE.md`. Anbieterunabhängig: funktioniert mit jeder KI, genannt werden AIS.chat, Duck.ai, Mistral, ChatGPT, Claude und Gemini.

## Projektregeln

- `index.html` ist Single File: kein Build, kein Framework, keine externen Abhängigkeiten. Änderungen gehen direkt in die Datei, es gibt keinen Generator davor.
- Die drei Prompts stehen als JS-Konstanten im `<script>`-Block, in `const PROMPTS = { lernszenario, dialogpartner, assistent }`. Der Kommentar darüber gilt: nur diese Texte aktualisieren, den Rest des Skripts unverändert lassen.
- Anzeigereihenfolge ist Assistent, Lernszenario, Dialogpartner und ergibt sich aus der Kartenreihenfolge im HTML, nicht aus dem `PROMPTS`-Objekt. Die Objekt-Keys stehen noch in der alten Reihenfolge.
- Versionierung läuft über Git-Tags nach SemVer mit `v`-Präfix (aktuell `v2.2.0`), Änderungen stehen in `CHANGELOG.md`. Jede veröffentlichte Änderung bekommt einen Tag. Seit v2.2.0 trägt die Seite einen Versionsvermerk im Fuß, der bei jedem Release mitgezogen wird.
- **Jede inhaltliche Prompt-Änderung braucht einen Abgleich mit `ais-chat-builder`.** Beide Projekte halten ihre Prompts getrennt und teilen keinen Code. Feldlogik, Zeichenlimits und Knappheitsbausteine müssen von Hand in beide Richtungen abgeglichen werden. Vor und nach jeder Prompt-Änderung dort den Stand prüfen (siehe `ORTE.md` und `STATUS.md`). Stand seit v2.1.0: Feldlogik wie Builder v2.1.0, Block-Überschriften im Instruktionsfeld als Markdown vierter Ebene (`#### Rolle` usw.). Bewusste Abweichungen vom Builder stehen in `STATUS.md`.
- **Längenbudget**: Jeder Prompt höchstens 5.300 Zeichen ohne die Platzhalterzeile unter IHRE EINGABE. Grund: Der Chat von AIS.chat nimmt derzeit höchstens 6.000 Zeichen pro Nachricht an (Stand 09/2026), daneben sollen mindestens ca. 650 Zeichen für die Idee bleiben. Nach jeder Prompt-Änderung messen. Das ausgeschriebene Ausgabegerüst unter AUSGABEFORMAT nicht wegkürzen: Im Test vom 15.09.2026 ließ ein kleines Modell ohne Gerüst bei 3 von 9 Läufen die Feldtitel weg. Ändert sich das Limit, den Aufklapper in der Intro-Box, die README und diese Regel anpassen.
- Impressum, Datenschutzerklärung und Verantwortung sind dienstlich (Hessische Lehrkräfteakademie, Dezernat II.3 Medien). Die Repo-Mail bleibt deshalb die global eingestellte dienstliche Adresse, kein `git config --local`.

## Ablage und Orte

- Dieses Projekt ist Produktionsort und Quelle der Wahrheit für Quellen und Doku (HTML, MD, Skripte, aggregierte Zahlen).
- Fertige dienstliche Endprodukte (PDFs etc.) liegen nicht im Repo und nicht auf GitHub, sondern lokal in `~/Documents/Arbeit/F3-4/` (je Thema ein Ordner). Das Repo hält die reproduzierbaren Quellen, `ORTE.md` verweist auf den Ablageort. Teamordner und Mail erhalten nur Kopien.
- Externe Fundorte in einer `ORTE.md` verweisen statt kopieren. Projektstand optional in `STATUS.md`.
- Privates GitHub-Remote ist Standard, Push gehört zum Arbeitsabschluss. Öffentlich nur bewusst, dann gilt die Repo-Mail-Regel aus der globalen CLAUDE.md.

## Lizenz

- Standard für Artefakte (einzelne HTML-Dateien, ggf. mit Bildern): alles unter CC BY-SA 4.0, auch der eingebettete HTML/CSS/JS-Code. Kein getrenntes MIT.
- MIT (oder andere freie Code-Lizenz) nur bei echtem, eigenständigem Programm: App, wiederverwendbares Tool, Komponentenbibliothek.
- Kontextabhängig. Im Zweifel kurz nachfragen.

## Tech-Stack und Veröffentlichung

- HTML5, CSS3, Vanilla JavaScript
- Veröffentlichung aktuell über GitHub Pages. Was dort technisch möglich ist, darf genutzt werden, besonders bei höherer Komplexität.
- Übergang zu React erst nach Rücksprache.
- Datenspeicherung bei Bedarf: Supabase (EU/Frankfurt). Noch keine Praxiserfahrung, daher die nötigen Schritte erklären, wenn es relevant wird.

## Datenschutz (DSGVO): nicht verhandelbar

- Keine externen CDNs, Analytics oder Tracker einbinden.
- Schriften lokal einbinden, notfalls mitliefern. Keine Remote-Fonts.
- Bilder, Medien und alle weiteren Assets lokal halten und mitliefern.
- Keine personenbezogenen Daten in Code, Kommentaren oder Commits, auch keine pseudonymisierten (IDs, Teilnehmerlisten, Exporte). Rohdaten nur in einer gitignorten Transitzone auswerten und löschen, committet werden nur Aggregate. Kolleginnen und Kollegen in Repo-Dateien nur mit Vornamen.
- Keine echten Schülerdaten in Beispielen. Immer Dummy-Daten.
- Bei jeder externen Abhängigkeit, die du vorschlagen willst: erst nennen und begründen, nicht ungefragt einbauen.

## Design

- Es gibt mehrere Design-Sets.
- Für AIS.chat liegt ein Styleguide als PDF vor, dazu Vorlagen-Dateien für Logo, Signets und Hintergründe.
- Assets werden lokal abgelegt oder diskret im Repo gehalten.
- Für dieses Projekt gilt das AIS.chat-CD (Barlow, Dark Purple, Mint). Styleguide und Vorlagen liegen in `~/Projekte/hessische-lehrkraefteakademie/referenz/` (`20260505_AIS.chat_Styleguide.pdf`).
- Ist-Stand: `index.html` ist seit v2.2.0 im AIS.chat-CD (Barlow eingebettet, Dark Purple, Mint, Logo und Pattern). Muster ist die Schwesterseite `ki-modell-auswahl`, Logo, Pattern und Schrift stammen wörtlich von dort.

## Barrierefreiheit

- Semantisches HTML (heading-Hierarchie, button statt div mit onclick, alt-Texte).
- Ausreichende Farbkontraste, Tastaturbedienbarkeit.
- Grundlegende Konformität, kein WCAG-AAA-Aufwand.

## Code-Konventionen

- Kommentare und UI-Texte auf Deutsch.
- Kurze, lesbare Funktionen. Sprechende Namen.
- Lesbarkeit vor Performance. Performance ist hier zweitrangig.
- Keine vorzeitige Optimierung.

## Git

- Kurze, sinnvolle Commit-Messages auf Deutsch.
- `.env` und Konfigdateien mit Secrets gehören in `.gitignore`, niemals committen.
- Vor jedem Commit prüfen: keine personenbezogenen Daten, keine Keys.
