# ais-chat-config

Fertige Prompts zum Erstellen von AIS.chat-Vorlagen: Lernszenarien, Dialogpartner und Assistenten.

Live: [https://mgkurz.github.io/ais-chat-config/](https://mgkurz.github.io/ais-chat-config/)

## Was ist das?

Eine einzelne HTML-Seite mit drei vorbereiteten Prompts. Lehrkräfte kopieren einen Prompt, fügen ihn in eine KI ihrer Wahl ein (AIS.chat, Duck AI, ChatGPT, Claude), beschreiben kurz Thema und Zielgruppe und erhalten die fertigen Texte zum Einfügen in das AIS.chat-Formular.

Standardmäßig erzeugt die KI direkt die fertigen Felder. Bei vagen Eingaben fragt sie Schritt für Schritt nach.

AIS.chat ist der ländergemeinsame, datenschutzkonforme KI-Chatbot für Schulen. Informationen für hessische Lehrkräfte: [ki.bildung.hessen.de](https://ki.bildung.hessen.de)

## Drei Vorlagentypen

- **Lernszenario**: themengebundener Chat mit Arbeitsauftrag, AIS.chat als Lernbegleiter. Für Lernende.
- **Dialogpartner**: simulierte Person oder Figur als Gesprächspartner, mit figurspezifischem Anti-Verhalten. Für Lernende.
- **Assistent**: konfigurierbares KI-Werkzeug primär für Lehrkräfte (Materialerstellung, Differenzierung, Korrekturhilfe).

Jede generierte Vorlage enthält wortgleich eingebaute Knappheitsregeln, damit AIS.chat im Einsatz nicht weitschweifig wird.

## Schnellstart

1. Live-Seite öffnen.
2. Vorlagentyp wählen, Prompt kopieren.
3. In eine KI Ihrer Wahl einfügen.
4. Thema, Zielgruppe und Lernziel kurz beschreiben.
5. Ausgegebene Texte in das AIS.chat-Formular übertragen.

Optional am Ende: Die KI bitten, eine begleitende Hintergrundwissens-Datei (Markdown oder Text) zu erzeugen, die in AIS.chat hochgeladen werden kann.

## Technik

Eine einzige `index.html`, kein Framework, kein Build, keine externen Abhängigkeiten, keine Cookies, kein Tracking. Die Prompts stehen als JS-Variablen (`const PROMPTS = { ... }`) im `<script>`-Block der Datei.

Für lokale Nutzung: `index.html` herunterladen und im Browser öffnen.

## Verwandte Projekte

- [`ais-chat-builder`](https://github.com/mgkurz/ais-chat-builder): Claude-Skill mit derselben Feldlogik, für erfahrenere Nutzerinnen und Nutzer.
- [`ki-modell-auswahl`](https://github.com/mgkurz/ki-modell-auswahl): Übersicht über die in AIS.chat verfügbaren Sprachmodelle.

## Lizenz

CC BY-SA 4.0, Hessische Lehrkräfteakademie, Martin Kurz

## Kontakt

Martin Kurz, Hessische Lehrkräfteakademie, Dezernat II.3 Medien
martin.kurz@bildung.hessen.de
