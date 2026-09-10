# ORTE

Wegweiser zu allem, was zu diesem Projekt gehört, aber nicht im Repo liegt.
Verweisen statt kopieren. Quelle der Wahrheit für Quellcode und Doku ist dieses Repo.

## Veröffentlichung

| Ort | Adresse | Rolle |
|---|---|---|
| Repo | https://github.com/mgkurz/ais-chat-config | Quelle der Wahrheit, öffentlich |
| GitHub Pages | https://mgkurz.github.io/ais-chat-config/ | Live-Seite aus diesem Repo |
| Spiegel | https://la-medienproduktion.github.io/ais-chat-config/ | zweite Pages-Instanz, Organisationskonto |
| Kurzlink | https://t1p.de/ais-chat-config | zeigt auf den **Spiegel**, nicht auf mgkurz. In Fortbildungen verteilt, auch als QR-Code |

Kurzlink-Verwaltung (Deaktivierungslink, QR-Generator): `~/Projekte/hessische-lehrkraefteakademie/referenz/t1p_de-ais-chat-config.txt`

Weil der Kurzlink auf den Spiegel zeigt, muss der Spiegel nach jedem Release nachgezogen werden. Sonst sehen Fortbildungsteilnehmer einen alten Stand.

## Versionsexporte (Release-Kopien)

`~/Documents/Arbeit/MediaLab/AIS.chat/Github/ais-chat-config/`

- `v2.0.0/` — index.html, README.md, RELEASE_v2.0.0.md, dazu die drei Prompts einzeln als `prompt_*.md`
- `v2.0.1/` — index.html, README.md, LICENSE, inhaltlich identisch mit dem aktuellen Repo-Stand

Diese Ordner sind ab jetzt **Release-Kopien, keine Arbeitskopien**. Gepflegt wird nur im Repo. Neue Exporte nur bei Bedarf, dann aus dem getaggten Stand.

## Schwesterprojekt

`~/Projekte/ais-chat-builder/` (Repo: https://github.com/mgkurz/ais-chat-builder)

Claude-Skill mit derselben Feldlogik für AIS.chat-Vorlagen, für erfahrenere Nutzerinnen und Nutzer. **Beide Projekte halten ihre Prompts getrennt und teilen keinen Code.** Änderungen an Feldlogik, Zeichenlimits oder Knappheitsbausteinen müssen von Hand abgeglichen werden, in beide Richtungen. Der Stand dort steht in dessen `CHANGELOG.md`.

## Sachgebiets-Referenz

`~/Projekte/hessische-lehrkraefteakademie/referenz/`

Übergreifende Referenz zu AIS.chat: Styleguide (`20260505_AIS.chat_Styleguide.pdf`), Materialübersicht, Kurzlink- und QR-Verzeichnis, Referenzdokument zu AIS.chat selbst.

## Verwandtes Repo

`~/Projekte/ki-modell-auswahl/` (Live: https://mgkurz.github.io/ki-modell-auswahl/)

Übersicht der in AIS.chat verfügbaren Sprachmodelle. Wird aus den Meta-Prompts und aus der README verlinkt. Eine geplante Umbenennung bricht diese Links, siehe `STATUS.md`.
