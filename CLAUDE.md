# PackPin — Web

Find Pokémon TCG vending machines near you, official and independent, worldwide, with community restock reports.

The web platform repository of the PackPin container. `../CLAUDE.md` governs product
behavior, domain vocabulary, user-facing copy, and releases. This file governs what this
repository holds and how it is published.

**This repository is public.** It exists so that store review, and anyone who installs the
app, can read PackPin's legal documents at a stable URL. Nothing here may name a key, an
internal URL, an unreleased feature, or anything the container's private repositories keep
to themselves. Read what you are about to commit as a stranger would.

**Web is not a mirror.** It is not expected to match iOS screen for screen and no parity
checker measures it. Today it is documents, not an app. If it ever grows product screens,
they implement `../docs/domain.md` directly and adopt the six layer folders under `src/` —
a container-level change, recorded in `../CLAUDE.md`'s tree.

## The tree

```
packpin-web/
├── CLAUDE.md
├── README.md
├── _config.yml     the site title and description — the only configuration
├── index.md        what PackPin is, and links to the documents below
├── privacy.md      the privacy policy the store listing links to
└── support.md      how to reach support, and the suggest-a-machine lines
```

**This tree is the single source of truth for this repository's structure. When a file is
added, removed, or renamed, update it in the same change.**

**There is no `terms.md`.** The terms are Apple's standard Licensed Application End User
License Agreement, linked from `index.md` and from the app; a document of PackPin's own
would only diverge from it.

## Status

The three documents are written and Pages is on (from `main`, root, switched on through the
GitHub API on 2026-09-09). Pages renders Markdown with its default theme, so a `.md` file at
the root becomes a page at the same path without the extension.

**Stack decided:** Markdown legal documents (privacy policy, terms of use, support) served by GitHub Pages from this public repository. No build step, no package manifest, no dependencies.

The privacy policy must describe what the app actually does. Community restock reports and a
saved-machines list are user data the moment they leave the device; write the policy against
the shipped feature set, and change it in the same release that changes what is collected —
`../docs/release.md` puts web first in the ship order for exactly this reason.

## Domain

| What | Value |
|---|---|
| Site address | `https://graboosky.github.io/packpin-web/` — GitHub Pages' own; no custom domain (decided 2026-09-09) |
| DNS / registrar | none |
| Host | GitHub Pages, from `main`, root |
| Privacy policy URL | `https://graboosky.github.io/packpin-web/privacy` — confirmed 200 on 2026-09-09 |
| Support URL | `https://graboosky.github.io/packpin-web/support` — confirmed 200 on 2026-09-09 |
| Support address | `p.grabowski.kontakt@gmail.com` |

Store review fetches the privacy policy and support URLs; each must return 200 before any
submission, and a 404 costs a review cycle.

## Build & test

There is no build. Pages publishes on every push to `main`, and takes about a minute. Check a
document rendered on github.com before pushing, and the live URL after.

## Conventions

- **Plain Markdown, one document per file, one `#` title each.** No HTML, no front matter
  beyond what a page needs for its title, no theme customisation until a document needs it.
- **Product copy comes from `../docs/domain.md`.** The product's name, what it does, and any
  sentence a user could also read inside the app are written once, there, and quoted here.
  Legal text has no other home; this repository is its source of truth.
- **Every legal document carries an absolute date** (`Last updated: 2026-09-08`), never a
  relative one, and the date changes whenever the text does.
- **English first.** A localized document is a sibling with a language suffix
  (`privacy.pl.md`), linked from the English one, and it says the English version governs.
