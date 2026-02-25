# Projecten Index — Single Source of Truth
> Geconsolideerd uit `~/.claude/projects/-home-wiz/memory/`
> Laatste update: 2026-02-25

---

## Devvit Games (Reddit)

### CityBlock
- **Type**: Top-down community life sim (GTA 1 × Stardew Valley)
- **Pad**: `/home/wiz/cityblock/`
- **Slug**: `cityblok` | **App**: developers.reddit.com/apps/cityblok
- **Subreddits**: r/cityblok_dev (dev), r/Cityblok (live)
- **Stack**: Phaser 3.90 + Hono server + Vite, arcade physics, 960×640
- **Status**: v0.0.21 live, 7 zones klaar (Forest, Residential, Market, Industrial, Commercial, Beach, Park)
- **Key**: zone-based scenes, atlas sprites, vehicles (E-toets), day/night cycle, waypoint NPCs
- **Memory**: [cityblock-devvit.md](/.claude/projects/-home-wiz/memory/cityblock-devvit.md)

### Snap Judge
- **Type**: Western-themed arcade shooter (5 game modes)
- **Pad**: `~/snap-judge/`
- **GitHub**: MarketingBoer/snap-judge | **App**: `snapjudgedev`
- **Subreddit**: r/SnapJudgeDev
- **Stack**: Single IIFE game.js (6560 regels), WebView bridge, Redis leaderboard
- **Status**: v0.0.16 deployed
- **Memory**: [snap-judge.md](/.claude/projects/-home-wiz/memory/snap-judge.md)

### Bye Bye Ducks
- **Type**: Duck Hunt clone / arcade shooter
- **Pad**: `~/Downloads/duck-hunt-devvit/`
- **Slug**: `bye-bye-ducks` | **Status**: v0.4.0 approved + PUBLIC in App Directory
- **Subreddit**: r/bye_bye_ducks_dev
- **Stack**: Canvas game (app.js ~1780 regels), Redis sorted sets
- **Memory**: [bye-bye-ducks.md](/.claude/projects/-home-wiz/memory/bye-bye-ducks.md)

### Gothicvania Platformer
- **Type**: Side-scrolling platformer (gothic horror)
- **Pad**: `/home/wiz/devvit-gothicvania/`
- **GitHub**: MarketingBoer/devvit-gothicvania (private)
- **Subreddit**: r/Gothicvania | **Status**: v0.0.5 live
- **Stack**: Canvas tilemap (4800px breed), 3-layer parallax, 5 enemy types, Redis leaderboard
- **Memory**: [gothicvania-devvit.md](/.claude/projects/-home-wiz/memory/gothicvania-devvit.md)

---

## Klant-websites (WordPress)

### MustHaveFloors.nl
- **Type**: WooCommerce vloerenshop (Flatsome theme)
- **Server**: `72.60.183.90:65002` user `u114164165`
- **GitHub**: MarketingBoer/musthavefloors (private)
- **GA4**: TBD
- **Kleuren**: zwart `#1a1a1a`, groen `#3C7C31` (CTA), oranje `#CE5400` (accent)
- **Prefix**: `mhf-` | **Skill**: `flatsome-woocommerce`
- **Homepage**: 12 secties (hero → USP → categories → popular → inspiration → reviews → trust → showroom → blog → brands → FAQ → newsletter)
- **Productpagina**: WPCode snippet #34160, offerte formulier, payment icons, trust grid
- **Mega menu**: WPCode #34261 (PHP) + #34262 (CSS), hook-based inject
- **Blog**: 26 posts gepubliceerd (regionale + thematische)
- **Deploy**: branch → commit → push → merge (NOOIT direct op main)
- **Memory**: [musthavefloors.md](/.claude/projects/-home-wiz/memory/musthavefloors.md)

### Mediadeboer.nl
- **Type**: Marketing agency site (Hello Biz theme + Elementor)
- **Server**: `72.60.183.90:65002` user `u114164165`
- **GitHub**: MarketingBoer/mediadeboer
- **Lokaal**: `/home/wiz/mediadeboer/`
- **GA4**: 250342574 | **GSC**: URL-prefix
- **Tools op site**: SEO Audit tool (iframe, Moz-style, PageSpeed API)
- **Status**: Snippet bieb faalt (0 clicks, 0 geïndexeerd), actieplan 4 fases
- **CSS-regels**: [mediadeboer-css-regels.md](/home/wiz/Vault/Klanten/mediadeboer-css-regels.md)
- **Memory**: [mediadeboer.md](/.claude/projects/-home-wiz/memory/mediadeboer.md)

### HuisenTuinSteigerhout.nl
- **Type**: WooCommerce meubelshop (steigerhout, douglas, eiken)
- **Locatie**: Zoetermeer
- **Kleuren**: blauw `#2a6496`, groen `#48a84a`
- **Memory**: [huisentuinsteigerhout.md](/.claude/projects/-home-wiz/memory/huisentuinsteigerhout.md)

### FBBouwservice.nl
- **Type**: Bouwbedrijf site (Astra + Elementor)
- **Prefix**: `dk-` | **CTA kleur**: oranje `#e85d2f`
- **Hero**: custom HTML widget, overlay nav, hamburger mobiel

### ScootOne.nl
- **Type**: E-scooter shop
- **GA4**: 443622489
- **Memory**: [scootone-general/](/.claude/projects/-home-wiz/memory/scootone-general/)

---

## GA4 Property Map

| Client | GA4 Property ID |
|---|---|
| richardhessink.com | 14287259 |
| mediadeboer.nl | 250342574 |
| nails4diva | 506387531 |
| samahair | 331734545 |
| samahair-extensions | 335830010 |
| ecotafels.nl | 506111621 |
| erotieksupermarkt | 469554080 |
| fietshome | 446213525 |
| musthavefloors.nl | TBD |
| scootone | 443622489 |

---

## Overige projecten

| Project | Pad | Beschrijving |
|---|---|---|
| Ranktracker | `~/ranktracker/`, `~/ranktracker-wp/` | SEO keyword ranktracker (Supabase + Tailwind) |
| Ranktracker Desktop | `~/ranktracker-desktop/` | Desktop versie ranktracker |
| Ranktracker MDB | `~/Ranktracker-voor-Mediadeboer/` | Klantversie voor Mediadeboer |
| Richard Hessink Dashboard | `~/projects/richard-hessink-dashboard/` | Dashboard voor klant |
| Gelasta Productanalyse | — | 500 producten geanalyseerd (vinyl/rigid/laminaat) voor MHF |

---

## Shared Server

- **IP**: `72.60.183.90` | **Poort**: `65002`
- **User**: `u114164165` (Hostinger)
- **Sites**: musthavefloors.nl, mediadeboer.nl
- **SSH**: `ssh -p 65002 u114164165@72.60.183.90`
- **Credentials**: `/home/wiz/.config/gcloud/mhf-mcp.json` (Google Service Account)

---

## Blog Schrijfregels (universeel)

1. Geen externe links overnemen
2. Altijd interne links toevoegen
3. Altijd afbeeldingen toevoegen
4. Concurrentnamen verwijderen
5. 100% uniek (plagiaat + AI-detector proof)
6. Geen AI-filler zinnen ("In de wereld van...", "Het is belangrijk om...")
7. Regionale blogs: unieke invalshoek per stad, lokale relevantie

Volledige regels: [blog-rules.md](/.claude/projects/-home-wiz/memory/blog-rules.md)
