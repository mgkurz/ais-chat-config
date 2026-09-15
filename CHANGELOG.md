# Changelog

## v2.1.0 (2026-09-15), Minor

Prompts gekürzt, damit sie samt Idee in den Chat von AIS.chat passen (derzeit höchstens 6.000 Zeichen pro Nachricht), und Feldlogik auf den Stand von `ais-chat-builder` v2.1.0 gebracht.

### Geändert

- Prompts um 16 bis 20 Prozent kürzer: Assistent 5.685 → 4.686, Lernszenario 5.917 → 4.946, Dialogpartner 6.699 → 5.395 Zeichen. Neben dem Prompt bleiben mindestens 600 Zeichen für die Idee.
- Gekürzt wurden vor allem Doppelungen: Der Kopf „SO NUTZEN SIE DIESEN PROMPT“ entfällt, ARBEITSWEISE geht in START auf, EMPFEHLUNGEN und das Angebot Hintergrundwissen sind zusammengefasst. Das ausgeschriebene Ausgabegerüst bleibt.
- Die Modusregeln gelten fürs ganze Gespräch. Wer den Prompt ohne Idee absendet und sie in der nächsten Nachricht nachreicht, bekommt direkt die fertige Vorlage.
- Block-Überschriften im Instruktionsfeld als Markdown vierter Ebene in Mixed Case (`#### Rolle`, `#### Kontext`, `#### Verhalten`, `#### Format`, beim Dialogpartner `#### Simulierte Person`, `#### Zielgruppe`, `#### Kontext`, `#### Verhalten`, `#### Anti-Verhalten`). Die Anweisung „Kein Markdown wie Raute oder Sternchen“ ist gestrichen.
- Knappheitsbausteine wortgleich im Wortlaut von Builder v2.1.0 (BAUSTEIN_DIALOG, BAUSTEIN_DIALOG_NEG, BAUSTEIN_WERKZEUG).
- Lernszenario: Der Verhalten-Block verlangt ausdrücklich, dass AIS.chat zum Denken anregt, den Lernenden die Arbeit nicht abnimmt und dem Baustein nicht widerspricht.
- Dialogpartner: Rollenkonsistenz im Verhalten-Block, Regeln zur Einstiegsfrage in Feld 5, Anti-Verhalten mit drei statt sechs Beispielen.
- Platzhalterzeile unter IHRE EINGABE kürzer.
- Seite: AIS.chat, Duck.ai, Mistral, ChatGPT, Claude und Gemini als Beispiele, Aufklapper „Tipp für den Chat von AIS.chat“ in der Intro-Box, Schritt 2 und Haftungsausschluss angepasst.

### Geprüft

- Vergleichstest alt (v2.0.2) gegen neu: je Vorlagentyp zwei Testideen, Haiku als Stellvertreter für kleine Modelle, Sonnet als Gegenprobe, geführter Modus über zwei Nachrichten.
- Objektiv per Skript (Feldtitel, Zeichenlimits, Blöcke, Bausteine wortgleich und an der richtigen Stelle, Empfehlungen samt Modell-Link): neu gleichauf mit alt.
- Eine Zwischenfassung mit einzeiligem AUSGABEFORMAT ließ bei 3 von 9 Läufen die Feldtitel weg. Das Gerüst wurde deshalb wiederhergestellt.
- Blinde Bewertung (A und B zufällig verteilt): Assistent neu 2:0, Dialogpartner neu 1:0 bei einem Unentschieden. Lernszenario zunächst alt 2:0 (Widerspruch zwischen Verhalten-Text und Baustein, fehlende Leitplanke „begleiten statt vorgeben“), daraufhin der Verhalten-Block nachgeschärft, danach 1:1. Gesamt mit der Endfassung: neu 4, alt 1, gleichwertig 1.

## v2.0.2 (2026-09-10), Patch

Haftungsausschluss im Impressum präzisiert, reine Textkorrektur an einer Zeile. Prompts, CSS und Skript unverändert.

## v2.0.1 (2026-05-21), Patch

- Eingabefeld IHRE EINGABE am Promptende, Kurzhinweis oben, konditionaler Start (Idee vorhanden: Direktmodus, leer: geführter Modus).
- Reihenfolge Assistent, Lernszenario, Dialogpartner in Oberfläche, Titel und README.
- Lizenzangabe mit © 2026 in Footer, Impressum und README.

## v2.0.0 (2026-05-19), Major

Prompts auf den damaligen Stand von `ais-chat-builder` gebracht. Das Ausgabeschema ändert sich strukturell.

- Neue Feldstruktur und Limits für alle drei Vorlagentypen.
- Knappheitsbausteine wortgleich in jede Instruktion, Dialogpartner zusätzlich mit Pflicht-Anti-Verhalten.
- Block-Struktur ROLLE, KONTEXT, VERHALTEN, FORMAT vorgegeben.
- Direktmodus als Standard, Interview nur bei vagen Eingaben.
- Modellwahl verweist auf `ki-modell-auswahl` statt auf feste Namen.
- Optionales Angebot, eine Hintergrundwissens-Datei zu erzeugen.
- Seite umbenannt zu „AIS.chat-Vorlagen erstellen“, Sie-Form durchgehend, keine Gedankenstriche.

## v1.0.0 (2026-05-07)

Erste Veröffentlichung mit Anleitung und Tipps für Lehrkräfte, einschließlich lokaler Nutzung.
