# telli-konfig

KI-gestützte Erstellung von telli-Konfigurationen – Lernszenarien, Dialogpartner und Assistenten.

## Was ist das?

Eine einzelne HTML-Seite mit fertigen Dialog-Prompts, die Lehrkräfte Schritt für Schritt durch die Erstellung von telli-Konfigurationen führen. Die Prompts können mit einem Klick kopiert und in eine KI der Wahl eingefügt werden – z. B. telli, Duck AI, ChatGPT oder Claude.

**telli** ist der DSGVO-konforme KI-Chatbot für hessische Schulen, erreichbar über das Schulportal Hessen. Weitere Informationen: [ki.bildung.hessen.de](https://ki.bildung.hessen.de)

## Live ansehen

👉 [https://mgkurz.github.io/telli-konfig/](https://mgkurz.github.io/telli-konfig/)

## Drei Konfigurationstypen

- **Lernszenario** – themengebundener Chat-Raum für Lernende mit definiertem telli-Verhalten (4 Schritte, 4 Felder)
- **Dialogpartner** – simulierte Person oder Figur, die Lernende im Gespräch begleitet (7 Schritte, 7 Felder)
- **Assistent** – konfigurierbares KI-Werkzeug primär für Lehrkräfte zur Unterrichtsvorbereitung (4 Schritte, 4 Felder + Promptvorschläge)

## So funktioniert es

1. Konfigurationstyp wählen und Prompt kopieren
2. Prompt in eine KI einfügen – die KI führt dialogisch durch die Erstellung
3. Fertige Texte in die telli-Formulare eintragen

## Technik

- Eine einzige `index.html` – kein Framework, kein Build-Step
- Alle Prompts als JS-Variablen direkt in der Datei
- Keine externen Abhängigkeiten – keine Cookies, kein Tracking, keine CDN-Schriften
- DSGVO-konform
- Datenschutzerklärung und Impressum integriert (Hash-Routing)

## Deployment

Datei `index.html` ins Repo legen, GitHub Pages auf den `main`-Branch zeigen lassen. Fertig.

## Prompts aktualisieren

Die Prompt-Texte sind direkt im `<script>`-Bereich der `index.html` als JS-Variablen hinterlegt (`const PROMPTS = { ... }`). Änderungen dort wirken sofort nach dem nächsten Push.

## Lizenz

CC BY-SA 4.0 · Hessische Lehrkräfteakademie · Martin Kurz

## Kontakt

Martin Kurz, Hessische Lehrkräfteakademie, Dezernat II.3 Medien (Medialab)
E-Mail: martin.kurz@bildung.hessen.de
