# docs.burakov.net

Public documentation for Burakov apps and developer packages, built with
[Mintlify](https://mintlify.com) and served at `https://docs.burakov.net/<product>/`.

- Config: [`docs.json`](docs.json) — navigation, theme, languages (EN default at root,
  RU under `/ru/`).
- Content: one `<product>.mdx` landing per product + a `<product>/` folder for its pages.
  Russian copies live under `ru/`.
- The **Documentation** tab on each product page at `burakov.net` links here (only for
  products flagged `docs: true` in `burakov.net/src/data/products.ts`).

## Develop

```bash
npm i -g mint
mint dev
```

## Add a product's docs

1. Create `<slug>.mdx` (landing) and `<slug>/…` pages, plus `ru/<slug>.mdx` and
   `ru/<slug>/…` for Russian.
2. Register both language copies under `navigation.languages[].products[]` in `docs.json`.
3. Flip `docs: true` on that product in `burakov.net/src/data/products.ts` so the tab
   appears.
