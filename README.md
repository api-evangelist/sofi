# SoFi (sofi)

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
