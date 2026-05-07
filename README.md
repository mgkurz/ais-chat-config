# ais-chat-config

KI-gestützte Erstellung von AIS.chat-Konfigurationen – Lernszenarien, Dialogpartner und Assistenten.

## Was ist das?

Eine einzelne HTML-Seite mit fertigen Dialog-Prompts, die Lehrkräfte Schritt für Schritt durch die Erstellung von AIS.chat-Konfigurationen führen. Die Prompts können mit einem Klick kopiert und in eine KI der Wahl eingefügt werden – z. B. AIS.chat, Duck AI, ChatGPT oder Claude.

**AIS.chat** ist der DSGVO-konforme KI-Chatbot für hessische Schulen, erreichbar über das Schulportal Hessen. Weitere Informationen: [ki.bildung.hessen.de](https://ki.bildung.hessen.de)

## Live ansehen

👉 [https://mgkurz.github.io/ais-chat-config/](https://mgkurz.github.io/ais-chat-config/)

## Drei Konfigurationstypen

- **Lernszenario** – themengebundener Chat-Raum für Lernende mit definiertem AIS.chat-Verhalten (4 Schritte, 4 Felder)
- **Dialogpartner** – simulierte Person oder Figur, die Lernende im Gespräch begleitet (7 Schritte, 7 Felder)
- **Assistent** – konfigurierbares KI-Werkzeug primär für Lehrkräfte zur Unterrichtsvorbereitung (4 Schritte, 4 Felder + Promptvorschläge)

## So funktioniert es

1. Konfigurationstyp wählen und Prompt kopieren
2. Prompt in eine KI einfügen – die KI führt dialogisch durch die Erstellung
3. Fertige Texte in die AIS.chat-Formulare eintragen

## Anleitung

### Schnellstart für Lehrkräfte
1. Öffne die Live-Seite: https://mgkurz.github.io/ais-chat-config/
2. Wähle einen der drei Konfigurationstypen (Lernszenario, Dialogpartner oder Assistent).
3. Klicke auf „Prompt kopieren".
4. Füge den Prompt in eine KI Deiner Wahl ein (AIS.chat, Duck AI, ChatGPT, Claude …).
5. Beantworte die Rückfragen der KI Schritt für Schritt.
6. Übertrage die fertigen Texte in die entsprechenden AIS.chat-Formularfelder.

### Tipps
- Du kannst den Prompt auch zwischendurch anpassen, wenn Dein Lernziel sich ändert.
- Bei Lernszenarien lohnt es sich, die Verhaltensregeln möglichst konkret zu formulieren.
- Bei Dialogpartnern: präziser Charakter + klare Gesprächsziele = bessere Ergebnisse.

### Lokale Nutzung
- `index.html` aus dem Repository herunterladen und im Browser öffnen — fertig.
- Keine Installation, keine Abhängigkeiten, keine Cookies.

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

Martin Kurz, Hessische Lehrkräfteakademie, Dezernat II.3 Medien
E-Mail: martin.kurz@bildung.hessen.de
