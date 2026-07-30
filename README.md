# MAGNUM CONTEST

Landing pages for Magnum Nutraceuticals' **"Name Our New Protein"** contest.

Two self-contained HTML files — no build step, no external requests. The product
shot is embedded as a WebP data URI; fonts are the only external load.

| File | Role |
|---|---|
| `enter.html` | **Step 1 — the gate.** Email + eligibility attestation. This is the page traffic should land on. |
| `index.html` | **Step 2 — the entry form.** Reached only from the single-use link emailed after step 1. |

## The flow

1. Visitor lands on `enter.html`, gives their email, ticks the eligibility
   confirmation (required) and optionally the marketing opt-in (unchecked by
   default, no effect on eligibility).
2. Backend creates the entrant record, mints a single-use token, sends the
   verification email.
3. The link in that email opens `index.html`, which greets them as verified and
   shows the naming form.

`enter.html` currently hands off with `index.html?e=<email>` and `index.html`
injects that address into both "entrant@email.com" slots. That query param is a
**review-build stand-in** for the tokenised URL — replace it with the real token
and resolve the address server-side.

Nothing gates `index.html` today. Anyone with the URL can open the entry form
directly. Real gating has to happen server-side against the token; the client
cannot enforce it.

## Status: review build — not production

Neither form has a backend. `enter.html` swaps to a "check your inbox" panel and
`index.html` swaps to a confirmation panel — both client-side only, nothing is
sent anywhere. The POST that has to replace the swap in `enter.html` is spelled
out in a comment in its submit handler, including the note that the response must
look identical for a new address and an already-entered one (otherwise the page
becomes a way to test who is on the list).

The "Official Contest Rules" link on `enter.html` points at `index.html#rules`,
which means clicking it from the gate drops the visitor onto the ungated entry
form. Before launch the rules need their own URL.

Both pages carry `<meta name="robots" content="noindex, nofollow">` so they stay
out of search results while under review.

## Unresolved placeholders

Every one is highlighted in gold on the page so it can be spotted visually:

| Placeholder | Needed for |
|---|---|
| `[START DATE]` / `[END DATE]` / `[TIME]` | Contest period, Official Rules §1, "Entries close" panels on both pages, footer strip |
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
