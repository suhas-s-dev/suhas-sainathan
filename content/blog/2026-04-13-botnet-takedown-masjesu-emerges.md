---
title: "The DOJ dismantled the botnet behind the largest DDoS on record. A new one was already for sale on Telegram."
date: 2026-04-13
week: "Apr 6 – Apr 12, 2026"
category: "DDoS"
severity: "High"
excerpt: >-
  A real win: US, Canadian, and German authorities took down four IoT botnets responsible
  for over 300,000 DDoS attacks. A month later, a stealthier DDoS-for-hire botnet targeting
  the same device pool was already advertising on Telegram — the vacancy didn't stay open long.
---
On March 19, 2026, the Department of Justice, working with authorities in Canada and Germany, announced the disruption of four IoT botnets — AISURU, Kimwolf, JackSkid, and Mossad — collectively responsible for hijacking more than 3 million devices and launching over 300,000 DDoS attacks. It's a genuine, well-executed law enforcement win. It's also a useful case study in why botnet takedowns rarely mean the underlying problem is solved.

## What happened

The four botnets were the infrastructure behind the record-setting 31.4 Tbps attack from late 2025 and the sustained multi-terabit campaigns that followed it. Authorities attributed roughly 200,000 attacks to AISURU, 90,000 to JackSkid, 25,000 to Kimwolf, and around 1,000 attack commands to Mossad — a combined operation large enough that dismantling it required cooperation across a genuinely wide set of private-sector partners: Akamai, AWS, Cloudflare, DigitalOcean, Google, Lumen, Nokia, Okta, Oracle, PayPal, and several threat-intelligence firms all contributed to the investigation. The operators had been monetizing the botnets two ways — running DDoS-for-hire services and directly extorting victims by threatening to sustain attacks until payment.

## How the takedown worked, and what came next

The scale of coordination here — three national law enforcement bodies plus roughly a dozen infrastructure and security companies — reflects how distributed the botnet's blast radius was. No single company had the full picture; the botnets spanned residential ISPs, cloud providers, proxy networks, and payment rails simultaneously, so the takedown required all of them contributing telemetry and acting on seized infrastructure together.

Less than a month later, researchers disclosed a botnet called Masjesu — also tracked as XorBot for its use of XOR-based encryption — actively operating as a DDoS-for-hire service on Telegram, targeting IoT devices across an unusually broad range of hardware architectures (i386, MIPS, ARM, SPARC, PPC, 68K, and AMD64) from vendors including D-Link, Huawei, and TP-Link. Masjesu had reportedly been running since at least 2023, well before the March takedown, and had already advertised attacks around 290 Gbps. Its operator was subsequently attributed with high confidence to a Turkish national already linked to a wider footprint of criminal infrastructure spanning credential theft and Discord token stealing alongside the DDoS operation.

Masjesu is deliberately smaller and quieter than AISURU ever was — researchers noted it specifically avoids high-profile targets like Department of Defense IP ranges, prioritizing longevity over headline-grabbing scale. That's not a coincidence; it reads like a lesson learned from watching what happens to botnets that get big and loud enough to draw a three-country law enforcement response.

## Why it matters beyond these two stories

- **Takedowns remove infrastructure, not incentive.** The economics that made AISURU profitable — cheap, poorly-secured IoT devices; DDoS-for-hire demand; extortion payouts — didn't go anywhere. A takedown clears the board; it doesn't close the market.
- **The next generation is optimizing for durability over scale.** Masjesu's deliberate avoidance of high-value targets and preference for staying under the threshold that triggers major-power law enforcement attention suggests operators are adapting their risk calculus directly in response to what happened to AISURU.
- **Attribution and takedown capability is real and improving.** The multi-agency, multi-vendor cooperation here is a genuinely higher bar than most past botnet disruptions managed. That's worth acknowledging even while noting it isn't sufficient on its own.

## What it means for defenders

- Don't treat a major botnet takedown as a signal to relax DDoS readiness — if anything, expect displacement to smaller, stealthier operations that are individually less newsworthy but collectively still a live threat to the same device categories.
- If your architecture or supply chain includes IoT and embedded devices across varied hardware architectures, Masjesu's exploit approach (command injection and code execution against consumer router/gateway firmware) is a reminder that device diversity doesn't equal safety — broad architecture support is now a standard feature of commodity botnet malware.
- Keep an eye on DDoS-for-hire markets specifically, not just botnet infrastructure. The operators, tooling, and criminal networks persist across takedowns even when the specific botnet brand changes.

The headline from March was a win. The right way to read it, a month later, is as one data point in an ongoing cycle rather than a resolution.

*Further reading: [Krebs on Security](https://krebsonsecurity.com/2026/03/feds-disrupt-iot-botnets-behind-huge-ddos-attacks/), [The Hacker News on the Masjesu botnet](https://thehackernews.com/2026/04/masjesu-botnet-emerges-as-ddos-for-hire.html), and [SecurityWeek's coverage of the takedown](https://www.securityweek.com/aisuru-and-kimwolf-ddos-botnets-disrupted-in-international-operation/).*
