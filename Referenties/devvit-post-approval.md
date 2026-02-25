# Devvit Post-Approval Referentie
> Compact overzicht voor wanneer je actief bezig bent met Devvit games.

---

## Pipeline: Upload → Publish → Listed

| Stap | Commando | Status | Installatie |
|---|---|---|---|
| Upload | `npx devvit upload` | Private | Alleen subreddits <200 leden |
| Publish | `npx devvit publish` | Under Review | Wacht op App Review |
| Approved | — | Approved | Moderator-installatie mogelijk |
| Listed | `npx devvit publish --public` | Public | Zichtbaar in App Directory |

**Approved ≠ Listed.** Een app kan approved zijn maar nog niet zichtbaar in de directory (incomplete metadata, experimentele features, of handmatige flip nodig).

## Versie-escalatie

```bash
npx devvit upload --bump patch   # bugfixes
npx devvit upload --bump minor   # nieuwe features
npx devvit upload --bump major   # breaking changes
```

## Settings & Secrets

```bash
npx devvit settings set <key>    # API keys (versleuteld, onzichtbaar voor mods)
npx devvit settings list         # huidige config bekijken
```

Scope: `SettingScope.App` = alleen ontwikkelaar, `SettingScope.Installation` = per subreddit (mod-configureerbaar).

## Installatie & Monitoring

```bash
npx devvit install <subreddit>          # installeer op community
npx devvit list installs                # overzicht installaties
npx devvit logs <subreddit>             # live monitoring
npx devvit logs <subreddit> --since 15m # events rond incident
npx devvit logs <subreddit> --verbose   # timestamps + logniveaus
```

**Limieten:** 30 sec per request, 4MB payload max. Logs: 5.000 events of 7 dagen retentie.

## Re-reviews (je goedkeuring is niet permanent)

| Trigger | Wat gebeurt er |
|---|---|
| Nieuwe versie publishen | Elke code-wijziging vereist nieuwe review |
| Willekeurige controle | Reddit checkt live apps steekproefsgewijs |
| Beleidswijziging | Reddit kan herbeoordelingen eisen |
| High-risk features activeren | `http fetch`, `payments` → intensievere review |

**Handhaving:** feedback → schorsing → ban (bij ernstige schending).

## Developer Funds — Groei-metrics

| Metric | Betekenis |
|---|---|
| Qualified Engagers | Gebruikers met "betekenisvolle interactie" (niet alleen clicks) |
| 14-daags gemiddelde | Metrics over 14 dagen (niet 7) — vlakt pieken af |
| Qualified Installs | Subreddits waar app actief wordt *gebruikt* |

**Tip:** Ontwerp games met diepgang en herhaalde acties, niet eenmalige clicks.

## Compliance Essentials

- **Privacy:** Anonimiseer usernames naar externe servers, data-minimalisatie, gebruiker moet data kunnen verwijderen
- **Moderatie:** Alle user-generated content moet door mods controleerbaar zijn
- **Bots:** Geautomatiseerde accounts moeten transparant gemarkeerd zijn
- **`runAs: 'USER'`:** Na approval neemt dit de echte user-identiteit aan (niet meer het app-account)

## Logged-out Users

- Gate acties achter login-prompt: "Log in om deel te nemen"
- Gebruik `localStorage` voor tijdelijke sessie-ID's (wordt gewist bij app-update)
- Test in incognito-venster op publieke/restricted subreddit

## Community & Support

- **Feedback Friday** op r/Devvit
- **r/GamesOnReddit** voor cross-posting en bèta-launches
- **Discord:** developers.reddit.com/discord
- **Escalatie:** Modmail via r/Devvit als review >1 week duurt
