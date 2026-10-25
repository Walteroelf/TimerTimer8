# TimerTimer8

Eine Unterrichts-Eieruhr für das iPad: **rote Arbeitszeit, danach grüne Auszeit**.
Die Lehrkraft kann die Auszeit jederzeit spontan verlängern oder kürzen, zum Beispiel wenn ein Schüler gut oder gar nicht arbeitet.

**App öffnen:** https://walteroelf.github.io/TimerTimer8/

Weiterentwicklung von [TimerTimer7](https://github.com/Walteroelf/TimerTimer7). TimerTimer7 bleibt unverändert.

---

## Die zwei Grundregeln

1. **Die Auszeit lässt sich immer verstellen, auch während der Timer läuft.** Das ist das Kernstück des Timers.
2. **Das Ende der Stunde ist fest.** Es lässt sich nur einstellen, solange der Timer pausiert ist. Plus und Minus verschieben nur das Verhältnis von Arbeitszeit zu Auszeit, das Ende bleibt immer gleich.

---

## Bedienung

### Einstellen (Timer steht)
- **Blauer Griff:** Ende der Stunde, also die Gesamtzeit (bis 119 Minuten). Bis 60 Minuten läuft die Zeit auf dem äußeren Ring, darüber zusätzlich auf dem inneren Ring.
- **Schwarzer Griff:** Grenze zwischen Arbeitszeit und Auszeit.
- **Zielzeit:** In der Mitte stehen die Gesamtzeit und die Uhrzeit, zu der der Timer endet.
- **Tippschutz:** Ein Tipp auf die Zeitanzeige in der Mitte verstellt nichts.

### Knöpfe unter der Scheibe
| Knopf | Funktion | Sichtbar |
|---|---|---|
| ▶ / ❚❚ | Start / Pause | immer |
| ↺ | Zurücksetzen auf 45 min, davon 10 min Auszeit | nur wenn der Timer steht |
| 🔊 | Ton an/aus (aus = orange). Stumm gilt für alle Töne und die Vibration, die Anzeigen bleiben. | nur wenn der Timer steht |
| QR | Lehrer-iPad verbinden (siehe unten) | nur wenn der Timer steht |

Solange der Timer läuft, sieht er so schlicht wie möglich aus: nur Scheibe, Start/Pause und die Auszeit-Tasten.

### Auszeit + / − (rechts bzw. unten)
- **+** verlängert die Auszeit um 1 Minute, die Arbeitszeit wird entsprechend kürzer.
- **−** kürzt die Auszeit um 1 Minute, die Arbeitszeit wird länger.
- **Ende bleibt fest:** Das funktioniert jederzeit, auch während die Auszeit schon läuft. Das Ende bleibt dabei immer gleich, deshalb kann + die Auszeit nie über das Stundenende hinaus verlängern.
- **Grünes Feld:** Es zeigt die Auszeit-Minuten, die noch kommen.
- **Rückmeldung für den Schüler:** Groß erscheint „+1“ oder „−1“ auf der Scheibe, schnelle Folgedrücke werden zusammengezählt (z. B. „−3“). Dazu gibt es einen eigenen kurzen Ton. Bei + fliegt außerdem ein Stern ins grüne Feld.

### Signale während des Laufs
| Zeitpunkt | Signal |
|---|---|
| 1 Minute vor Ende der Arbeitszeit | sanfter Doppelton, grüner Bogen pulsiert |
| Beginn der Auszeit | Gong, große Einblendung **AUSZEIT!** |
| 1 Minute vor Ende der Auszeit | sanfter Doppelton, grüner Bogen pulsiert |
| Ende | dreifacher Gong, große Einblendung **FERTIG!** |

Das Display bleibt an, solange der Timer läuft.

---

## Fernsteuerung mit dem Lehrer-iPad (QR-Code)

So verstellst du die Auszeit vom eigenen iPad aus, ohne zum Schüler-iPad zu gehen.

1. **Schüler-iPad:** Bei stehendem Timer auf den **QR-Knopf** tippen.
2. **Lehrer-iPad:** Den QR-Code mit der normalen **Kamera** scannen und den Link öffnen. Es erscheint die Lehrer-Steuerung.
3. Oben steht dann „Verbunden“. Auf dem Schüler-iPad steht „Lehrer-iPad verbunden ✓“, und bei stehendem Timer leuchtet oben links ein kleiner grüner Punkt.
4. Auf dem Schüler-iPad mit **Fertig** das Fenster schließen.

**Was die Lehrer-Steuerung kann:**

*Immer:*
- den Timer des Schülers live sehen: Phase, Restzeit, Auszeit-Minuten und Ende
- **− Auszeit / + Auszeit** auslösen; auf dem Schüler-iPad erscheinen dann „±1“, Ton und Stern
- **Start / Pause** auslösen

*Nur wenn der Timer pausiert ist oder steht (Grundregel 2):*
- **Stundenende** mit −5 / −1 / +1 / +5 Minuten verschieben
- **Stundenende** direkt als Uhrzeit setzen, z. B. „12:00“, dann **Ende setzen**
- **↺ Zurücksetzen** auf 45 Minuten mit 10 Minuten Auszeit, mit Rückfrage
- **Ton** am Schüler-iPad an- oder ausschalten

Läuft der Timer, blendet die Lehrer-Seite diese Einstellungen aus. Das Schüler-iPad würde solche Befehle dann auch ablehnen.

**Gut zu wissen:**
- **Das Schüler-iPad bleibt der eigentliche Timer.** Bricht die Verbindung ab, läuft es normal weiter. Die Lehrer-Seite verbindet sich automatisch neu.
- **Der Code bleibt gleich**, auch wenn das Schüler-iPad neu geladen wird. Die Lehrer-Seite kann also offen bleiben.
- **Neuer Code** erzeugt einen frischen QR-Code, damit ist der alte ungültig. **Fernsteuerung aus** beendet die Verbindung ganz.
- **Ohne QR-Code verbinden:** Öffne https://walteroelf.github.io/TimerTimer8/lehrer.html und gib den Code ein, der unter dem QR-Code steht.
- **Ton nach Neuladen:** Wurde das Schüler-iPad neu geladen, kommt der Ton erst wieder, wenn einmal jemand auf das Schüler-iPad getippt hat. Das verlangt iOS.

**Technik und Datenschutz:**
- Die beiden iPads verbinden sich direkt miteinander (WebRTC).
- Nur für den Verbindungsaufbau wird der kostenlose öffentliche Vermittlungsdienst von PeerJS (peerjs.com) benutzt.
- Übertragen werden nur Zeiten und Tastendrücke, keine Namen und keine Schülerdaten.
- Der Code ist zufällig erzeugt.
- Beide iPads brauchen Internet. Sperrt das Schul-WLAN Direktverbindungen zwischen Geräten, klappt die Fernsteuerung dort nicht. Der Timer selbst funktioniert trotzdem.

---

## Auf dem iPad installieren und offline nutzen

1. Die App in **Safari** öffnen: https://walteroelf.github.io/TimerTimer8/
2. **Teilen → „Zum Home-Bildschirm“** wählen.
3. Ab dann startet die App vom Home-Bildschirm auch **ohne Internet**. Nur die Fernsteuerung braucht Internet.

Mit Internet lädt die App automatisch die neueste Version.

**Hinweise:**
- Töne gibt es nur, wenn der Stummschalter bzw. „Stumm“ im Kontrollzentrum aus ist.
- Vibration unterstützt Safari auf iPhone und iPad nicht.

---

## Dateien

| Datei | Inhalt |
|---|---|
| `index.html` | der Timer (Schüler-iPad), alles in einer Datei |
| `lehrer.html` | die Lehrer-Steuerung für die Fernsteuerung |
| `sw.js` | Service Worker für die Offline-Nutzung |
| `manifest.json` | App-Angaben für den Home-Bildschirm |
| `timer-icon.png` | App-Symbol |

Die Einstellungen (Gesamtzeit, Auszeit, Ton an/aus, Fernsteuerungs-Code) werden nur lokal auf dem Gerät gespeichert.
