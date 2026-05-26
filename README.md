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

## Getting access

API access requires an API key. Visit **[fapi.iisis.ru](https://fapi.iisis.ru)** for pricing and onboarding.

## License

This spec is published under [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0.html), matching the API license declared in `openapi.yml`.
