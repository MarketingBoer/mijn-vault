# AI Team — Dynamisch Multi-Model Routing

> Laatste update: 2026-02-25
> Skill: `~/.claude/skills/ai-team/SKILL.md`
> Activeer met: `/ai-team`

## Het Team

| Model | Commando | Rol | Kosten/1M tokens |
|---|---|---|---|
| **Claude Opus 4.6** | *(actief in sessie)* | Lead / Coder / Architect — eindverantwoordelijk, alle beslissingen, planning | $15 in / $75 out |
| **Grok 4** | `~/ask_grok.sh "..."` | Adversarial Reviewer — challenge aannames, edge cases, security | $0.20 in / $0.50 out |
| **Gemini 3.1 Pro Preview** | `gemini -p "..." --model gemini-3.1-pro-preview` | Co-Architect + Bulk Generator — second opinion architectuur, complexe research, bulk taken | $0.30 in / $2.50 out |

> GPT-5 Nano (`n-gpt`) verwijderd uit workflow (2026-02-21) — output kwaliteit te laag.

## Kernprincipe: Dynamische Rolverdeling

Geen vaste modi meer (Lite/Normal/Heavy zijn vervangen). Bij elke `/ai-team` activatie:

1. **Claude analyseert de taak** (type, complexiteit, risico)
2. **Claude stelt teamplan voor** — welke modellen nodig zijn (1, 2 of 3), welke rol per model, waarom
3. **User bevestigt** → Claude voert uit

### Universeel inzetbaar

Het team werkt voor ELKE taak — niet alleen code:

| Taak | Teamadvies |
|------|-----------|
| SEO artikel schrijven | Claude schrijft → Grok reviewt op zwakke claims en kannibalisatie |
| Landing page HTML/CSS | Claude bouwt → Gemini genereert bulk content varianten → Grok reviewt UX |
| Game architectuur | Claude ontwerpt → Gemini second opinion → Grok challenge edge cases |
| Simpele bugfix | Claude solo — geen team nodig |
| Database migratie | Claude ontwerpt → Gemini genereert seeds → Grok reviewt security |
| Concurrentie-analyse | Gemini bulk research → Claude analyseert → Grok challenge conclusies |
| Blogpost herschrijven | Claude herschrijft → Grok reviewt op AI-detectie en originaliteit |
| Strategie/business | Claude formuleert → Grok tegenargumenten → Gemini optioneel voor marktdata |

### Adviesformat

Claude presenteert altijd bij activatie:
```
TAAK: [wat de user vraagt]
TEAMADVIES:
- Claude: [rol voor deze taak]
- Grok: [rol, of "niet nodig — reden"]
- Gemini: [rol, of "niet nodig — reden"]
ALTERNATIEF: [goedkopere optie als die er is]
```

## Wanneer welk model

### Grok inzetten wanneer:
- Review/check nodig (code, content, strategie)
- Aannames gechallenged moeten worden
- Security of risico's beoordeeld moeten worden
- Tweede mening vanuit andere model-familie

### Gemini inzetten wanneer:
- Bulk output nodig (>200 regels)
- Grote context analyseren (hele codebases, lange documenten)
- Architectuur second opinion
- Complexe research over meerdere bronnen

### Claude solo wanneer:
- Simpel en laag risico
- Geen review of bulk nodig
- Snelheid > extra checks

## Configuratie

| Wat | Locatie |
|---|---|
| Gemini settings | `~/.gemini/settings.json` |
| Gemini API key | `GEMINI_API_KEY` in `~/.bashrc` |
| AI Team skill | `~/.claude/skills/ai-team/SKILL.md` |
| CLAUDE.md referentie | `~/.claude/CLAUDE.md` |
| Memory referentie | `~/.claude/projects/-home-wiz/memory/MEMORY.md` |

## Upgrade Historie Gemini

| Datum | Model |
|---|---|
| Initieel | gemini-2.0-flash |
| 2026-02-21 | gemini-2.5-flash |
| 2026-02-25 | **gemini-3.1-pro-preview** |

## Wijzigingen 2026-02-25

- Vaste modi (Lite/Normal/Heavy) → **dynamische rolverdeling** per taak
- Gemini rol: "Bulk Analist" → **Co-Architect + Bulk Generator**
- Scope: code-only → **universeel** (SEO, design, strategie, content, etc.)
- Claude adviseert nu per taak welke modellen nodig zijn (1, 2 of 3)
- Nano definitief uit alle documentatie

## Reality Check — Verplichte Stap (nieuw, 2026-02-25)

**Wanneer:** Bij ELKE taak met visuele elementen, kaarten, locaties, afbeeldingen, of real-world referenties.

**Waarom:** AI-modellen (inclusief reviewers) missen systematisch feitelijke visuele fouten — ze reviewen code/structuur maar verifiëren niet of output klopt met de werkelijkheid.

**Verplichte checks:**
1. **Geografische positionering** — Staat pin/marker op juiste locatie?
2. **Landmark herkenning** — Worden gebouwen/torens correct geïdentificeerd?
3. **Screenshot-verificatie** — ALTIJD screenshot nemen, niet blind op CSS vertrouwen
4. **Real-world factcheck** — Kloppen feiten, namen, adressen?
5. **Vraag de user** bij twijfel over lokale kennis

**Grok prompt uitgebreid met:**
> "Are there any FACTUAL or VISUAL errors? (positions on maps, landmark identifications, real-world accuracy)"

### Incident Log

| Datum | Incident | Oorzaak | Modellen betrokken |
|---|---|---|---|
| 2026-02-25 | Pulserende stip stond niet op Emmeloord op NOP-kaart | Geen visuele verificatie tegen werkelijke geografie, alleen code-review | Claude + Gemini + Grok (alle 3 gemist) |

## Harde Regels (altijd)

- NOOIT output van externe modellen verzinnen — letterlijk citeren
- NOOIT secrets extern verzenden zonder redactie
- NOOIT code/content wijzigen zonder bevestiging
- NOOIT pushen/committen zonder toestemming
- Grok timeout: kan >60s duren, korte vragen (<500 woorden)
- Modellen ALLEEN aanroepen als `/ai-team` actief is
- ALTIJD Reality Check uitvoeren bij visuele/geografische output
