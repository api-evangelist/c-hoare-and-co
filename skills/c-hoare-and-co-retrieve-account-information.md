---
name: Retrieve C. Hoare & Co. account information (AIS)
description: Set up an account-access consent, obtain PSU authorisation, then read accounts, balances, and transactions from C. Hoare & Co. as a consented AISP.
api: openapi/c-hoare-and-co-account-and-transaction-api-openapi.yml
operations:
  - CreateAccountAccessConsents
  - GetAccountAccessConsentsConsentId
  - GetAccounts
  - GetAccountsAccountId
  - GetAccountsAccountIdBalances
  - GetAccountsAccountIdTransactions
---

# Retrieve account information as a consented AISP

You are acting as an onboarded, FCA/OBIE-registered Account Information Service
Provider (AISP) accessing C. Hoare & Co. (Hoare's Bank) via the OBIE v3.1
Read/Write Account & Transaction Information API.

## Preconditions

- You have completed TPP onboarding and hold valid OBIE/eIDAS transport + signing
  certificates; all calls use mutual-TLS.
- You hold a valid `TPPOAuth2Security` client-credentials token with the
  `accounts` scope for TPP-only steps, and will obtain a `PSUOAuth2Security`
  authorization-code token (with PSD2 SCA) for PSU-authorised reads.
- Set `x-fapi-interaction-id` on every request and log the value echoed back.

## Steps

1. **Create the account-access consent** — `CreateAccountAccessConsents`
   (`POST /account-access-consents`). Supply the `Permissions` you need
   (e.g. `ReadAccountsDetail`, `ReadBalances`, `ReadTransactionsDetail`) and an
   optional `ExpirationDateTime`. This returns a `ConsentId` in `AwaitingAuthorisation` status.
2. **Have the PSU authorise the consent** — redirect the customer through the
   bank's OAuth2/OIDC authorization-code flow with PSD2 SCA. On return you hold a
   `PSUOAuth2Security` access token bound to that `ConsentId`.
3. **Confirm consent status** (optional) — `GetAccountAccessConsentsConsentId`
   (`GET /account-access-consents/{ConsentId}`) to verify status is `Authorised`.
4. **List accounts** — `GetAccounts` (`GET /accounts`) with the PSU token to get
   the `AccountId`s the consent covers.
5. **Read account detail** — `GetAccountsAccountId` (`GET /accounts/{AccountId}`).
6. **Read balances** — `GetAccountsAccountIdBalances` (`GET /accounts/{AccountId}/balances`).
7. **Read transactions** — `GetAccountsAccountIdTransactions`
   (`GET /accounts/{AccountId}/transactions`), optionally filtered with
   `fromBookingDateTime` / `toBookingDateTime`. Follow the `Links.Next` cursor to
   page bulk results.

## Rules

- Errors return the OBErrorResponse1 envelope; branch on `Errors[].ErrorCode`
  (UK.OBIE.* namespace) — see errors/c-hoare-and-co-problem-types.yml.
- A `403` means the consent/scope does not cover the requested resource; a `429`
  means back off per OBIE polling guidance.
- Reads are safe/idempotent GETs — no `x-idempotency-key` is required for AIS.
