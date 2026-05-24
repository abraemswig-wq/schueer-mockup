# Schüer Immobilien — Site-Architecture

> Vorgeschlagene Seitenstruktur für die vollständige Webseite (über den Landing-Mockup hinaus).

## Hierarchie

```
/                                  Landing (vorhanden)
│
├── /ueber-uns                     Familie, Werte, Team
│   ├── /ueber-uns/team            Mitarbeiter-Übersicht mit Portraits
│   └── /ueber-uns/chronik         Vollständige Zeitleiste 1990 → heute
│
├── /leistungen                    Übersicht der 3 Säulen
│   ├── /leistungen/planung        Projektentwicklung, Referenzobjekte
│   ├── /leistungen/vermietung     Prozess, Bewerbungsunterlagen
│   └── /leistungen/verwaltung     WEG, Miet, SE — Detail je Variante
│
├── /objekte                       Verfügbare Objekte (Filterbar)
│   └── /objekte/[slug]            Einzelobjekt mit Bildergalerie + Floorplan
│
├── /fuer-mieter                   Mieter-Self-Service-Hub
│   ├── /fuer-mieter/formulare     Download: Selbstauskunft, Übergabeprotokoll
│   ├── /fuer-mieter/anliegen      Online-Formular für Mängelmeldung
│   └── /fuer-mieter/uebergabe     Termin-Buchung Wohnungsübergabe
│
├── /karriere                      Übersicht Stellenanzeigen
│   └── /karriere/[stelle]         Einzelne Stellenanzeige + Bewerbung
│
├── /kontakt                       Adresse, Anfahrt, Formular, Karte
│
├── /datenschutz                   Pflicht
├── /impressum                     Pflicht
└── /faq                           (Sektion auf /, evtl. eigene Seite)
```

## Navigationsstruktur

### Primary Nav (Header)
1. **Über uns** → `/ueber-uns`
2. **Leistungen** → `/leistungen` (Mega-Menü: Planung / Vermietung / Verwaltung)
3. **Objekte** → `/objekte`
4. **Für Mieter** → `/fuer-mieter`
5. **Karriere** → `/karriere`

CTA rechts: **Kontakt** → `/kontakt` (sticky)

### Footer-Sekundär-Nav
- Leistungen: Planung · Vermietung · Verwaltung · Neubauten
- Service: Für Mieter · Formulare · Objekte · Karriere
- Kontakt: Telefon · E-Mail · Adresse
- Rechtliches: Datenschutz · Impressum

## URL-Konvention

- Lowercase, Bindestriche
- Deutsche Begriffe (kein Englisch in URLs)
- Trailing-Slash optional (für GitHub Pages besser ohne)

## Wichtigste 3 Templates (bei Webflow-Umsetzung)

1. **Marketing Page** — Hero + Editorial-Sections (wie Landing)
2. **Objekt-Detail** — Galerie, Floorplan, Lagekarte, Kontakt-Box
3. **Listing/Index** — Filterbar (Stadtteil, Zimmer, m², Preis) + Card-Grid

## Cross-Links (Interne Verlinkung für SEO)

- Hero-CTA „Objekte ansehen" → `/objekte`
- Leistungs-Cards → jeweilige Detailseite
- Zitat-Section → `/ueber-uns/chronik`
- FAQ-Antworten verlinken auf relevante Detailseiten
- Footer-Wordmark → `/`

## SEO-Title-Pattern

| Seite | Title |
|-------|-------|
| `/` | Schüer Immobilien — Planung, Vermietung & Verwaltung in Münster & Coesfeld |
| `/leistungen/verwaltung` | Hausverwaltung in Münster & Coesfeld — Schüer Immobilien |
| `/objekte` | Aktuelle Wohnungen in Münster & Coesfeld — Schüer Immobilien |
| `/karriere` | Karriere im Familienunternehmen — Schüer Immobilien |
| `/ueber-uns` | Familienunternehmen seit 1990 — Über Schüer Immobilien |

## Conversion-Mapping

| Seite | Primärer CTA | Sekundärer CTA |
|-------|--------------|----------------|
| `/` | Unsere Objekte | Kontakt |
| `/leistungen/*` | Erstgespräch buchen | Mehr erfahren |
| `/objekte/[slug]` | Besichtigung buchen | Bewerbungsunterlagen |
| `/karriere/[stelle]` | Jetzt bewerben | Mehr zur Stelle |
| `/fuer-mieter` | Anliegen melden | Formulare |
| `/kontakt` | Anrufen / Schreiben | — |

## Lokale SEO — Stadtteil-Landingpages (Phase 2)

Programmatisch generierbare Seiten für Long-Tail-Suche:
- `/münster/hiltrup` — Immobilienverwaltung in Hiltrup
- `/münster/kreuzviertel`
- `/münster/gievenbeck`
- `/coesfeld/lette`
- `/rosendahl/holtwick`

Template-basiert mit identischer Struktur + lokalem Content.

## Phasenplan

**Phase 1 (MVP nach Mockup-Freigabe):** `/`, `/leistungen`, `/objekte`, `/kontakt`, `/karriere`, `/datenschutz`, `/impressum`

**Phase 2:** `/ueber-uns/*`, `/fuer-mieter/*`, einzelne Objekt-Detailseiten

**Phase 3:** Stadtteil-Landingpages, Mieter-Portal-Login, evtl. Blog/Ratgeber
