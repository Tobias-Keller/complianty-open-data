# Complianty-Studie 2026 — Offener Datensatz (Datenbeschreibung)

**Tracking vor der Einwilligung auf deutschen Websites**
Version 1.0 · Datenstand 18.06.2026 · veröffentlicht 19.08.2026
Quelle & vollständige Studie: https://complianty.de/studie/dsgvo-verstoesse-deutsche-websites-2026/

## Lizenz: CC BY 4.0 (Open Data)

Dieser Datensatz steht unter der Lizenz **Creative Commons Namensnennung 4.0 International
(CC BY 4.0)**: https://creativecommons.org/licenses/by/4.0/deed.de

Sie dürfen die Daten nutzen, teilen und bearbeiten — auch kommerziell —, solange Sie
**„Complianty" als Quelle nennen und auf die Quell-URL verlinken**:

> Complianty (2026): Tracking vor der Einwilligung auf deutschen Websites.
> Datenauswertung von 1.193.438 erfolgreich geprüften .de-Websites, Stand Juni 2026.
> complianty.de/studie

## Dateien

| Datei | Inhalt |
|---|---|
| `complianty-studie-2026-aggregiert.csv` | Alle Aggregate als flache Tabelle |
| `complianty-studie-2026-aggregiert.json` | Dieselben Aggregate strukturiert, inkl. Metadaten/Lizenz |
| `chart-kernbefund.svg` / `.png` | Einbettbares Chart zum Kernbefund |
| `README-daten.md` | Diese Datenbeschreibung |

## Spalten der CSV

| Spalte | Bedeutung |
|---|---|
| `bereich` | Themenblock (Überblick, Weitere Befunde, Validierung, Top-Dienste, CMP-Marktanteil, Kategorie) |
| `kennzahl` | Name der Kennzahl bzw. des Dienstes/CMPs |
| `seiten` | Absolute Anzahl distinct Websites (leer, wenn nur ein Prozentwert sinnvoll ist) |
| `anteil_prozent` | Prozentwert; Bezugsgröße ist der Gesamtkorpus, sofern die Kennzahl nichts anderes sagt (z. B. „Anteil der Banner-Seiten") |

## Was wurde gemessen? (Kurzmethodik)

Automatisierte Browser-Messung mit frischem Browser-Kontext (keine Cookies, kein Storage):
Netzwerk-Mitschnitt **vor** der Einwilligung → Klick auf „Alle akzeptieren" → Delta-Messung
**nach** der Einwilligung. Korpus: 1.193.438 fehlerfrei geprüfte .de-Websites (jüngster Scan
je Domain, technische Erfolgsquote ~62,6 %).

**„Befund" = messbarer technischer Sachverhalt** (Tracking vor dem Consent-Klick),
**keine rechtliche Bewertung** des Einzelfalls.

### Definitionen

- **Streng (Headline):** nur echtes Tracking — Analytics, Werbung, Retargeting,
  Session-Recording, A/B-Testing. Maps-/Video-Embeds, Monitoring und
  Consent-Mode-denied-Pings sind bewusst **ausgeschlossen** (rechtliche Einordnung im
  Einzelfall umstritten).
- **Weit (nur Transparenz):** inklusive Maps/Video/Monitoring — nicht Headline.
- **Kernbefund:** Seiten mit Cookie-Banner, die trotzdem vor der Einwilligung echtes
  Tracking laden — bezogen auf alle Seiten mit Banner (21,0 %).

### Validierung

Blinde Re-Beurteilung einer geschichteten Stichprobe (n=250, Scanner-Verdict verdeckt)
anhand der rohen Netzwerk-Evidenz: 59,6 % klare Treffer, 27,2 % Graufälle, 13,2 % klare
False Positives (95-%-Wilson-KI 9,6–18,0 %). Die Re-Beurteilung erfolgte automatisiert durch
ein separates Sprachmodell, **nicht** durch ein menschliches Experten-Panel. Die FP-Rate ist
eher überschätzt (First-Party-/proxied Tracker waren ausgeblendet).

### Grenzen

- Server-seitiges Tracking ist netzwerkseitig nicht sichtbar → alle Quoten sind
  **konservative Untergrenzen**.
- Nicht hochgerechnet auf „alle deutschen Websites" — gezählt wird nur der erfolgreich
  geprüfte Bestand.
- Es werden ausschließlich **Aggregate** veröffentlicht, keine Einzelseiten.

## Wichtige Lesehinweise

- **Top-Dienste (weite Zählung):** Ob ein Dienst vor oder nach der Einwilligung lädt, hängt
  allein von der Einbindung auf der jeweiligen Seite ab — nicht vom Dienst selbst. Mehrere
  der genannten Dienste (u. a. Google Analytics, Matomo) lassen sich nachweislich erst nach
  der Einwilligung betreiben.
- **CMP-Marktanteile:** reiner Marktüberblick, **keine Befundquote pro Produkt**. Die
  Befunde hängen an der technischen Einbindung, nicht am Banner-Produkt; eine Aufschlüsselung
  der Befunde nach CMP-Produkt wird bewusst nicht vorgenommen.

## Interessenkonflikt-Hinweis

Erhoben von Complianty, einem Anbieter von DSGVO-Prüfsoftware für Websites. Das
wirtschaftliche Interesse am Thema ist damit offengelegt.

## Changelog

- **1.0 (2026-08-19):** Erstveröffentlichung als offener Datensatz unter CC BY 4.0
  (Datenstand der Studie: 18.06.2026).

## Kontakt

Rückfragen, vollständige Methodik oder zusätzliche aggregierte Auswertungen für
redaktionelle Zwecke: mail@complianty.de · https://complianty.de/presse/
