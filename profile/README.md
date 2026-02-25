# RDAP API — Modern WHOIS Lookup API for Developers

**[RDAP API](https://rdapapi.io)** is a REST API that replaces WHOIS with structured JSON domain lookups. It queries [RDAP](https://rdapapi.io/docs) (Registration Data Access Protocol) — the official WHOIS successor defined in RFCs 7480–7484 — and normalizes responses into a flat, consistent format across 1,200+ TLDs.

No more parsing unstructured WHOIS text or nested vcardArray. One API call, one JSON shape, every registry.

## Quick start

```bash
curl -H "Authorization: Bearer YOUR_TOKEN" \
  https://rdapapi.io/api/v1/domain/google.com
```

Returns registrar, registration/expiration dates, nameservers, DNSSEC status, and contact data — all in a single normalized JSON response.

## Features

- **Normalized JSON domain data** — consistent fields across all supported TLDs, no WHOIS parsing
- **Registrar follow-through** — `?follow=true` merges thin registry + registrar RDAP data in one call
- **1,200+ TLDs supported** — gTLDs, ccTLDs, and new TLDs via IANA RDAP bootstrap
- **Bulk domain lookups** — query up to 10 domains in a single request with concurrent upstream fetches
- **Fast & cached** — sub-50ms cached responses, no upstream rate limit issues
- **Simple Bearer auth** — one API key, usage dashboard, predictable pricing

## Use cases

- Domain monitoring and expiration tracking
- Registrar and WHOIS data enrichment
- Brand protection and trademark monitoring
- Security research and threat intelligence
- Domain portfolio management

## Official SDKs

| Language | Package | Install |
|----------|---------|---------|
| Python | [rdapapi](https://pypi.org/project/rdapapi/) | `pip install rdapapi` |
| Node.js | [rdapapi](https://www.npmjs.com/package/rdapapi) | `npm install rdapapi` |
| PHP | [rdapapi/rdapapi-php](https://packagist.org/packages/rdapapi/rdapapi-php) | `composer require rdapapi/rdapapi-php` |
| Go | [rdapapi-go](https://pkg.go.dev/github.com/rdapapi/rdapapi-go) | `go get github.com/rdapapi/rdapapi-go` |
| Java | [rdapapi-java](https://central.sonatype.com/artifact/io.rdapapi/rdapapi-java) | [Maven Central](https://central.sonatype.com/artifact/io.rdapapi/rdapapi-java) |

## Resources

- [API Documentation](https://rdapapi.io/docs) — interactive OpenAPI explorer with live requests
- [TLD Directory](https://rdapapi.io/tlds) — browse all 1,200+ supported TLDs and their RDAP servers
- [Pricing](https://rdapapi.io/pricing) — 7-day free trial, plans from $9/mo
- [Free Domain Lookup](https://rdapapi.io) — try RDAP lookups without signing up
