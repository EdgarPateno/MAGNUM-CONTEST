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
| `[START DATE]` / `[END DATE]` / `[TIME]` | Contest period, Official Rules §1, "Entries close" panel, footer strip |
| `[CONTACT EMAIL]` | Official Rules §11 |
| `[DATE]` | Rules effective date |

`entrant@email.com` (two places) is **not** a placeholder to fill by hand — it is the
verified entrant's own address, injected at runtime from their unique link. It stays
until the form is wired to a real endpoint.

### Resolved

- **Full Official Rules link** — there is no separate rules document; the rules on this
  page are the Official Rules. The dangling `href="#"` was removed and the lead-in
  reworded to say so.
- **Protein-source ratios** — staying order-of-inclusion only. The internal
  "confirm before publishing" note has been removed from the page.

## Contest terms reflected on the page

- Canada excluding Quebec, age of majority, one entry per person
- Prize: 14 two-pound tubs, approx. **$1,000 CAD** retail value
- Judged on originality / product relevance / brand fit, 33.3% each
- Test of skill — no random draw; ties settled by a skill-testing question
- **No purchase necessary**, stated on the page itself, not only in the rules

Sources: contest outline and Official Rules documents.
