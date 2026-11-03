# Jägerteich – Vereins-App (Testversion)

Klickbare Testversion der Vereins-App: Tauschbörse, Termine, Wegelicht, Temperaturen.
Sie läuft als Web-App (PWA) im Browser, lässt sich wie eine App installieren und funktioniert offline.

**Wichtig:** Alles, was jemand einträgt, bleibt nur auf dem eigenen Handy.
Andere sehen fremde Einträge nicht. Das kommt erst mit dem Server (PocketBase) in der echten Version.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | die App |
| `sw.js` | Offline-Cache (Service Worker) |
| `manifest.webmanifest`, `icon-192.png`, `icon-512.png` | Installation als App |
| `ANLEITUNG.md` | diese Anleitung |

## 1. Auf GitHub Pages stellen

Wie beim Stundenbuch:

1. github.com → **+** → **New repository** → Name `jaegerteich-app`, **Public**, Haken bei „Add a README file“ → **Create repository**.
2. **Add file → Upload files** → die 5 Dateien aus der ZIP hineinziehen (nicht den Ordner, nicht die ZIP) → **Commit changes**.
3. **Settings** (Reiter oben, rechts neben „Insights“) → **Pages** → Source **Deploy from a branch**, Branch **main**, Ordner **/ (root)** → **Save**.
4. Nach 1–2 Minuten läuft die App unter:
   **https://mavrogray.github.io/jaegerteich-app/**

Im Repo liegt nur Programmcode mit Beispieldaten, keine echten Vereinsdaten.

## 2. An den Vorstand weitergeben

Einfach die Adresse schicken. **Kein Konto nötig**, weder bei Claude noch bei GitHub.

Auf dem Android-Handy:
1. Adresse in **Chrome** öffnen.
2. Menü ⋮ → **App installieren** bzw. **Zum Startbildschirm hinzufügen**.
3. Über das neue Blatt-Symbol starten, Gartennummer eingeben, fertig.

Auf dem iPhone: in Safari öffnen → Teilen → **Zum Home-Bildschirm**.

## 3. Was ist echt, was simuliert?

| Bereich | In der Testversion |
|---|---|
| Tauschbörse | funktioniert, Einträge anlegen und eigene löschen; nur auf dem eigenen Gerät |
| Nachricht an Garten | Hinweis, noch ohne Funktion |
| Termine | feste Beispiele |
| Wegelicht | Countdown, 15 min Pause, Protokoll; „Vereins-WLAN“ und „dunkel“ per Schalter simuliert, **schaltet kein echtes Licht** |
| Temperaturen | feste Beispielwerte |
| Anmeldung | nur Gartennummer; später Code pro Garten, derselbe wie der WLAN-Voucher |

Einträge verschwinden nach 4 Wochen von selbst. Unten auf der Startseite lassen sich die Testdaten zurücksetzen.

## 4. Update der App

1. Neue Dateien ins Repo hochladen (alte überschreiben).
2. In `sw.js` die Zeile `const VERSION = "jaegerteich-v1";` hochzählen (v2, v3 …), sonst bleibt die alte Version im Cache.
3. App mit Internet zweimal neu öffnen.

Die Testdaten auf den Handys bleiben bei einem Update erhalten.
