# HELLFIRE LAN – mit Story-Modus

Koop-Shooter (Raycaster) für den Browser. Koop und Deathmatch sind wie vorher, neu ist der **Story-Modus im Duo**.

## Starten

- **Lokal:** `index.html` doppelklicken. Fertig.
- **Online:** Den kompletten Ordner bei einem beliebigen Hoster für statische Seiten hochladen
  (z. B. GitHub Pages, Netlify oder itch.io als HTML5-Spiel). Es gibt keinen Server-Teil –
  nur Dateien. Wichtig ist, dass `index.html` im Hauptordner liegt und die Ordner `js`, `css`
  und `assets` daneben.
- **Zu zweit:** Einer klickt auf „Story-Modus“, wählt seinen Charakter und schickt den
  4-stelligen Raum-Code. Der Partner klickt auf „Beitreten“, wählt seinen Charakter und gibt
  den Code ein. Beide brauchen Internet (die Verbindung läuft direkt zwischen euch über PeerJS).

## Story-Modus

| Level | Karte | Wellen | Boss | Song |
|---|---|---|---|---|
| 1 | Arena | 5 | Lil M | Fühle mich wie Chief Keef 2012 |
| 2 | Ringlabyrinth | 10 | Drachenlord | Skrrr Skrrr |
| 3 | Bunker | 15 | SehrJamal | 17 |
| 4 | Kathedrale | 20 | Jermaine | Cracker |
| 5 | Präsidentenstraße | 25 | Raphael | ballack |
| 6 | Ultimative Kampf Arena Bonn | 30 | Slimee Rebel | fur.jacket.swag.for.real |

- Start nur mit Faust und Pistole. Nach jedem Level: Case Opening (neue Waffe für beide), danach meldet sich Slime.
- 3 gemeinsame Leben pro Level, Münzen sammeln: 50 Münzen = 1 Extraleben.
- Checkpoint alle 5 Wellen und direkt vor dem Boss. Bei Game Over geht es am Checkpoint weiter, die Waffen bleiben.
- Der Fortschritt wird im Browser des Hosts gespeichert („Fortsetzen“).
- `Enter`, `Leertaste` oder Klick: Dialoge und Bildschirme weiter.

## Aufbau

```
index.html            Menü
css/style.css         Aussehen des Menüs
js/game.js            Engine: Karten, Waffen, Gegner, Netzwerk, Grafik
js/story.js           Story-Modus: Level, Bosse, Wellen, Case Opening, Slimes Texte
js/peerjs.min.js      Netzwerk-Bibliothek (liegt lokal bei, kein CDN nötig)
assets/sprites/*.png  Charaktere, Gegner, Bosse
assets/music/*.mp3    ein Song pro Level
```

## Schnell anpassen (alles oben in `js/story.js`)

- `LEVELS` – Karte, Name und Song pro Level
- `WAVES_PER_LEVEL` – 5 bedeutet 5/10/15/20/25/30 Wellen
- `BOSS` – Leben, Tempo und Angriffe der Bosse
- `CASEP` – welche Waffen nach welchem Level in der Kiste sein können
- `DLG` – Slimes Sprüche
