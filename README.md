# Portfolio — Yauheni Vesialukha

Persönliche Portfolio-Website, aufgebaut als Analytics-Dashboard.
Statische Seite ohne Build-Schritt: reines HTML, CSS und JavaScript.

**Live:** https://yauhenivesialukha.netlify.app

---

## Struktur

```
.
├── index.html          Deutsche Fassung (Startseite)
├── en.html             Englische Fassung
├── Yauheni_Vesialukha_CV.pdf
├── og-image.png        Linkvorschau Deutsch (1200×630)
├── og-image-en.png     Linkvorschau Englisch (1200×630)
├── favicon.svg
├── favicon-32.png
├── apple-touch-icon.png
├── robots.txt
├── sitemap.xml
├── netlify.toml        Publish-Verzeichnis und Cache-Regeln
└── .gitignore
```

Beide HTML-Dateien sind eigenständig: CSS und JavaScript stehen direkt darin.
Bilder, Porträt und Hero-Video liegen auf Cloudinary und werden von dort geladen.

---

## Deployment

### Netlify (empfohlen)

1. Repository auf GitHub anlegen und diesen Ordner hochladen.
2. In Netlify **Add new site → Import an existing project → GitHub** wählen.
3. Repository auswählen. Build-Command bleibt leer, Publish-Verzeichnis ist `.`
   — beides steht bereits in `netlify.toml`.
4. Nach jedem Push auf `main` veröffentlicht Netlify automatisch neu.

### GitHub Pages

Settings → Pages → Branch `main`, Ordner `/ (root)`.
Danach in allen Meta-Tags, in `robots.txt` und in `sitemap.xml`
die Domain auf `https://<user>.github.io/<repo>/` anpassen.

---

## Bei einem Domainwechsel anpassen

Die Adresse steht an mehreren Stellen und muss überall gleich sein,
sonst zeigt die Linkvorschau ins Leere:

- `index.html` und `en.html`: `canonical`, `hreflang`, `og:url`,
  `og:image`, `twitter:image` sowie der `JSON-LD`-Block im `<head>`
- `robots.txt`: Sitemap-Zeile
- `sitemap.xml`: alle `<loc>`- und `hreflang`-Einträge

---

## Inhalte pflegen

Texte stehen doppelt — einmal in `index.html`, einmal in `en.html`.
Änderungen an Zahlen, Projekten oder Formulierungen also in **beiden**
Dateien nachziehen.

Lebenslauf ersetzen: neue Datei unter demselben Namen ins Wurzelverzeichnis legen,
dann bleiben die vier Verweise auf der Seite unverändert.

Projektbilder tauschen: Datei zu Cloudinary hochladen und die URL im
jeweiligen `<img src="...">` ersetzen. Die Parameter
`f_auto,q_auto,w_1200,e_sharpen:70` sollten erhalten bleiben —
sie liefern Format, Kompression und Schärfe passend zum Endgerät.

---

## Technisches

- Zwei Themes (hell und dunkel), Umschalter oben rechts, Wahl wird
  im Browser gespeichert; beim ersten Besuch entscheidet die Systemeinstellung
- Sprachumschaltung über getrennte Adressen, verknüpft per `hreflang`
- Bewegung: Einblendungen, hochzählende Kennzahlen, Zeichnen der
  Retention-Kurve, gestaffelte Balken in der Laufbahn — alles reagiert auf
  `prefers-reduced-motion` und schaltet sich bei Bedarf vollständig ab
- Ohne JavaScript bleiben alle Inhalte sichtbar; Animationen sind reine Zugabe
- Eigene Druckfassung: heller Hintergrund, ohne Navigation und Video,
  mit ausgeschriebenen Projektlinks
- Responsiv über sieben Breakpoints von 1400 px bis 380 px

---

## Rechtliches

Quellcode frei verwendbar. Inhalte, Porträt, Lebenslauf und Projektgrafiken
sind persönliche Daten und nicht zur Weiterverwendung freigegeben.
