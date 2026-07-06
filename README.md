# Mr. Clay's Lawn Care

Single-page static website (`index.html`, no build step) for a residential lawn care and landscaping business. Deployed via GitHub Pages (branch-based, `main` / root, `.nojekyll` present since this is a plain static site, not a Jekyll project).

## Page structure

Services → New Lawns → Pricing → Custom Plan Builder → Book Now.

## Business rules / pricing model

### Base per-visit services (Custom Plan Builder)

| Service | Price | Notes |
|---|---|---|
| Lawn Care | J$7,500 / visit | Base service. Includes weeding for progressive reduction and elimination of weeds. |
| Hedging | +J$2,000 / visit | |
| Watering | +J$1,000 / visit | Free when 3 or 4 visits/month are selected (see inclusion rules). |

### Treatments (priced standalone, not per visit)

| Treatment | Standalone price | Notes |
|---|---|---|
| Fertilizer Treatment | J$3,000 / treatment | Billed monthly. Free at 3-4 visits/month. |
| Pesticide Treatment | J$3,000 / treatment | Billed monthly. Free when Hedging is selected. |
| Weed Control & Removal | J$5,000 / treatment | Billed monthly. Free when Lawn Care is selected (Lawn Care already bundles weeding). |
| Topsoil Treatment | J$10,000 / 3 months | Billed quarterly, shown as a separate line from the monthly total. Free under the New Lawn Development plan. |
| Consultation/Inspection | J$3,000 / consultation | One-time. Free under the New Lawn Development plan. |

### Inclusion rules (treatments/services that become free)

These are evaluated live in the plan builder and visually highlighted ("Included free") on the affected tile:

- **Lawn Care selected** → Weed Control & Removal included free.
- **Hedging selected** → Pesticide Treatment included free.
- **3 or 4 visits/month selected** → Fertilizer Treatment included free, and Watering included free.
- **New Lawn Development plan active** → Topsoil Treatment and Consultation/Inspection included free.

A tile that becomes included this way is force-checked and its checkbox disabled while the triggering condition holds; it re-enables (without forcing it back off) once the condition no longer applies, so genuine customer selections are never lost.

### Named plans (presets)

| Plan | Price | Composition |
|---|---|---|
| Essential Care | J$15,000 / month | Lawn Care, 2 visits/month. |
| Full Maintenance | J$21,000 / month | Lawn Care + Hedging + Watering, 2 visits/month. |
| New Lawn Development | J$50,000 / month (flat) | Lawn Care × 4 visits/month, Consultation/Inspection included, Topsoil Treatment included free. This is a full standalone plan, not a consultation starter — its price is a fixed flat rate, not a sum of its parts. |

Selecting more visits than a plan's minimum (e.g. bumping Essential Care from 2 to 3 visits) does not remove the plan's highlighted/active state — only changing the selected services, or dropping below the plan's minimum visit count, does.

### Currency

Prices are quoted in JMD (Jamaican Dollar) with a USD reference shown alongside, at a fixed reference rate of **J$150 = US$1**.

## Deployment

- Static site, no build step — `index.html` plus `assets/` (photos, logo).
- Hosted on GitHub Pages from the `main` branch, repo root.
- `.nojekyll` is present so GitHub Pages serves the files as-is without running them through Jekyll.
- After any push, verify the deployment: `gh run list --repo doxservices/mr-clays-lawn-care --limit 3` and `gh api repos/doxservices/mr-clays-lawn-care/pages --jq '.status'` should report a successful run and `status: "built"`.
