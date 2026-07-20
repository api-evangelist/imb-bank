# IMB Bank (imb-bank)

IMB Bank (IMB Ltd, ABN 92 087 651 974) is a member-owned Australian mutual bank founded in 1880 as the Illawarra Mutual Building Society in Wollongong, New South Wales. It is an authorised deposit-taking institution (ADI) regulated by APRA and ASIC, serving members across NSW, Victoria and the ACT. Under Australia's Consumer Data Right (CDR / Open Banking), IMB is a data holder that exposes a public, unauthenticated Product Reference Data (PRD) API conforming to the Consumer Data Standards.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/imb-bank/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/imb-bank/refs/heads/main/apis.yml)

## Tags

- Financial
- Banks
- Open Banking
- CDR
- Consumer Banking
- Australia
- Mutual Bank
- Product Reference Data

## Timestamps

- **Created:** 2026-07-20
- **Modified:** 2026-07-20

## APIs

### IMB Bank CDR Product Reference Data API

Public, unauthenticated Consumer Data Right (CDR) Product Reference Data API exposing IMB Bank's retail banking products (home loans, deposits, cards and more) under the Consumer Data Standards path `/cds-au/v1/banking/products`. Confirmed live returning HTTP 200 with a `data.products` array; supports endpoint versions x-v 4 and 5. Covers the `GET /banking/products` list and `GET /banking/products/{productId}` detail operations.

- **Human URL:** [https://www.imb.com.au/openbanking](https://www.imb.com.au/openbanking)
- **Base URL:** `https://openbank.openbanking.imb.com.au/cds-au/v1/banking/products`

#### Tags

- CDR
- Open Banking
- Product Reference Data
- Banking Products
- Consumer Data Standards

#### Properties

- [Documentation](https://www.imb.com.au/openbanking)
- [API Reference](https://developer.openbanking.imb.com.au/public/apis)
- [OpenAPI](openapi/imb-bank-cds-banking-products-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [Website](https://www.imb.com.au/)
- [Developer Portal](https://developer.openbanking.imb.com.au/public/apis)
- [Documentation](https://www.imb.com.au/openbanking)
- [Terms of Service](https://www.imb.com.au/important-information)
- [Privacy Policy](https://www.imb.com.au/important-information/privacy)
- [Support](https://www.imb.com.au/help-centre)
- [About](https://www.imb.com.au/about-us)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
