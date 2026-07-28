# MAGNUM CONTEST

Landing page for Magnum Nutraceuticals' **"Name Our New Protein"** contest.

Single self-contained `index.html` — no build step, no external requests. The
product shot is embedded as a WebP data URI; fonts are the only external load.

## Status: review build — not production

The entry form has **no backend**. Submitting swaps to a confirmation panel
client-side only; nothing is sent anywhere. It needs wiring to a real endpoint
before launch.

The page carries `<meta name="robots" content="noindex, nofollow">` so it stays
out of search results while under review.

## Unresolved placeholders

Every one is highlighted in gold on the page so it can be spotted visually:

| Placeholder | Needed for |
|---|---|
| `[START DATE]` / `[END DATE]` / `[TIME]` | Contest period, Official Rules §1 |
| `[CONTACT EMAIL]` | Official Rules §11 |
| `[LINK TO FULL OFFICIAL RULES]` | Required link from the entry form |
| `[DATE]` | Rules effective date |
| `entrant@email.com` | Verified-entrant address, injected per unique link |

Also open: whether exact protein-source ratios can be disclosed. The bars in the
formula section currently show **order of inclusion only**, and are labelled as
such.

## Contest terms reflected on the page

- Canada excluding Quebec, age of majority, one entry per person
- Prize: 14 two-pound tubs, approx. **$1,000 CAD** retail value
- Judged on originality / product relevance / brand fit, 33.3% each
- Test of skill — no random draw; ties settled by a skill-testing question
- **No purchase necessary**, stated on the page itself, not only in the rules

Sources: contest outline and Official Rules documents.
