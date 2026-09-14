# Trainingsprotokoll als App aufs iPhone

## Was hier drin ist

| Datei | Wofür |
|---|---|
| `index.html` | die komplette App – Code, Styles und Plan stecken alle in dieser einen Datei |
| `manifest.json` | Name, Icon, Farben, Vollbildmodus |
| `sw.js` | Service Worker: macht die App offline nutzbar |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | Icons für den Home-Bildschirm |
| `apple-touch-icon.png` | Icon speziell für iOS |

Alle Dateien müssen zusammen in **einem** Ordner liegen – nicht in Unterordner sortieren.

---

## Variante A – GitHub Pages (dauerhaft, kostenlos)

1. Auf **github.com** anmelden (oder Account anlegen).
2. Oben rechts **+ → New repository**.
   - Name: `trainingsprotokoll`
   - Sichtbarkeit: **Public** (bei kostenlosen Accounts funktioniert Pages nur mit Public)
   - **Create repository**
3. Auf der leeren Repo-Seite: **uploading an existing file** anklicken.
4. Alle Dateien aus diesem Ordner ins Browserfenster ziehen → unten **Commit changes**.
5. **Settings → Pages** (linke Spalte).
   - Source: **Deploy from a branch**
   - Branch: `main`, Ordner `/ (root)` → **Save**
6. 1–2 Minuten warten, Seite neu laden. Oben steht dann deine Adresse:
   `https://DEIN-NAME.github.io/trainingsprotokoll/`
7. Diese Adresse auf dem iPhone in **Safari** öffnen.
8. Teilen-Symbol (Quadrat mit Pfeil) → **Zum Home-Bildschirm** → Name z. B. „Training" → **Hinzufügen**.

Fertig. Das Icon liegt auf dem Home-Bildschirm, die App startet im Vollbild ohne Safari-Leiste.

---

## Variante B – Netlify Drop (2 Minuten, zum Ausprobieren)

1. **app.netlify.com/drop** öffnen.
2. Den Ordner ins Feld ziehen.
3. Nach ein paar Sekunden erscheint eine Adresse wie `https://irgendwas-1234.netlify.app`.
4. Diese Adresse auf dem iPhone in **Safari** öffnen → Teilen → **Zum Home-Bildschirm**.

Ohne Account bleibt die Seite nur eine begrenzte Zeit online – für einen Test reicht das,
für den Dauerbetrieb ist Variante A besser.

---

## Wichtig

- **Nur Safari.** Chrome oder Firefox auf dem iPhone können „Zum Home-Bildschirm" nicht als
  echte App anlegen.
- **Daten sind getrennt.** Die Home-Bildschirm-App hat einen eigenen Speicher, unabhängig von
  Safari. Was du vorher im Safari-Tab eingetragen hast, ist in der App nicht da – also erst
  installieren, dann loslegen.
- **Regelmäßig exportieren.** Die Trainings liegen nur auf dem iPhone. Wenn du in den
  Safari-Einstellungen „Website-Daten löschen" antippst, sind sie weg. Nach jeder Einheit
  läuft der Export sowieso automatisch los.
- **Offline.** Nach dem ersten Start funktioniert die App auch ohne Netz – praktisch im Keller
  oder im Gym.

---

## Update einspielen

Wenn eine neue Version der App kommt:

1. In `sw.js` die Zeile `const VERSION = "v1";` auf `"v2"` ändern (bei jedem Update weiterzählen).
2. Die geänderten Dateien wieder ins Repo hochladen (GitHub: **Add file → Upload files**,
   gleiche Dateinamen → überschreibt automatisch).
3. App auf dem iPhone schließen und neu öffnen – der neue Stand ist da.

Die eingetragenen Trainings bleiben dabei erhalten.
