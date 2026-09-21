---
title: "RBL Leviathan Ghost is racking up government targets across India and Indonesia. Its own proof mostly disagrees."
date: 2026-08-17
week: "Aug 10 – Aug 16, 2026"
category: "DDoS"
severity: "Medium"
excerpt: >-
  A pro-Palestine hacktivist collective is claiming defacements and DDoS hits against Indian
  and Indonesian government sites, and stitching together alliances with other named crews to
  look bigger while it does it. Its own check-host screenshots tell a quieter story.
---
RBL Leviathan Ghost — part of a self-styled "RBL Family" brand — has spent the past few weeks publicly claiming website defacements and DDoS hits against government and public-sector targets in India and Indonesia, while simultaneously announcing new alliances with other hacktivist crews to grow its visible footprint. The claims are loud. The proof it publishes alongside them mostly isn't.

## What happened

The group's activity tracks a familiar hacktivist pattern: pro-Palestine framing (#FreePalestine, #LongLivePalestine), a Telegram channel used as the coordination and announcement hub, and a growing list of claimed hits against public-sector web infrastructure. Documented claims include a defacement of Outlook India's site (site.outlookindia.com) on July 23, 2026, and a DDoS claim against Zila Sahkari Bank (dcbbijnor.bank.in) on July 26. More recent claims, tracked by the threat-intel account FalconFeeds.io on X, add Indonesia's Ministry of Communication and Digital Affairs (komdigi.go.id), Government Polytechnic College Dharmapuri (gptcdharmapuri.co.in), and India's Central Board of Indirect Taxes and Customs (cbic.gov.in) to the list.

Alongside the target claims, the group has been actively building coalition optics: graphics posted to Telegram and amplified on X announce alliances between "RBL Family" and Garuda Kernel Error System ("From Cyber To Brother") and separately with USTAD CYBER TEAM (UCT). Broader reporting on the actor lists it operating within — and crediting — a loosely federated network of 18-plus named groups, including Cyber Team Indonesia, NoName057(16), Akatsuki Cyber Team, Tegal Cyber Team, AnonGhost Official, and others, all cross-promoting each other's claims.

## How the "proof" actually holds up

Each DDoS claim ships with a check-host.net screenshot as evidence — a multi-region HTTP status check the group presents as confirmation of a successful hit. Read closely, they mostly undercut the claim rather than support it:

- **Central Board of Indirect Taxes and Customs (cbic.gov.in):** every monitored region — US, UK, Japan, Germany, Switzerland, Russia, Canada, Sweden, Portugal, Turkey, Vietnam, Indonesia, Brazil — returned `200 OK`. The only non-success was the India-based check node itself, which timed out. A site returning healthy responses from thirteen countries simultaneously is not a site under successful denial-of-service.
- **Government Polytechnic College Dharmapuri (gptcdharmapuri.co.in):** the same pattern — uniform `200 OK` across every region checked, one India-based timeout.
- **Indonesia's Komdigi (komdigi.go.id):** a genuinely mixed result, with some regions returning `200 OK` and others `403 Forbidden`. That split is far more consistent with routine WAF or CDN geo-fencing than with an actual outage — a site selectively blocking certain regions looks identical to this on a check-host report, DDoS or not.

None of that means the group didn't send traffic at these targets. It means the specific evidence it chose to publish, in two of three cases, shows the target fully reachable from most of the world at the moment of the check.

## Why it matters beyond one group

- **Alliance-building scales visibility faster than it scales capability.** Announcing a merger with another named crew costs a Telegram post and a graphic. It's a cheap way to look like a bigger, more coordinated threat than the underlying technical activity necessarily supports.
- **Public evidence-sharing cuts both ways.** Posting check-host screenshots as proof is meant to build credibility. Because the underlying check-host reports are public and independently reviewable, anyone — a defender, a journalist, a competing analyst — can pull the same report and check whether it actually says what the caption claims.
- **This isn't an isolated pattern.** CloudSEK's review of the broader India-Pakistan-adjacent hacktivist surge in 2025 found that a large share of over 100 claimed attacks from various actors were fabricated or exaggerated, with "alleged data leaks containing primarily public information, website defacements leaving no digital footprint, and supposed DDoS attacks... causing negligible disruption." RBL Leviathan Ghost's own published evidence fits that same shape.

## What it means for defenders

- **Don't elevate a claim to an incident until you've checked your own telemetry.** A hacktivist screenshot is not confirmation. If you run a public-sector or .gov-adjacent domain and see yourself named in one of these claims, check your own uptime and WAF logs before treating it as a live event — the group's own evidence often shows the opposite of what it's claiming.
- **Public-sector domains should assume they're on the target list regardless of actual risk.** With 18-plus affiliated groups sharing targeting and tooling under a loose banner, any .gov.in, .go.id, or similar domain is a low-effort, opportunistic target almost by default. Basic rate limiting, WAF coverage, and bot management in front of anything public-facing blunts most of what this tier of actor can actually do.
- **Track coalition activity as a signal, not a threat multiplier.** New "alliance" announcements are worth noting as an indicator the group is trying to expand its reach, but weight your response to actual verified impact — not to the volume or theater of the claims themselves.

The lesson here isn't that RBL Leviathan Ghost is harmless — defacement and opportunistic DDoS attempts against under-hardened public-sector sites are a real, if low-severity, nuisance. It's that the group's own published proof is a reminder to read the evidence, not just the caption.

*Further reading: [Cyberxtron's profile of the coalition targeting Indian infrastructure](https://cyberxtron.com/resources/blogs/hacktivist-attacks-target-india-s-government-critical-infrastructure-education-sectors-ahead-of-independence-day-8004), [FalconFeeds.io's ongoing DDoS-claim tracking on X](https://x.com/FalconFeedsio), and [CloudSEK's analysis of the wider India-Pakistan hacktivist surge](https://www.cloudsek.com/blog/brief-disruptions-bold-claims-the-tactical-reality-behind-the-india-pakistan-hacktivist-surge).*
