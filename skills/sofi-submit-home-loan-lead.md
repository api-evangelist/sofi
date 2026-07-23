---
name: Submit a SoFi home-loan affiliate lead
description: >-
  Submit a home-loan lead to SoFi as an approved affiliate partner via the Home Loan Affiliate
  Lead API, and persist the returned SoFi lead identifier.
api: openapi/sofi-home-loan-affiliate-lead-api-openapi.yml
operations:
  - createHomeLoanLead
---

# Submit a SoFi home-loan affiliate lead

Use this skill to send a home-loan lead from an approved affiliate partner into SoFi.

## Prerequisites
- The correct environment-specific `accountId` (QA or Production) issued by SoFi.
- Base URL per environment:
  - QA / testing: `https://dev-external-0.sofitest.com`
  - Production: `https://www.sofi.com`
- All fields required by SoFi's Create Lead Request Fields table must be present in the body.

## Steps
1. **Submit the lead.** Call `createHomeLoanLead` — `POST /afpq/api/v1/affiliate/lead/home-loan`.
   Include the environment `accountId` plus the required (and any applicable optional) lead fields
   in the JSON body.
2. **Handle success.** A `201` returns `sofiAffiliateLeadId` and a `status` of `CREATED`. **Store
   the `sofiAffiliateLeadId`** for future reference.
3. **Handle failures** (see `errors/sofi-problem-types.yml`): `400` = a required parameter is
   missing (the reason is in the `message` node); `404` = resource not found; `500` = unexpected
   server error, retry or escalate.

## Conventions
- Auth: API key (`accountId`) only. See `authentication/sofi-authentication.yml`.
- No idempotency-key mechanism is documented — persist `sofiAffiliateLeadId` and de-duplicate on
  your side to avoid resubmitting the same lead.
- The source material is marked confidential/proprietary to Social Finance, Inc.
- See `conventions/sofi-conventions.yml` for cross-cutting semantics.
