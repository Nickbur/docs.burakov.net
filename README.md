# docs.burakov.net

Public, **multi-project** documentation for Burakov apps and developer packages, built with
[Mintlify](https://mintlify.com) and served at `https://docs.burakov.net`.

- **Home hub** — [`index.mdx`](index.mdx) is the root landing (`/`): a card per product.
- **One tab per product** — each product is a top-level tab in `docs.json`, with its pages
  under `<product>/` (landing at `<product>.mdx` → `/<product>`).
- **English only** — Mintlify's multi-language localization is paywalled on the free plan,
  so the nav uses plain `tabs`/`groups`, not `languages`.
- **Audience: human customers.** No AI/agent or internal-meta notes — client-facing only.
- The **Documentation** tab on a product's page at `burakov.net` links here (shown only for
  products flagged `docs: true` in `burakov.net/src/data/products.ts`).

## Develop

```bash
npm i -g mint
mint dev
```

## Add a product's docs

1. Create `<slug>.mdx` (the product landing → `/<slug>`) and its `<slug>/…` pages.
2. In [`docs.json`](docs.json), add a tab under `navigation.tabs` for the product, listing
   its groups/pages.
3. Add a `<Card>` for it to the hub in [`index.mdx`](index.mdx).
4. Flip `docs: true` on that product in `burakov.net/src/data/products.ts` so its
   Documentation tab appears and links to `docs.burakov.net/<slug>`.
