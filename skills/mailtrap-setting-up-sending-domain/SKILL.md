---
name: mailtrap-setting-up-sending-domain
description: Verify a sending domain in Mailtrap for production email delivery. Use when setting up DNS records for email sending, configuring SPF, DKIM, and DMARC, or troubleshooting domain verification issues.
metadata:
  category: business
  author: mailtrap
  source:
    repository: https://github.com/mailtrap/mailtrap-skills
    path: skills/setting-up-sending-domain
    license_path: LICENSE
    commit: 73a7113dbab938f716b8a77b3f63b83a91d8be93
---

# Setting Up a Sending Domain with Mailtrap

This skill covers verifying a sending domain in Mailtrap for production email delivery.

## When to Use This Skill

- Setting up a new sending domain for production email
- Configuring SPF, DKIM, and DMARC DNS records
- Troubleshooting domain verification failures
- Improving email deliverability

## Required DNS Records

Mailtrap requires three DNS records to verify your domain:

**SPF** — Authorizes Mailtrap to send on your behalf:
`v=spf1 include:_spf.mailtrap.io ~all`

**DKIM** — Signs outgoing emails cryptographically:
`CNAME mailtrap._domainkey [your-dkim-value].dkim.mailtrap.io`

**DMARC** — Sets policy for failed authentication:
`v=DMARC1; p=none; rua=mailto:dmarc@yourdomain.com`

## Verification Steps

1. Add your domain in Mailtrap → Sending → Domains
2. Add the DNS records shown in the Mailtrap dashboard to your DNS provider
3. DNS propagation typically takes 24-48 hours
4. Click "Verify" in Mailtrap once records are in place

## Related Skills

`mailtrap-sending-emails`, `mailtrap-authorizing-api-requests`
