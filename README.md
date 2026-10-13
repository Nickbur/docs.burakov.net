# docs.burakov.net

Public, **multi-project** documentation for Burakov apps and developer packages, built with
[Mintlify](https://mintlify.com) and served at `https://docs.burakov.net`.

- **Home hub** — [`index.mdx`](index.mdx) is the root landing (`/`): a card per project.
- **One product per project** — theme `aspen`; each project is an entry in
    `navigation.products` in `docs.json` (header product switcher, with `icon` + short
    `description`), its pages under `<project>/` (landing at `<project>.mdx` → `/<project>`).
    The hub is the first entry, "All projects".
- **Tabs inside a product** follow its type: apps — Get started · Features · Help (+ Self-hosting);
    developer tools — Get started · Guides · Reference; team products — For users · For admins ·
    Help; the OS — Overview · Technology · Roadmap & licensing. Products move to tabs as their docs
    are expanded; the rest keep plain groups until then.
- **Wide pages** — every page sets `mode: "wide"` in its frontmatter (after `description`):
    no right-hand "On this page" column, so content gets the full width. Keep it on new pages.
- **English only** — Mintlify's multi-language localization is paywalled on the free plan,
    so the nav uses plain `products`/`groups`, not `languages`.
- **Audience: human customers.** No AI/agent or internal-meta notes — client-facing only.
- The **Documentation** tab on a project's page at `burakov.net` links here (shown only for
    projects flagged `docs: true` in `burakov.net/src/data/projects.ts`).

## Develop

```bash
npm i -g mint
mint dev
```

## Add a project's docs

1. Create `<slug>.mdx` (the project landing → `/<slug>`) and its `<slug>/…` pages, each
    with `title`, `description` and `mode: "wide"` in the frontmatter.
2. In [`docs.json`](docs.json), add a product under `navigation.products` for the project
    (`product`, `icon`, a short `description`), listing its pages in tabs per its type.
3. Add a `<Card>` for it to the hub in [`index.mdx`](index.mdx).
4. Flip `docs: true` on that project in `burakov.net/src/data/projects.ts` so its
    Documentation tab appears and links to `docs.burakov.net/<slug>`.
