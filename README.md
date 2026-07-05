# Plan F – Ausweichrouten mit Rad + VBB

Wenn S-Bahn oder Bus ausfallen: per Klapprad zur nächsten brauchbaren Haltestelle, Verbindungen ab dort in Echtzeit, sortiert nach frühester Ankunft. Läuft komplett im Browser, keine Server, keine Keys.

## Aufs Handy holen

Die URL in Safari oder Chrome öffnen, dann "Zum Home-Bildschirm hinzufügen". Beim ersten GPS-Klick die Standortfreigabe erlauben.

## Bedienung

1. Start setzen (GPS-Button oder Adresse tippen), Ziel eingeben.
2. Radradius und Radtempo einstellen.
3. Wählen, was als Ausweichhaltestelle zählt (S-Bahn, U-Bahn, RE/RB, Tram, Bus, Fähre).
4. Ausgefallene Linien ins Feld "Linien meiden" eintragen, z.B. `S1, RE7`.
5. Suchen. Die Karten zeigen Radetappe (mit Google-Maps-Radrouten-Link), alle ÖPNV-Etappen mit Echtzeit und Störungshinweisen, sortiert nach Ankunftszeit.

## Technik

- Verbindungen und Echtzeit: VBB-HAFAS über [v6.vbb.transport.rest](https://v6.vbb.transport.rest) (öffentlich, CORS-freundlich, ohne Gewähr)
- Radzeiten: Schätzung über Luftlinie × 1,35 Umwegfaktor bei einstellbarem Tempo
- Kern-Logik: Abfahrtssuche pro Haltestelle beginnt erst zu dem Zeitpunkt, zu dem du sie per Rad realistisch erreichst

## Ideen für später

- Echtes Radrouting (BRouter oder Valhalla) statt Schätzung
- Favoriten für Wohnung und Büro, Ein-Knopf-Suche
- Automatisches Einlesen der VBB-Störungsmeldungen in den Linienfilter
