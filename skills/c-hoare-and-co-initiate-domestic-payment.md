---
name: Initiate a C. Hoare & Co. domestic payment (PIS)
description: Create a domestic payment consent, obtain PSU authorisation and optional funds confirmation, then execute an idempotent, JWS-signed domestic payment as a consented PISP.
api: openapi/c-hoare-and-co-payment-initiation-api-openapi.yml
operations:
  - CreateDomesticPaymentConsents
  - GetDomesticPaymentConsentsConsentId
  - GetDomesticPaymentConsentsConsentIdFundsConfirmation
  - CreateDomesticPayments
  - GetDomesticPaymentsDomesticPaymentId
---

# Initiate a domestic payment as a consented PISP

You are acting as an onboarded Payment Initiation Service Provider (PISP)
initiating a single domestic payment via C. Hoare & Co.'s OBIE v3.1 Read/Write
Payment Initiation API.

## Preconditions

- TPP onboarding complete; OBIE/eIDAS transport + signing certificates held; all
  calls use mutual-TLS.
- `TPPOAuth2Security` client-credentials token with the `payments` scope for
  consent creation; `PSUOAuth2Security` authorization-code token (PSD2 SCA) for execution.
- Every request carries `x-fapi-interaction-id`. Payment-order write requests
  additionally require `x-idempotency-key` (unique per logical payment, ≤ 40 chars)
  and a detached `x-jws-signature` over the request body.

## Steps

1. **Create the payment consent** — `CreateDomesticPaymentConsents`
   (`POST /domestic-payment-consents`). Supply `Initiation` (debtor/creditor
   accounts, `InstructedAmount`, reference). Returns a `ConsentId` in
   `AwaitingAuthorisation`. Include `x-jws-signature`.
2. **Have the PSU authorise** — redirect the customer through the OAuth2/OIDC
   authorization-code + PSD2 SCA flow to authorise the `ConsentId`; you receive a
   PSU-bound access token.
3. **Confirm consent status** — `GetDomesticPaymentConsentsConsentId`
   (`GET /domestic-payment-consents/{ConsentId}`) — proceed only when `Authorised`.
4. **Confirm funds** (optional) — `GetDomesticPaymentConsentsConsentIdFundsConfirmation`
   (`GET /domestic-payment-consents/{ConsentId}/funds-confirmation`).
5. **Execute the payment** — `CreateDomesticPayments` (`POST /domestic-payments`)
   with the same `Initiation` block and the `ConsentId`. Set a unique
   `x-idempotency-key` and `x-jws-signature`. Returns a `DomesticPaymentId`.
6. **Poll payment status** — `GetDomesticPaymentsDomesticPaymentId`
   (`GET /domestic-payments/{DomesticPaymentId}`) until `AcceptedSettlementCompleted`
   (or a terminal rejected status).

## Rules

- **Idempotency:** replaying the same `x-idempotency-key` with an identical body
  returns the original payment rather than creating a duplicate (keys retained ≥ 24h).
  See conventions/c-hoare-and-co-conventions.yml.
- **Errors:** OBErrorResponse1 envelope; `UK.OBIE.Rules.AfterCutOffDateTime`,
  `UK.OBIE.Rules.DuplicateReference`, and `UK.OBIE.Signature.*` are the common
  payment-write failures — see errors/c-hoare-and-co-problem-types.yml.
- Never re-execute a payment on a network timeout without reusing the original
  `x-idempotency-key`.
