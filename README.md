# docs.burakov.net

Public, **multi-project** documentation for Burakov apps and developer packages, built with
[Mintlify](https://mintlify.com) and served at `https://docs.burakov.net`.

- **Home hub** — [`index.mdx`](index.mdx) is the root landing (`/`): a card per project.
- **One product per project** — theme `aspen`; each project is an entry in
    `navigation.products` in `docs.json` (header product switcher, with `icon` + short
    `description`), its pages under `<project>/` (landing at `<project>.mdx` → `/<project>`).
    The hub is the first entry, "All projects".
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

1. Create `<slug>.mdx` (the project landing → `/<slug>`) and its `<slug>/…` pages.
2. In [`docs.json`](docs.json), add a product under `navigation.products` for the project
    (`product`, `icon`, a short `description`), listing its groups/pages.
3. Add a `<Card>` for it to the hub in [`index.mdx`](index.mdx).
4. Flip `docs: true` on that project in `burakov.net/src/data/projects.ts` so its
    Documentation tab appears and links to `docs.burakov.net/<slug>`.
