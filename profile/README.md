# RDAP API — Modern WHOIS Lookup API for Developers

**[RDAP API](https://rdapapi.io)** is a REST API that replaces WHOIS with structured JSON lookups for domains, IP networks, ASNs, nameservers, and entities. It queries [RDAP](https://rdapapi.io/docs) (Registration Data Access Protocol) — the official WHOIS successor defined in RFCs 7480–7484 — and normalizes responses into a flat, consistent format across 1,200+ TLDs and all five RIRs.

No more parsing unstructured WHOIS text or nested vcardArray. One API call, one JSON shape, every registry.

## Quick start

```bash
curl -H "Authorization: Bearer YOUR_TOKEN" \
  https://rdapapi.io/api/v1/domain/google.com
```

Returns registrar, registration/expiration dates, nameservers, DNSSEC status, and contact data — all in a single normalized JSON response.

## Endpoints

| Endpoint | Returns |
|----------|---------|
| `GET /api/v1/domain/{domain}` | Registrar, dates, nameservers, EPP status codes, DNSSEC, contacts |
| `POST /api/v1/domains/bulk` | Up to 10 domains in one pooled request (Pro and Business) |
| `GET /api/v1/ip/{ip}` | Network range, holder, country, abuse contacts, geofeed URL |
| `GET /api/v1/asn/{asn}` | Autonomous system holder, country, registration dates |
| `GET /api/v1/nameserver/{host}` | Host record: addresses, status, sponsoring registrar |
| `GET /api/v1/entity/{handle}` | Organization or contact by RIR handle |
| `GET /api/v1/tlds` | Every supported TLD, its server, and per-field availability — never billed |

## Features

- **Normalized JSON** — consistent fields across all supported TLDs and RIRs, no WHOIS parsing
- **WHOIS fallback** — ccTLDs with no RDAP server are read over WHOIS and returned in the same shape, marked `source: whois`
- **Registrar follow-through** — `?follow=true` merges thin registry + registrar RDAP data in one call
- **1,200+ TLDs supported** — gTLDs, ccTLDs, and new TLDs, including registries missing from IANA's bootstrap file
- **Bulk domain lookups** — up to 10 domains per request with concurrent upstream fetches
- **MCP server** — the same lookups as tools for AI agents at [rdapapi.io/mcp](https://rdapapi.io/mcp)
- **Fast & cached** — sub-50ms cached responses, no upstream rate limit issues
- **Simple Bearer auth** — one API key, usage dashboard, predictable pricing

## Use cases

- Domain monitoring and expiration tracking
- Registrar and WHOIS data enrichment
- Brand protection and trademark monitoring
- Security research and threat intelligence
- Network and ASN attribution
- Domain portfolio management

## Official SDKs

All clients cover domain, bulk, IP, ASN, nameserver, and entity lookups.

| Language | Package | Install | Source |
|----------|---------|---------|--------|
| Python | [rdapapi](https://pypi.org/project/rdapapi/) | `pip install rdapapi` | [python-sdk](https://github.com/rdapapi/python-sdk) |
| Node.js | [rdapapi](https://www.npmjs.com/package/rdapapi) | `npm install rdapapi` | [node-sdk](https://github.com/rdapapi/node-sdk) |
| PHP | [rdapapi/rdapapi-php](https://packagist.org/packages/rdapapi/rdapapi-php) | `composer require rdapapi/rdapapi-php` | [rdapapi-php](https://github.com/rdapapi/rdapapi-php) |
| Go | [rdapapi-go](https://pkg.go.dev/github.com/rdapapi/rdapapi-go) | `go get github.com/rdapapi/rdapapi-go` | [rdapapi-go](https://github.com/rdapapi/rdapapi-go) |
| Java | [rdapapi-java](https://central.sonatype.com/artifact/io.rdapapi/rdapapi-java) | [Maven Central](https://central.sonatype.com/artifact/io.rdapapi/rdapapi-java) | [java-sdk](https://github.com/rdapapi/java-sdk) |

## Resources

- [API Documentation](https://rdapapi.io/docs) — interactive OpenAPI explorer with live requests
- [MCP Server](https://rdapapi.io/mcp) — RDAP lookups as tools for AI agents
- [TLD Directory](https://rdapapi.io/tlds) — browse all 1,200+ supported TLDs and their RDAP servers
- [RDAP Coverage Stats](https://rdapapi.io/stats) — how much of the DNS answers over RDAP, backend concentration, certificate health
- [WHOIS Sunset Tracker](https://rdapapi.io/whois-sunset) — where each registry stands in the ICANN WHOIS-to-RDAP transition
- [Blog](https://rdapapi.io/blog) — RDAP protocol guides, migration walkthroughs, and comparisons
- [Pricing](https://rdapapi.io/pricing) — 7-day free trial, plans from $9/mo
- [Free Domain Lookup](https://rdapapi.io) — try RDAP lookups without signing up
