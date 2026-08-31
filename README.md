# MHNG Documentation

The documentation site for **Mile High Nomad Group** — platform architecture,
shared packages, and our security and privacy posture.

Live at the deployment configured for this repository. Source of truth for the
site's structure, branding, and navigation is [`docs.json`](docs.json).

## Local development

Install the CLI:

```bash
npm i -g mint
```

Then, from the repository root (the folder containing `docs.json`):

```bash
mint dev
```

The preview runs at `http://localhost:3000`.

## Validating before you push

```bash
mint validate
```

Runs a strict build and exits non-zero on any warning or error. `docs.json` is
schema-validated — an unknown or misspelled key fails the build with a single
generic "not valid under any of the given schemas" message, so check your most
recent edit first.

## Repository layout

```
docs.json              Site config: theme, brand colors, navigation, footer
style.css              Brand CSS — auto-included on every page, no import needed
favicon.svg            Navy badge with the MHNG mountain mark
logo/light.svg         Lockup used in light mode (navy ink)
logo/dark.svg          Lockup used in dark mode (white ink)
index.mdx              Placeholder landing page
```

The site is currently a single branded placeholder. Branding, navigation
chrome, and the footer are already wired up, so adding real content is just a
matter of dropping in `.mdx` files and listing them in `docs.json`.

## Branding

Colors come from the shared brand scale in
`packages/config/tailwind/index.ts` — the same eleven stops the dashboard and
marketing site use.

| Token | Hex | Used for |
| --- | --- | --- |
| `brand-600` | `#0074C5` | Primary — links, emphasis in light mode |
| `brand-400` | `#36ADF6` | Emphasis in dark mode |
| `brand-700` | `#015CA0` | Buttons and hover states |
| `brand-950` | `#072A49` | Dark-mode page background |

Typography is **Geist**, matching `mhng.tech` and the dashboard.

Any `.css` file in this directory is included on every page automatically —
there is no key to add in `docs.json` and nothing to import from MDX.

## Adding a page

1. Create the `.mdx` file with `title` and `description` frontmatter.
2. Add its path (no extension) to `navigation.pages` in `docs.json`.
3. Run `mint validate`.

A page that is not listed in `navigation` will not appear in the sidebar.

Once there is enough material to group, swap `navigation.pages` for
`navigation.groups`. Note that a navigation level accepts exactly **one** kind
of child — `pages` and `groups` cannot be siblings.

## Publishing

Changes deploy automatically once the GitHub app is installed on this
repository and connected to the deployment. Pushing to the default branch
triggers a production deploy.

## Contact

- General — [info@mhng.tech](mailto:info@mhng.tech)
- Security — [security@mhng.tech](mailto:security@mhng.tech)
