# STATUS

Stand: 09.09.2026

## Aktueller Stand

**v2.0.1 (Tag `v2.0.1`, 21.05.2026)**, veröffentlicht über GitHub Pages.

Inhalt: eine `index.html` (891 Zeilen) mit drei Meta-Prompts als JS-Konstanten, dazu Impressum und Datenschutzerklärung als Hash-gesteuerte Unterseiten in derselben Datei. Kein Build, keine externen Ressourcen, kein Tracking.

Alle drei Vorlagentypen haben fünf Felder:

| Typ | Felder 1 bis 4 | Feld 5 |
|---|---|---|
| Assistent | Name (50), Kurzbeschreibung (500), Sprachmodell, Instruktionen (10000) | Promptvorschläge, 3 bis 4 à 500 |
| Lernszenario | wie oben | Arbeitsauftrag (500) |
| Dialogpartner | wie oben | Einstiegsfrage (500) |

Versionsgeschichte: v1.0.0 (07.05.2026), v2.0.0 (19.05.2026, Prompts auf den damaligen `ais-chat-builder`-Stand gebracht), v2.0.1 (21.05.2026, Idee-Direkteingabe unter IHRE EINGABE, neue Typ-Reihenfolge, Lizenzjahr).

Seit v2.0.1 wurde am Repo nichts mehr geändert. Dieser Klon ist ab jetzt Produktionsort und Quelle der Wahrheit, die Exporte unter `~/Documents/Arbeit/MediaLab/` sind Release-Kopien (siehe `ORTE.md`).

## Offene Punkte

### 1. Umbenennung `ki-modell-auswahl` bricht vier Links (vorgemerkt, nicht jetzt)

Das Repo `ki-modell-auswahl` soll später in `ais-chat-modellwahl` umbenannt werden. Damit bricht `https://mgkurz.github.io/ki-modell-auswahl/`. Betroffene Stellen hier:

- `index.html`, Zeile 561 (Lernszenario), 673 (Dialogpartner), 783 (Assistent), jeweils im Block EMPFEHLUNGEN unter "Modellwahl prüfen"
- `README.md`, Abschnitt "Verwandte Projekte", GitHub-Link auf `mgkurz/ki-modell-auswahl`

Zu beachten: GitHub richtet nach einer Umbenennung eine Weiterleitung für die Repo-URL ein, für **GitHub Pages gilt das nicht zuverlässig**. Die Pages-URL sollte als gebrochen angenommen werden. Wenn die Umbenennung kommt, ist das hier ein Patch-Release mit neuem Tag, danach Spiegel nachziehen.

### 2. Prompt-Drift zu `ais-chat-builder` (inhaltlich das Dringendste)

Das Schwesterprojekt steht auf **v2.1.0 (04.06.2026)** und hat die Feldlogik seitdem geändert:

- Block-Überschriften im Instruktionsfeld sind dort jetzt Markdown der vierten Ebene (`#### Rolle`, `#### Kontext`, `#### Verhalten`, `#### Format`) in Mixed Case, begründet mit einer Analyse des AIS.chat-Quellcodes.
- Die Knappheitsbausteine wurden verschärft und steuern jetzt explizit gegen die hauseigenen Formatvorgaben von AIS.chat.

Hier steht dagegen noch die v2.0.1-Logik: Überschriften in Großbuchstaben und die ausdrückliche Anweisung "Kein Markdown wie Raute oder Sternchen". Genau diese Aussage hat der Builder in v2.1.0 zurückgenommen. Die beiden Projekte widersprechen sich damit inhaltlich.

Zu entscheiden: v2.1.0-Logik hier nachziehen (dann Major- oder Minor-Release plus neue Exporte) oder bewusst auf dem alten Stand belassen und begründen.

### 3. Design nicht im AIS.chat-CD

`index.html` nutzt ein eigenes Grünschema (`--color-accent: #4a7c59`) und System-Schriften, nicht Barlow, Dark Purple und Mint aus dem AIS.chat-Styleguide. Die Typ-Akzentfarben (Lila, Beere, Grün) sind ebenfalls frei gewählt. Eine Umstellung wäre reine CSS-Arbeit ohne Struktureingriff, Schriften müssten wegen der No-CDN-Regel lokal mitgeliefert werden.

### 4. Git-Autor wechselt beim nächsten Commit

Die gesamte bisherige Historie ist mit der privaten Autor-Adresse geschrieben. Lokal ist keine Mail gesetzt, global steht die dienstliche Adresse. Der nächste Commit läuft damit auf die dienstliche Adresse, die Historie bekommt einen Bruch. (Konkrete Adressen bewusst nicht hier, sie stehen in `CLAUDE.local.md` und im Impressum.)

Entschieden: Das ist so gewollt. Impressum und Verantwortung sind dienstlich, deshalb bleibt es bei der globalen dienstlichen Adresse, kein `git config --local`. Der Bruch wird in Kauf genommen, alte Commits werden nicht umgeschrieben.

### 5. Kleinigkeiten

- Die Seite trägt keine sichtbare Versionsnummer. Wer die Datei lokal gespeichert hat, kann seinen Stand nicht erkennen. Ein kleiner Vermerk im Footer würde reichen.
- Kein `CHANGELOG.md`. Die Tag-Nachrichten tragen die Information, das Schwesterprojekt führt aber ein Changelog. Bei der nächsten inhaltlichen Änderung mit anlegen.
- Im Impressum steht unter Haftungsausschluss: "Die bereitgestellten Prompts sind Vorlagen und Ausgangspunkte, keine fertigen Vorlagen." Der Satz widerspricht sich selbst. Gemeint ist vermutlich "keine fertigen Unterrichtsmaterialien". Beim nächsten Anfassen korrigieren.
