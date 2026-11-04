# Complianty-Studie 2026: Offener Datensatz, Version 2 (Datenbeschreibung)

**Tracking vor der Einwilligung auf deutschen Websites**
Version 2.0 · Datenstand 14.09. bis 02.11.2026 · aufbereitet 03.11.2026
Quelle & vollständige Studie: https://complianty.de/studie/dsgvo-verstoesse-deutsche-websites-2026/
DOI (Version 2): https://doi.org/10.5281/zenodo.23939754

Version 1.0 (Datenstand 18.06.2026, DOI 10.5281/zenodo.22009986) bleibt unverändert
abrufbar: `complianty-studie-2026-aggregiert.csv` und `.json` sowie `README-daten.md`.

## Lizenz: CC BY 4.0 (Open Data)

Dieser Datensatz steht unter der Lizenz **Creative Commons Namensnennung 4.0 International
(CC BY 4.0)**: https://creativecommons.org/licenses/by/4.0/deed.de

Sie dürfen die Daten nutzen, teilen und bearbeiten, auch kommerziell, solange Sie
**„Complianty" als Quelle nennen und auf die Quell-URL verlinken**:

> Complianty (2026): Tracking vor der Einwilligung auf deutschen Websites.
> Datenauswertung von 3.158.515 erfolgreich geprüften .de-Websites, Version 2, Stand November 2026.
> complianty.de/studie · DOI: https://doi.org/10.5281/zenodo.23939754

## Dateien

| Datei | Inhalt |
|---|---|
| `complianty-studie-2026-aggregiert-v2.csv` | Alle Aggregate der Version 2 als flache Tabelle |
| `complianty-studie-2026-aggregiert-v2.json` | Dieselben Aggregate strukturiert, inkl. Metadaten, Lizenz und Vergleich zu Version 1 |
| `README-daten-v2.md` | Diese Datenbeschreibung |

## Spalten der CSV

| Spalte | Bedeutung |
|---|---|
| `bereich` | Themenblock (Überblick, Weitere Befunde, Validierung, Top-Dienste, CMP-Marktanteil, Kategorie) |
| `kennzahl` | Name der Kennzahl bzw. des Dienstes/CMPs |
| `seiten` | Absolute Anzahl distinct Websites (leer, wenn nur ein Prozentwert sinnvoll ist) |
| `anteil_prozent` | Prozentwert; Bezugsgröße ist der Gesamtkorpus, sofern die Kennzahl nichts anderes sagt (Banner-Seiten beim Kernbefund und bei den CMP-Marktanteilen) |

Gegenüber Version 1 ist eine Zeile hinzugekommen: „Tracking vor Einwilligung (weit, nur
Transparenz)". Die technische Erfolgsquote entfällt (siehe Grenzen).

## Was wurde gemessen? (Kurzmethodik)

Automatisierte Browser-Messung mit frischem Browser-Kontext (keine Cookies, kein Storage):
Netzwerk-Mitschnitt **vor** der Einwilligung → Klick auf „Alle akzeptieren" → Delta-Messung
**nach** der Einwilligung. Korpus: 3.158.515 fehlerfrei geprüfte .de-Websites (jüngster
erfolgreicher Scan je Domain, Scans vom 14.09. bis 02.11.2026).

**„Befund" = messbarer technischer Sachverhalt** (Tracking vor dem Consent-Klick),
**keine rechtliche Bewertung** des Einzelfalls.

### Definitionen (unverändert zu Version 1)

- **Streng (Headline):** nur echtes Tracking: Analytics, Werbung, Retargeting,
  Session-Recording, A/B-Testing, die laut Katalog eine Einwilligung erfordern. Maps-/Video-Embeds,
  Monitoring und Consent-Mode-denied-Pings sind bewusst **ausgeschlossen** (rechtliche
  Einordnung im Einzelfall umstritten).
- **Weit (nur Transparenz):** inklusive Maps/Video/Monitoring, nicht Headline.
- **Kernbefund:** Seiten mit Cookie-Banner, die trotzdem vor der Einwilligung echtes
  Tracking laden, bezogen auf alle Seiten mit Banner (19,8 %).

### Was in Version 2 anders ist

- **Größerer Korpus.** 3.158.515 statt 1.193.438 Websites. Die Zusammensetzung des Korpus
  hat sich verändert; aus dem Unterschied der Zahlen lässt sich deshalb kein Trend ablesen.
- **Aktueller Katalog.** Alle Scans werden mit dem heutigen Fingerprint-Katalog
  (3.140 Signaturen) klassifiziert. Top-Dienste und Kategorien sind damit neu klassifiziert;
  die Top-Dienste-Liste in Version 1 war eine Rohzählung des damaligen Scans.
