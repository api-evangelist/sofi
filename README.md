# SoFi (sofi)

SoFi (Social Finance) is a digital personal finance company and federally chartered bank offering an integrated suite of financial products including banking (checking and savings), personal loans, student loan refinancing, private student loans, mortgages, home equity products, active and automated investing, cryptocurrency trading, and credit cards. The platform is unified through the SoFi app and complemented by a SoFi Plus premium membership ($10/month) that unlocks enhanced APY, investment matching, loan rate discounts, and unlimited financial planner access. Third-party integration with SoFi accounts is facilitated through open banking aggregators Plaid and Finicity (Mastercard Open Banking) for consumer-permissioned data access. SoFi's subsidiary Galileo Financial Technologies provides the underlying fintech infrastructure and white-label banking APIs used by major fintech brands globally. SoFi does not publish a first-party consumer-facing open-banking API; consumer account access is aggregator-only (Plaid, Finicity, MX, Akoya). Its real first-party public API surface is B2B/partner-oriented: two documented REST APIs in SoFi's public Postman workspace (a Partner Offer Pre-Qualification API exposing SoFi's PL/SLR underwriting model, and a Home Loan Affiliate Lead API), a Business Banking developer-docs project at docs.sofi.com, and the SoFi Tech Solutions (formerly Galileo) platform at docs.tech.sofi.com.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/sofi/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/sofi/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Personal Finance
- Banking
- Lending
- Student Loans
- Mortgages
- Investing
- Credit Cards
- Fintech
- Open Banking
- Digital Banking

## Timestamps

- **Created:** 2026-06-13
- **Modified:** 2026-07-23

## APIs

> SoFi's consumer products (SoFi Money, personal/student loans, mortgages, SoFi Invest, credit card) are app and web experiences, not public APIs, and consumer account access is aggregator-only (Plaid, Finicity, MX, Akoya). The entries below are SoFi's genuinely documented first-party developer APIs.

### SoFi Partner Offer Pre-Qualification API

SoFi's partner-offer-api (documented as Partner Offer Pre Qual V2) is a real, first-party external REST API that exposes SoFi's underwriting model to approved partners, returning real-time Personal Loan (PL) and Student Loan Refinancing (SLR) offers via `POST /po/api/v2/loan-offer/json`. Auth is by API key / UUID (per product type) passed as `accountId` in the JSON body, HTTPS only. Test base `https://dev-external-0.sofitest.com`, production `https://www.sofi.com`.

- **Human URL:** [Postman documentation](https://www.postman.com/sofi-api/team-sofi-s-public-workspace/documentation/7686555-548d8800-0df1-4783-8450-aade8b8a39e4)
- **Base URL:** https://www.sofi.com

#### Tags

- Lending
- Personal Loans
- Student Loan Refinancing
- Prequalification
- Partner API
- United States

#### Properties

- [OpenAPI](openapi/sofi-partner-offer-api-openapi.yml)
- [Documentation](https://www.postman.com/sofi-api/team-sofi-s-public-workspace/documentation/7686555-548d8800-0df1-4783-8450-aade8b8a39e4)
- [Postman](https://www.postman.com/sofi-api/team-sofi-s-public-workspace/collection/orw4s7j/affiliate-prequal-offers)

### SoFi Home Loan Affiliate Lead API

A real, first-party REST endpoint letting approved affiliate partners submit home-loan leads via `POST /afpq/api/v1/affiliate/lead/home-loan`. A successful submission (HTTP 201) returns a `sofiAffiliateLeadId` and CREATED status. Environment-specific `accountId` values authenticate requests (QA base `https://dev-external-0.sofitest.com`, production `https://www.sofi.com`).

- **Human URL:** [Postman documentation](https://www.postman.com/sofi-api/team-sofi-s-public-workspace/documentation/11106810-0d3f9390-b6f2-4100-891d-977691e36fc2)
- **Base URL:** https://www.sofi.com

#### Tags

- Mortgage
- Home Loans
- Affiliate
- Lead Generation
- Partner API
- United States

#### Properties

- [OpenAPI](openapi/sofi-home-loan-affiliate-lead-api-openapi.yml)
- [Documentation](https://www.postman.com/sofi-api/team-sofi-s-public-workspace/documentation/11106810-0d3f9390-b6f2-4100-891d-977691e36fc2)
- [Postman](https://www.postman.com/sofi-api/team-sofi-s-public-workspace/documentation/5k2lj48/home-loan-affiliate-lead-api)

### SoFi Business Banking API

SoFi Business Banking (Big Business Banking) is SoFi Bank, N.A.'s API-driven commercial platform for real-time 24/7/365 money movement in fiat, SoFiUSD, or selected digital assets, powering debit/prepaid/ACH/wire for sponsor-banking partners on Galileo's Cyberbank Core. First-party developer docs are published at docs.sofi.com (ReadMe-hosted, HTML-only; no downloadable spec confirmed); onboarding is partner-gated (bbb@sofi.org).

- **Human URL:** [https://docs.sofi.com/business-banking/docs](https://docs.sofi.com/business-banking/docs)

#### Tags

- Business Banking
- Commercial Payments
- Real-Time Payments
- Embedded Finance
- Sponsor Banking
- United States

#### Properties

- [Developer Portal](https://docs.sofi.com/business-banking/docs)
- [Documentation](https://www.sofi.com/business-banking/commercial/)

### SoFi Tech Solutions Platform API

SoFi Tech Solutions (formerly Galileo Financial Technologies) is SoFi's B2B fintech platform arm, exposing cloud-native RESTful APIs - Program, Config, Dispute, Loan, Payment Hub, Risk/Auth, Events webhooks, External Transactions - across Cyberbank Core/Digital, Card Issuing & Payment Hub, Secured Credit, and the Payment Risk Platform (250+ methods, sandbox at sandbox.gpsrv.com). Deep one-per-resource coverage is maintained separately in `api-evangelist/galileo-fs`.

- **Human URL:** [https://docs.tech.sofi.com/pro/reference/program-api-intro](https://docs.tech.sofi.com/pro/reference/program-api-intro)

#### Tags

- Banking-as-a-Service
- Card Issuing
- Payment Processing
- Embedded Finance
- Core Banking
- United States

#### Properties

- [Developer Portal](https://docs.tech.sofi.com/pro/reference/program-api-intro)
- [Documentation](https://tech.sofi.com/platform/open-apis/)
- [Sandbox](https://sandbox.gpsrv.com/auth/login)

## Common Properties

- [Website](https://www.sofi.com/)
- [Documentation](https://www.sofi.com/blog/)
- [Developer Portal](https://docs.sofi.com/business-banking/docs)
- [Postman](https://www.postman.com/sofi-api/team-sofi-s-public-workspace/)
- [LinkedIn](https://www.linkedin.com/company/sofi)
- [Blog](https://www.sofi.com/blog/)
- [Pricing](https://www.sofi.com/sofi-plus/)
- [Status Page](https://sofi.statuspage.io)
- [X (Twitter)](https://twitter.com/SoFi)
- [Plans](plans/sofi-plans-pricing.yml)
- [Rate Limits](rate-limits/sofi-rate-limits.yml)
- [Fin Ops](finops/sofi-finops.yml)
- [Terms of Service](https://www.sofi.com/terms-of-use)
- [Privacy Policy](https://www.sofi.com/privacy-policy)
- [Support](https://support.sofi.com/hc/en-us)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
