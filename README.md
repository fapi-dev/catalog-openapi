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
- **Vehicle catalog (`catalogDt`)** — parts lookup by vehicle make / model / modification / node: aftermarket parts (`productList`) and the maker's original numbers (`productListOEM`).
- **VIN (`vin`)** — identify a vehicle by VIN and continue in the vehicle catalog with the modification it resolved to.

## Getting a key

Register at **[id.iisis.ru](https://id.iisis.ru)** and issue a key for this API on the "Keys"
page of your account. A new account starts on a trial package of credits, granted once.

Send the key in the `Authorization` header:

```bash
KEY=<your key>
curl -H "Authorization: Bearer $KEY" "https://fapi.iisis.ru/fapi/v2/analogList?n=w753"
```

Never put a key in a URL — URLs end up in access logs and proxies. VIN decoding (`/vin`) is
billed to a prepaid balance of its own, not to the trial package.

Questions — **`development.iisis@gmail.com`** or **[fapi.iisis.ru](https://fapi.iisis.ru)**.

## About this repository

This repository is a publication target: the spec is maintained together with the API itself and
copied here on release. Changes made here directly are overwritten by the next release — to report
a mistake in the spec, open an issue.

## License

This spec is published under [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0.html), matching the API license declared in `openapi.yml`.
