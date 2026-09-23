# OnlineNIC (onlinenic)

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

OnlineNIC, Inc. is an ICANN-accredited domain registrar (IANA ID 82) and wholesale reseller platform,
operating since 1999, selling domain names across roughly 400 TLDs, SSL/TLS certificates from DigiCert,
GeoTrust, RapidSSL, Sectigo and Symantec, business email, reseller and cloud hosting, escrow and
domain-privacy services. It publishes a partner-facing Reseller API — currently build 4.0.9 — for
domains, contacts, nameservers, EPP auth codes, registrar transfers, ID Shield privacy, Whois
verification and the full SSL certificate lifecycle.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/onlinenic/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Producing
- **Access:** 3rd-Party

## Timestamps

- **Created:** 2025-02-09
- **Modified:** 2026-09-17

## APIs

### OnlineNIC Reseller API

Twenty-six domain commands and seventeen SSL commands over an RPC-style HTTPS surface: two PHP
endpoints, a `command` query parameter, POST only, and a JSON envelope carrying an integer status code
on every response (including errors — the HTTP status is always 200). Authentication is an API key plus
a per-request MD5 token over the reseller id, password digest, timestamp and command name, with an
optional source-IP allowlist.

**Human URL:** [https://www.onlinenic.com/cp_english/template_api/api_help.php](https://www.onlinenic.com/cp_english/template_api/api_help.php)

**Base URL:** `https://api.onlinenic.com/api4/`

#### Properties

- [Documentation](https://www.onlinenic.com/cp_english/template_api/api_help.php)
- [API 4.0.9 Reseller Guide (PDF)](https://www.onlinenic.com/cp_english/template_api/download/Onlinenic_API_v4.0.9.2_Reseller_Guide.pdf)
- [API 3.4 Usage Guide (PDF, deprecated)](https://onlinenic.com/cp_english/template_api/download/API_EN_Version_3.4.pdf)
- [OnlineNIC PHP SDK](https://www.onlinenic.com/cp_english/template_api/download.php?f=sdk_php.zip)
- [OnlineNIC Pro for WHMCS](https://www.onlinenic.com/en/Module/index/17.html)

## Notes from the 2026-09-17 enrichment pass

- **No machine-readable contract.** The API reference ships only as a PDF. `/openapi.json`,
  `/swagger.json`, `/api-docs` and `?wsdl` were probed on both `www.onlinenic.com` and
  `api.onlinenic.com` and all return 404 or the ordinary JSON error envelope. No AsyncAPI, GraphQL SDL,
  Postman collection or JSON Schema exists either.
- **The API is live.** `GET https://api.onlinenic.com/api4/ssl/index.php` returns
  `{"code":1001,"msg":"Invalid request."}` and an unauthenticated POST returns
  `{"code":1004,"msg":"Required parameter missing(user)."}`.
- **The recorded docs host was dead.** `wiki.onlinenic.com` returns "No forward mapping for this host."
  and serves a mismatched certificate; the record has been repointed at the live reference page.
- **The documented OTE sandbox host did not answer.** `ote.onlinenic.com` resolves but did not complete
  a connection over HTTP or HTTPS on 2026-09-17.
- **Every first-party package predates the current API.** The PHP SDK (2015) and the WHMCS module
  (2019) both drive the deprecated 3.4 socket protocol on port 30009; nothing first-party targets
  API v4.
- **No published rate limits and no idempotency key.** Two scaffold artifacts that had invented both
  (`plans/` and `rate-limits/`) were replaced with what the provider actually publishes.
- **Nothing in `/.well-known/`** on any host, no MCP server, no A2A agent card, no status page and no
  GitHub organisation.

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
