# rps-design

Source of truth for the shared RPS design tokens (v1.2) used by www.1rps.com,
portal.1rps.com and hub.1rps.com. Build Plan v0.2, Phase 2.

| File | What it is |
| --- | --- |
| `rps-tokens.css` | Colour, type, space and radius as CSS variables, with a print block that flips every surface to paper. |
| `index.html` | The rendered check page. Open it in a browser, and print it. |
| `rps-mark.png` | Logo mark, from RPS-website. |
| `rps-connect/` | The RPS Connect logo: light and dark lockups (each also on a transparent background), the mark alone, and the app icon. SVG for screens and print, PNG for documents. The lettering is outlined, so no font is needed. |

## How apps use it

Each app keeps its own copy of `rps-tokens.css`, with the version comment at
the top left intact. Nothing hot-links it, so no app's content security
policy or uptime depends on another site. The apps have no build chain;
copying the file is the whole mechanism. When the file changes here, bump
the version and copy it again.

## Decided

- **RPS Connect**, 8 October 2026: the name for the whole digital estate
  (the Hub, the inspection app and customer portal, Triage, RPS Cashflow
  and Talent LMS). Its mark is an open C: the RPS ring opened up, with a
  centre node and a trace leaving each end, in the brand mint-to-blue
  gradient. Files in `rps-connect/`. The Resolution Production Services
  logo stays the company's logo; RPS Connect sits under it. Use the light
  lockup on light pages, the dark one on the dark portal and Triage.
  The family, added the same day: a dark and a light lockup for each
  module (`rps-connect-hub-`, `-portal-`, `-triage-`, `-cashflow-`);
  one-colour lockups and marks in white, ink and mint, for places that
  take one colour; icons drawn for 16, 32 and 48 px, and
  `favicon.ico` holding them. Each as SVG and PNG.
- **Ring order**, 18 September 2026: 1 System Health & Reporting,
  2 Spares, Repairs & Maintenance, 3 Training & Knowledge, 4 Lifecycle
  Management, 5 Triage Intelligence, 6 Engineer Access, clockwise from the
  top. Tokens are named by service so a later reorder does not touch the
  palette.
- **Pillar colours**, approved 18 September 2026: Health mint #00EBB4,
  Spares magenta #D46BD9, Training steel #9DB4D0, Lifecycle orange
  #FFA13B (v1.2, was violet), Triage cyan #00BEEB, Engineer Access blue
  #008CF5. No ring neighbours merge for red–green colour-blind viewers.
  Supersedes Build Plan 5.3.
- **Entitlement is strength, not greyness**, 23 September 2026: every
  pillar keeps its own colour whether a customer has that service or not,
  because pillar colour identifies a service and never its status. What
  they have is shown at full fill and glow with an ACTIVE pill; what they
  do not is the same colour dimmed, inviting a conversation on hover. The
  lock and "Not included" are retired: six locks on one screen read as a
  sales pitch. The portal ring takes the website wheel's styling, so the
  two read as one system.
- **Passed is green** #56D364 with a tick (v1.1, was text colour). Held
  well clear of brand mint and never used for identity.
- **Lifecycle orange never shares a view with caution amber** (v1.2). They
  are almost the same colour; the word and icon on every status are what
  keep them apart, and pages are designed so they do not meet.
- **Type**: Roboto for all text; Stolzl retired. IBM Plex Mono for figures.
- **Filled buttons** use `--rps-action-fill` #0072CE with white text (4.9:1),
  because white on #008CF5 is 3.5:1 and fails AA.

## Mapping from the website's variables (for Phase 5)

| RPS-website `styles.css` | Token |
| --- | --- |
| `--ink` | `--rps-shell` |
| `--panel` / `--panel-2` | `--rps-panel` / `--rps-panel-raised` |
| `--line` | `--rps-line` |
| `--paper` / `--muted` | `--rps-text` / `--rps-text-muted` |
| `--teal` | `--rps-brand-mint` |
| `--blue` | `--rps-brand-blue` |
| `--violet` (actually #008cf5) | `--rps-brand-blue` — retire the name |
| `--amber` | `--rps-cta-public` |
| inline `--accent` on ring and pillar cards | `var(--rps-pillar-health)` etc., by service |
