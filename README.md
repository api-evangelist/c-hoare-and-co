# C. Hoare & Co. (c-hoare-and-co)

C. Hoare & Co. (Hoares Bank) is the United Kingdom's oldest privately-owned bank, founded in 1672 by Sir Richard Hoare and owned continuously by the Hoare family for twelve generations. It offers bespoke private banking, lending, and wealth services from Fleet Street in London and an office in Cambridge. It is an FCA-authorised ASPSP and a regulated participant in UK Open Banking under PSD2. As a private bank it is not one of the CMA9 mandated institutions, so it publishes the OBIE Read/Write APIs — Account & Transaction Information, Payment Initiation, and Dynamic Client Registration — through a MuleSoft Anypoint developer portal, but does not publish the unauthenticated Open Data (ATM / branch / product) reference APIs.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/c-hoare-and-co/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/c-hoare-and-co/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Private Bank
- Open Banking
- PSD2
- OBIE
- FAPI
- United Kingdom
- Payments
- Account Information

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### C. Hoare & Co. Account and Transaction Information API

OBIE Read/Write Account & Transaction Information (AIS) API — lets onboarded, consented AISP third-party providers retrieve C. Hoare & Co. account, balance, transaction, beneficiary, standing order, direct debit, product, and party data. Conformant to the OBIE v3.1 Read/Write standard; FAPI-secured (OAuth2/OIDC + PSD2 SCA + mTLS).

- **Human URL:** [https://developer.hoaresbank.co.uk/apis/ob-account-and-transaction-api-v3-1-0/docs](https://developer.hoaresbank.co.uk/apis/ob-account-and-transaction-api-v3-1-0/docs)
- **Base URL:** `https://api.hoaresbank.co.uk/open-banking/v3.1/aisp`

#### Tags

- Account Information
- Transactions
- Open Banking
- AISP

#### Properties

- [OpenAPI](openapi/c-hoare-and-co-account-and-transaction-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.hoaresbank.co.uk/apis/ob-account-and-transaction-api-v3-1-0/docs)
- [API Reference](https://developer.hoaresbank.co.uk/apis/ob-account-and-transaction-api-v3-1-0/docs)
- [Documentation](https://www.hoaresbank.co.uk/open-banking)

### C. Hoare & Co. Payment Initiation API

OBIE Read/Write Payment Initiation (PIS) API — lets onboarded, consented PISP third-party providers initiate domestic and scheduled payments and standing orders and retrieve payment/consent status on behalf of C. Hoare & Co. customers. Conformant to the OBIE v3.1 Read/Write standard; FAPI-secured (OAuth2/OIDC + PSD2 SCA + mTLS).

- **Human URL:** [https://developer.hoaresbank.co.uk/apis/ob-payment-initiation-v3-1-0/docs](https://developer.hoaresbank.co.uk/apis/ob-payment-initiation-v3-1-0/docs)
- **Base URL:** `https://api.hoaresbank.co.uk/open-banking/v3.1/pisp`

#### Tags

- Payment Initiation
- Payments
- Open Banking
- PISP

#### Properties

- [OpenAPI](openapi/c-hoare-and-co-payment-initiation-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.hoaresbank.co.uk/apis/ob-payment-initiation-v3-1-0/docs)
- [API Reference](https://developer.hoaresbank.co.uk/apis/ob-payment-initiation-v3-1-0/docs)
- [Documentation](https://www.hoaresbank.co.uk/open-banking)

### C. Hoare & Co. Dynamic Client Registration API

OBIE Dynamic Client Registration (DCR) proxy — lets third-party providers submit a signed Software Statement Assertion to register an OAuth2 client with C. Hoare & Co. as part of TPP onboarding. Published on the developer portal as v3.1-RC1; the harvested contract is the shared OBIE client-registration standard.

- **Human URL:** [https://developer.hoaresbank.co.uk/apis/ob-dynamic-client-registration-proxy-v3-1-rc1/docs](https://developer.hoaresbank.co.uk/apis/ob-dynamic-client-registration-proxy-v3-1-rc1/docs)
- **Base URL:** `https://api.hoaresbank.co.uk/open-banking/v3.1`

#### Tags

- Dynamic Client Registration
- OAuth2
- Onboarding
- Open Banking

#### Properties

- [OpenAPI](openapi/c-hoare-and-co-dynamic-client-registration-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.hoaresbank.co.uk/apis/ob-dynamic-client-registration-proxy-v3-1-rc1/docs)
- [API Reference](https://developer.hoaresbank.co.uk/apis/ob-dynamic-client-registration-proxy-v3-1-rc1/docs)

## Common Properties

- [Website](https://www.hoaresbank.co.uk/)
- [Developer Portal](https://developer.hoaresbank.co.uk/)
- [Documentation](https://www.hoaresbank.co.uk/open-banking)
- [OpenID Configuration](https://developer.hoaresbank.co.uk/.well-known/openid-configuration)
- [Support](https://www.hoaresbank.co.uk/contact-us)
- [Developer Support](mailto:developersupport@hoaresbank.co.uk)
- [Terms of Service](https://www.hoaresbank.co.uk/terms-and-conditions)
- [Privacy Policy](https://www.hoaresbank.co.uk/privacy)
- [Legal](https://www.hoaresbank.co.uk/legal)
- [FCA Register](https://register.fca.org.uk/s/firm?id=001b000000MfFMxAAN)
- [Open Banking Registration](https://www.openbanking.org.uk/regulated-providers/c-hoare-co-2/)
- [LinkedIn](https://uk.linkedin.com/company/c-hoare-&-co)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