- **Gegenprobe zu Version 1.** Der Juni-Korpus wurde mit dem heutigen Katalog erneut
  klassifiziert. Der reine Katalog-Effekt liegt bei rund 2 Prozent relativ (streng 17,9 % auf
  18,3 %). Die Hauptzahl ist über beide Versionen stabil (18,3 % gegen 18,0 %), der Kernbefund
  liegt mit 19,8 % um 1,5 Prozentpunkte unter der Gegenprobe (21,3 %). Die Ursache lässt sich
  nicht trennen.

| Kennzahl | v1 veröffentlicht | v1 mit heutigem Katalog | v2 |
|---|---|---|---|
| Mit Cookie-Banner | 46,5 % | 46,5 % | 44,8 % |
| Tracking vor Einwilligung (streng) | 17,9 % | 18,3 % | 18,0 % |
| Tracking vor Einwilligung (weit) | 31,1 % | 31,7 % | 30,5 % |
| Kernbefund (Banner und Tracking) | 21,0 % | 21,3 % | 19,8 % |
| Kein Banner und Dritt-Tracking | 16,7 % | 16,6 % | 19,5 % |
| Daten an Google vor Consent | 14,8 % | 14,8 % | 15,4 % |
| Daten an Meta vor Consent | 3,2 % | 3,2 % | 2,9 % |
| Cookies/Storage vor Consent | 9,1 % | 9,1 % | 14,0 % |

### Validierung

Blinde Re-Beurteilung einer Stichprobe (n=250, Scanner-Verdict verdeckt) anhand der rohen
Netzwerk-Evidenz: 63,2 % klare Treffer, 33,2 % Graufälle, 3,6 % klare False Positives
(95-%-Wilson-KI 1,9 bis 6,7 %). Die Stichprobe bestand aus 200 Seiten mit bestätigtem Befund
und 50 Consent-Mode-/Transfer-Fällen; sie ist nicht identisch aufgebaut wie die Stichprobe in
Version 1 (59,6 / 27,2 / 13,2 %). Die FP-Raten sind daher nur eingeschränkt vergleichbar. Die
Re-Beurteilung erfolgte automatisiert durch ein separates Sprachmodell, **nicht** durch ein
menschliches Experten-Panel.

### Grenzen

- Server-seitiges Tracking ist netzwerkseitig nicht sichtbar, alle Quoten sind
  **konservative Untergrenzen**.
- Nicht hochgerechnet auf „alle deutschen Websites": gezählt wird nur der erfolgreich
  geprüfte Bestand. Eine technische Erfolgsquote wird für Version 2 nicht ausgewiesen, weil
  der Korpus nur erfolgreiche Scans enthält.
- **Cookies/Storage vor Consent (14,0 %):** Der Anstieg gegenüber Version 1 (9,1 %) steckt
  bereits in den Rohdaten der neueren Scans. Ob er ein Trend ist oder auf eine geänderte
  Messung des Scanners zurückgeht, ist nicht geklärt. Bitte nicht als Trend zitieren.
- Es werden ausschließlich **Aggregate** veröffentlicht, keine Einzelseiten.

## Wichtige Lesehinweise

- **Top-Dienste (weite Zählung):** Ob ein Dienst vor oder nach der Einwilligung lädt, hängt
  allein von der Einbindung auf der jeweiligen Seite ab, nicht vom Dienst selbst. Mehrere
  der genannten Dienste (u. a. Google Analytics, Matomo) lassen sich nachweislich erst nach
  der Einwilligung betreiben.
- **CMP-Marktanteile:** reiner Marktüberblick, **keine Befundquote pro Produkt**. Die
  Befunde hängen an der technischen Einbindung, nicht am Banner-Produkt; eine Aufschlüsselung
  der Befunde nach CMP-Produkt wird bewusst nicht vorgenommen. Bezugsgröße sind die
  1.413.507 Seiten mit Banner.

## Interessenkonflikt-Hinweis

Erhoben von Complianty, einem Anbieter von DSGVO-Prüfsoftware für Websites. Das
wirtschaftliche Interesse am Thema ist damit offengelegt.

## Changelog

- **2.0 (2026-11-03 aufbereitet):** Neuauswertung mit 3.158.515 Websites (Datenstand
  14.09. bis 02.11.2026), aktueller Katalog, neue Validierung, Gegenprobe zu Version 1.
- **1.0 (2026-08-19):** Erstveröffentlichung als offener Datensatz unter CC BY 4.0
  (Datenstand der Studie: 18.06.2026).

## Kontakt

Rückfragen, vollständige Methodik oder zusätzliche aggregierte Auswertungen für
redaktionelle Zwecke: mail@complianty.de · https://complianty.de/presse/
