# ais-chat-config

Fertige Prompts zum Erstellen von AIS.chat-Vorlagen: Assistenten, Lernszenarien und Dialogpartner.

Live: [https://mgkurz.github.io/ais-chat-config/](https://mgkurz.github.io/ais-chat-config/)

## Was ist das?

Eine einzelne HTML-Seite mit drei vorbereiteten Prompts. Lehrkräfte kopieren einen Prompt, fügen ihn in eine KI ihrer Wahl ein (AIS.chat, Duck.ai, Mistral, ChatGPT, Claude, Gemini), tragen ihre Idee direkt unten im Prompt ein und erhalten die fertigen Texte zum Einfügen in das AIS.chat-Formular.

Standardmäßig erzeugt die KI direkt die fertigen Felder. Wer die Zeile unter IHRE EINGABE unverändert lässt, wird Schritt für Schritt gefragt.

AIS.chat ist der ländergemeinsame, datenschutzkonforme KI-Chatbot für Schulen. Informationen für hessische Lehrkräfte: [ki.bildung.hessen.de](https://ki.bildung.hessen.de)

## Drei Vorlagentypen

- **Assistent**: konfigurierbares KI-Werkzeug primär für Lehrkräfte (Materialerstellung, Differenzierung, Korrekturhilfe).
- **Lernszenario**: themengebundener Chat mit Arbeitsauftrag, AIS.chat als Lernbegleiter. Für Lernende.
- **Dialogpartner**: simulierte Person oder Figur als Gesprächspartner, mit figurspezifischem Anti-Verhalten. Für Lernende.

Jede generierte Vorlage enthält wortgleich eingebaute Knappheitsregeln, damit AIS.chat im Einsatz nicht weitschweifig wird. Feldlogik und Knappheitsbausteine entsprechen `ais-chat-builder` v2.1.0, die Block-Überschriften im Instruktionsfeld sind Markdown (`#### Rolle`, `#### Kontext` usw.).

## Schnellstart

1. Live-Seite öffnen.
2. Vorlagentyp wählen, Prompt kopieren.
3. In eine KI Ihrer Wahl einfügen.
4. Ihre Idee unten unter IHRE EINGABE eintragen und alles zusammen absenden. Zeile unverändert lassen für den geführten Modus.
5. Ausgegebene Texte in das AIS.chat-Formular übertragen.

Im Chat von AIS.chat gilt derzeit ein Limit von 6.000 Zeichen pro Nachricht. Die Prompts sind so knapp gehalten, dass daneben mindestens 600 Zeichen für die Idee bleiben. Für eine längere Beschreibung den Prompt unverändert absenden und die Idee in die nächste Nachricht schreiben.

Optional am Ende: Die KI bitten, eine begleitende Hintergrundwissens-Datei (Markdown oder Text) zu erzeugen, die in AIS.chat hochgeladen werden kann.

## Technik

Eine einzige `index.html`, kein Framework, kein Build, keine externen Abhängigkeiten, keine Cookies, kein Tracking. Die Prompts stehen als JS-Variablen (`const PROMPTS = { ... }`) im `<script>`-Block der Datei. Längenbudget: jeder Prompt höchstens 5.300 Zeichen ohne Platzhalterzeile, damit er samt Idee in den Chat von AIS.chat passt.

Für lokale Nutzung: `index.html` herunterladen und im Browser öffnen.

## Verwandte Projekte

- [`ais-chat-builder`](https://github.com/mgkurz/ais-chat-builder): Claude-Skill mit derselben Feldlogik, für erfahrenere Nutzerinnen und Nutzer.
- [`ki-modell-auswahl`](https://github.com/mgkurz/ki-modell-auswahl): Übersicht über die in AIS.chat verfügbaren Sprachmodelle.

## Lizenz

CC BY-SA 4.0, © 2026 Hessische Lehrkräfteakademie, Martin Kurz

## Kontakt

Martin Kurz, Hessische Lehrkräfteakademie, Dezernat II.3 Medien
martin.kurz@bildung.hessen.de
