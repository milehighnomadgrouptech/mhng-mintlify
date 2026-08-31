# MHNG documentation — project instructions

## About this project

- This is the documentation site for **Mile High Nomad Group (MHNG)**, a
  compliance-native data engineering, AI, and automation consultancy.
- It is a Mintlify site. Pages are MDX with YAML frontmatter; configuration
  lives in `docs.json`.
- Brand assets: `logo/light.svg` (navy ink, light mode), `logo/dark.svg`
  (white ink, dark mode), `favicon.svg`.
- `style.css` is auto-included on every page. Do not import it from MDX and do
  not add a key for it in `docs.json`.

## Terminology

- **MHNG** on second reference; **Mile High Nomad Group** on first.
- **Organization**, not "workspace" or "tenant", for a client account.
- **Dashboard** for `app_mhng`; **marketing site** for `mhng.tech`.
- **Packages** for the `@milehighnomadgrouptech/*` libraries — not "SDK".
- **Engagement** for a client project.

## Style preferences

- Active voice, second person ("you").
- One idea per sentence.
- Sentence case for headings.
- Bold for UI elements: Click **Settings**.
- Code formatting for file names, commands, paths, and code references.
- US English. Spell out numbers under ten except in tables and measurements.

## Content boundaries

- **Never publish** internal-only material: route status trackers, the security
  debt register, secret-rotation runbooks, or the canary and deception
  procedure.
- **Never publish** registers marked Confidential or Restricted, and scrub
  seeded canary values before porting any register.
- Compliance policies may be summarized publicly; the full control matrix is
  shared under NDA only.
- Describe the four frameworks (SOC 2, ISO 27001:2022, HIPAA, GDPR) as
  **implemented and maintained**. Do not claim certification or attestation
  that has not been issued.
- Do not add outbound links to vendors, tools, or platforms that are not part
  of MHNG's own stack or identity.

## Editing rules

- Every page referenced in `docs.json` under `navigation` must exist, and every
  page that exists should be referenced — an unlisted page will not appear.
- Run `mint validate` before pushing. `docs.json` is strictly schema-validated
  and reports unknown keys only as a generic failure.
- Keep brand colors in sync with `packages/config/tailwind/index.ts`; that file
  is the source of truth, not this repository.
