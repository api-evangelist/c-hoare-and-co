# C. Hoare & Co. (c-hoare-and-co)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
