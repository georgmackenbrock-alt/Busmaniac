# Bus Maniac

Ein Stadtbus-Spiel für den Browser (HTML5 Canvas, ohne Abhängigkeiten, ohne Build-Schritt).

Fahre deinen Linienbus durch eine belebte Stadt, halte an den Haltestellen, lass Fahrgäste
ein- und aussteigen – und versuche dabei den Fahrplan einzuhalten, ohne die Fahrgäste mit
Vollbremsungen zu verärgern, über rote Ampeln zu brettern oder den Bus zu Schrott zu fahren.

## Starten

`index.html` im Browser öffnen – fertig. Alternativ lokal servieren:

```bash
python3 -m http.server 8000
# dann http://localhost:8000 öffnen
```

## Steuerung

| Taste | Aktion |
|---|---|
| ↑ / W | Gas |
| ↓ / S | Bremse, im Stand: rückwärts |
| ← → / A D | Lenken |
| H / Leertaste | Hupe |
| P / Esc | Pause |
| M | Ton an/aus |

Auf Touch-Geräten erscheinen Bildschirm-Tasten.

## Spielprinzip

- **Haltestellen:** Die nächste Haltestelle ist grün markiert (Karte, Minikarte, Pfeil am
  Bildschirmrand und gestrichelte Navigationslinie). Halte in Fahrtrichtung in der Bucht an –
  die Türen öffnen sich automatisch. Fährst du zu früh los, bleiben Fahrgäste zurück.
- **Fahrplan:** Pünktliche Ankunft bringt Bonus, Verspätung kostet Geld und Stimmung.
- **Stimmung:** Harte Bremsungen, schnelle Kurven, Raserei und Unfälle verärgern die
  Fahrgäste. Fällt die Stimmung auf 0, bist du gefeuert. Gute Laune bringt Trinkgeld.
- **Schaden:** Unfälle mit Autos oder Gebäuden beschädigen den Bus – bei 100 % ist Schluss.
- **Ampeln:** Bei Rot über die Kreuzung = Bußgeld.

## Linien

1. **Erste Schicht** – ruhiger Einstieg
2. **Berufsverkehr** – viel Verkehr, volle Haltestellen
3. **Regentag** – längerer Bremsweg, rutschige Kurven
4. **Nachtlinie** – nur Scheinwerfer und Straßenlaternen
5. **Bus Maniac** – knapper Fahrplan, Chaos überall

Jede Linie wird mit bis zu drei Sternen bewertet; Fortschritt und Bestwerte werden lokal im
Browser gespeichert.

## Aufbau

- `index.html` – Seite, HUD und Menüs
- `style.css` – Gestaltung (inkl. Mobil-Layout)
- `game.js` – Spiellogik: Stadtgenerator, Fahrphysik, Verkehrs-KI mit Ampeln,
  Haltestellen/Fahrgäste, Navigation, Rendering, Sound (Web Audio)
