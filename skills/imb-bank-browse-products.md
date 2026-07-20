---
name: Browse IMB Bank banking products
description: Retrieve IMB Bank's publicly available retail banking products and their
  detail via the unauthenticated CDR Product Reference Data API.
api: openapi/imb-bank-cds-banking-products-openapi.yml
operations:
- listBankingProducts
- getBankingProductDetail
auth: none
---

# Browse IMB Bank banking products

IMB Bank exposes a **public, unauthenticated** Consumer Data Right (CDR) Product
Reference Data (PRD) API. Use it to list retail banking products and read the full
detail of any product. No OAuth, no consent, no client certificate required — only
the CDS endpoint-version header.

## Base URL

```
https://openbank.openbanking.imb.com.au/cds-au/v1
```

## Required convention

- Send an endpoint-version header **`x-v: 4`** (IMB's PRD supports `x-v` 4 and 5).
- On version mismatch the API returns **406** `urn:au-cds:error:cds-all:Header/UnsupportedVersion`.
- Errors use the CDS `ErrorV2` envelope: `{ "errors": [ { "code", "title", "detail" } ] }`
  (see `errors/imb-bank-problem-types.yml`).

## Step 1 — List products (`listBankingProducts`)

```
GET /banking/products?page-size=25
x-v: 4
```

Optional query params: `product-category`, `page`, `page-size` (max 1000),
`effective` (CURRENT | FUTURE | ALL), `updated-since`, `brand`.
Response: `data.products[]` (each with `productId`, `name`, `productCategory`,
`brand`), plus `links` (page-number pagination) and `meta.totalRecords`.

## Step 2 — Get product detail (`getBankingProductDetail`)

Take a `productId` from Step 1 and fetch the full product record:

```
GET /banking/products/{productId}
x-v: 4
```

Response `data` includes `bundles`, `features`, `constraints`, `eligibility`,
`fees`, `depositRates`, `lendingRates`, and `cardArt`. A missing/invalid id
returns **404** `urn:au-cds:error:cds-all:Resource/Invalid`.

## Notes

- Read-only: both operations are `GET`; there is no idempotency-key contract.
- Member account/transaction/payee data is NOT covered by this skill — those
  operations require the CDR consent flow (FAPI OAuth2 + PAR + mTLS); see
  `authentication/imb-bank-authentication.yml`.
