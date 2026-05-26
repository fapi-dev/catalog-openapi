# FAPI Catalog API — OpenAPI 3.0 spec

OpenAPI 3.0.3 reference for the [FAPI](https://fapi.iisis.ru) auto-parts catalog API.

**Live docs:** https://fapi-dev.github.io/catalog-openapi/

## What's in this repo

- [`openapi.yml`](./openapi.yml) — the spec itself. Use it to generate clients in any language with [`openapi-generator`](https://openapi-generator.tech/) or import into Postman / Insomnia / Bruno.
- [`index.html`](./index.html) — [Scalar](https://github.com/scalar/scalar) renderer pointing at the spec. Served via GitHub Pages.

## What the API does

OEM cross-reference database for auto parts:

- **Manufacturers** — index of parts brands.
- **Products** — look up parts by article number; get attributes, applicability, images.
- **Cross-references (`analogList`)** — find equivalent parts across brands by article number, with a confidence rating.
- **Vehicle catalog (`catalogDt`)** — non-original parts lookup by vehicle make / model / modification.

## Try it now (demo key)

A public demo key is rotated periodically — fetch the current value from:

```
curl -s https://gist.githubusercontent.com/serp83/652d191745773ef6d8b5a0a689479cd6/raw/demo-key.txt
```

Pass it as the `ui` query parameter on any endpoint:

```bash
KEY=$(curl -s https://gist.githubusercontent.com/serp83/652d191745773ef6d8b5a0a689479cd6/raw/demo-key.txt)
curl "https://fapi.iisis.ru/fapi/v2/analogList?ui=$KEY&n=w753"
```

The demo key has a shared daily quota — fine for evaluation, not for production load.

## Getting a permanent key

Production access requires a personal API key. Contact **`development.iisis@gmail.com`** or visit **[fapi.iisis.ru](https://fapi.iisis.ru)**.

## License

This spec is published under [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0.html), matching the API license declared in `openapi.yml`.
