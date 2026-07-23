---
name: Request a SoFi partner loan offer
description: >-
  Return real-time Personal Loan or Student Loan Refinancing offers from SoFi's underwriting model
  through the Partner Offer Pre-Qualification API, then hand the selected offer back to SoFi to
  pre-populate an application.
api: openapi/sofi-partner-offer-api-openapi.yml
operations:
  - getLoanOffer
---

# Request a SoFi partner loan offer

Use this skill to pre-qualify a user for a SoFi Personal Loan (PL) or Student Loan Refinancing
(SLR) offer from an approved partner site.

## Prerequisites
- A SoFi-issued `accountId` (API key / UUID). There is **one unique UUID per product type** — one
  for Personal Loan, a different one for Student Loan Refinancing. Keep them separate.
- Use the correct base URL for the environment:
  - Testing: `https://dev-external-0.sofitest.com` (does not affect live data)
  - Production: `https://www.sofi.com`
- All requests must be over HTTPS.

## Steps
1. **Build the request.** Call `getLoanOffer` — `POST /po/api/v2/loan-offer/json`. Put the
   partner `accountId` (the UUID for the product type you want) and the user-entered criteria in
   the JSON body. Set `loanPurpose` to select the product (e.g. `2` = Student Loan Refinance). For
   specialty SLR, set `graduateProgram` (`3` = Medicine MD, `13` = Medicine DO, `14` = Dental).
2. **Handle the response.** A `200` returns real-time loan offers from SoFi's underwriting model.
   Present them to the user.
3. **Handle failures** (see `errors/sofi-problem-types.yml`): `400` = missing/invalid required
   parameter; `401` = the accountId was not valid (check you used the right per-product UUID);
   `404` = resource not found.
4. **Persist selection.** When the user selects an offer, the user-entered criteria can be saved to
   pre-populate a SoFi loan application on the partner's site.

## Conventions
- Auth: API key (`accountId`) only; no password. See `authentication/sofi-authentication.yml`.
- No idempotency-key mechanism is documented; avoid duplicate submissions client-side.
- See `conventions/sofi-conventions.yml` for cross-cutting semantics.
