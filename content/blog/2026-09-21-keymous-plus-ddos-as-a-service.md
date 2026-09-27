---
title: "Keymous+ claims 700+ DDoS attacks since 2023. About a third check out — and it's renting the rest out as a subscription."
date: 2026-09-21
week: "Sep 14 – Sep 20, 2026"
category: "DDoS"
severity: "High"
excerpt: >-
  Keymous+ markets itself as a North African hacktivist collective fighting for causes from
  Morocco to Gaza to Sudan. The infrastructure behind its Telegram announcements is a commercial
  booter service with a price list — and it's become one of the busiest DDoS actors of 2026.
---
Keymous+ first surfaced in November 2023 with a DDoS claim against Morocco's national e-Visa portal. Three years later, it's one of the most prolific hacktivist-branded DDoS actors tracked in 2026 — implicated in the largest coordinated hacktivist wave of the year — while running what researchers increasingly describe not as a cause-driven collective but as a commercial stresser platform wearing a hacktivist Telegram channel as a marketing front.

## What it's been doing in 2026

The clearest data point is the surge that followed the U.S.–Israel military strikes on Iran in late February 2026. Between February 28 and March 2, twelve hacktivist groups launched 149 recorded DDoS claims against 110 organizations across 16 countries. Three groups — Keymous+, DieNet, and NoName057(16) — accounted for 74.6% of all that activity. The Middle East absorbed the bulk of it (107 of 149 attacks, 71.8%), with Kuwait, Israel, and Jordan the three heaviest-hit countries; government targets made up 47.8% of the campaign, finance 11.9%, telecommunications 6.7%. Radware, which tracked the wave, described the regional hacktivist landscape as "heavily lopsided" toward a small handful of high-output groups — Keymous+ chief among them.

That burst sits on top of a steadier drumbeat through 2025 and into 2026: coordinated attacks on German federal portals, tax offices, and telecom providers in April 2025 (alongside NoName057(16)); DNS amplification against French carriers SFR and Bouygues Telecom in July 2025; attacks on Sudan's federal government, Ministry of Finance, and Sudan Railways Corporation in August 2025, tied to the country's civil war; and operations against Pakistani telecom and power infrastructure in November 2025 amid Kashmir tensions. The through-line isn't a fixed enemy — it's whichever conflict is generating headlines that week.

## Two teams, one brand, no consistent ideology

Keymous+ organizes itself into two named divisions: an "Alpha Team" for data breaches and leaks, which researchers assess has gone largely inactive, and a "Beta Team" that handles DDoS operations and does almost all of the group's current public output. The group's own slogan — "Hack for Humanity" — and its participation in branded campaigns like #OpIndia and #OpIsrael suggest an ideological throughline. Its actual target list doesn't cooperate: researchers who've mapped its claims describe the selection as close to random across dozens of countries and sectors, with no consistent enemy beyond "whoever's in the news." That gap between stated cause and observed behavior is why multiple analysts now classify Keymous+ as opportunistic first, ideological second.

![Horizontal bar chart showing Keymous+ claimed targets by sector: Government 27.6%, Telecommunications 10.0%, Financial services 6.5%, all other sectors combined 55.9%.](/images/blog/keymous-plus-sector-targeting.svg)

*Source: [CybelAngel's analysis of Keymous+ targeting data](https://cybelangel.com/blog/keymous-ddos-warfare/).*

Government sites are the single largest identifiable category, consistent with a group that leans on public-sector targets for headline value. But well over half of all claims scatter across education, manufacturing, and other sectors with no obvious pattern — the signature of an actor taking whatever paying or ideologically convenient target comes up next, rather than running a focused campaign.

## EliteStress: the storefront behind the hashtag

The part that separates Keymous+ from a typical hacktivist crew is EliteStress, a tiered DDoS-as-a-service platform researchers assess has an operator-level relationship with the group, even though Keymous+ has never publicly claimed ownership. It's marketed openly on Telegram and X, with subscription pricing that researchers have clocked at anywhere from roughly €5 per day up to €600 a month in mid-2025 reporting, rising to figures as high as €15 a day and €2,100 a month in later 2026 coverage — a jump consistent with a maturing commercial product rather than a static hacktivist tool. The platform offers more than 30 attack methods: DNS, NTP, memcached, CLDAP, and SNMP amplification; TCP SYN and UDP floods; Layer-7 HTTP/2 floods; and spoofed SSH/ICMP traffic layered on top of Tor exit nodes, compromised IoT devices, commercial VPNs, and cloud instances to obscure the source.

![Bar chart comparing Keymous+ attack peaks: a solo attack peaking at 11.8 Gbps versus a joint operation with allied groups peaking at 44 Gbps, roughly 3.7 times larger.](/images/blog/keymous-plus-attack-scale.svg)

*Source: [Orange Cyberdefense's Keymous+ threat profile](https://www.orangecyberdefense.com/fileadmin/global/CyberIntelligenceBureau/Gangs_Investigations/Keymous/Keymous_Plus_Group.pdf) and [CybelAngel](https://cybelangel.com/blog/keymous-ddos-warfare/).*

A solo Keymous+ attack peaks around 11.8 Gbps — not remarkable by 2026 standards. What changes the picture is coordination: joint runs with allied groups like NoName057(16), Mr Hamza, AnonSec, and Moroccan Dragons have pushed observed peaks to roughly 44 Gbps, nearly four times the solo figure. That's the actual value of the alliance-building the group does on Telegram — not just louder claims, but pooled botnet capacity when several crews fire at the same target simultaneously.

The platform's durability is its own data point. Threat-intel tracking in 2026 has tied the same underlying booter infrastructure to multiple rebrands — Orbital Stress, later Goliath Stress — with independent sightings of other, unrelated hacktivist crews (including one tracked as "313 Team") using the same elitestress[.]st infrastructure against unrelated targets. A commercial DDoS-for-hire platform that outlives its own name changes, and gets used by groups that have nothing to do with Keymous+'s stated causes, looks a lot more like enduring criminal infrastructure than a cause's dedicated weapon. Of the 700-plus attacks Keymous+ has claimed since 2023, independent tracking (NETSCOUT's ATLAS telemetry, cited in multiple 2026 write-ups) has only been able to confirm around 249 — meaning a large share of the group's public claims still can't be independently verified either way.

## Why it matters beyond one group

- **Hacktivism and DDoS-for-hire are converging into the same business model.** Keymous+ isn't unusual because it sells attacks — it's unusual because it does so openly while maintaining a hacktivist public identity. Expect more crews to run this hybrid: ideological branding drives free publicity and volunteer goodwill, while the commercial backend pays the bills and keeps the infrastructure running between causes.
- **Alliance networks are functioning as informal botnet-sharing agreements.** The jump from 11.8 Gbps solo to 44 Gbps in coordinated runs shows these Telegram "alliances" aren't just cross-promotion — they're capacity pooling. A defender's threat model for any one group increasingly has to account for who that group can call in.
- **Claimed-attack counts are not a reliable severity signal.** With roughly a third of 700+ claims independently confirmed, treating every group's self-reported tally as ground truth overstates the actual threat — while still leaving genuine, verified high-volume activity that shouldn't be dismissed either.

## What it means for defenders

- **Don't rely on IP or infrastructure attribution alone.** Traffic sourced from Tor exits, compromised IoT, commercial VPNs, and cloud instances simultaneously means source-based blocking will miss most of an EliteStress-powered run. Behavioral and volumetric detection in front of anything public-facing matters more than reputation lists here.
- **Size your mitigation for coordinated, not solo, peaks.** If Keymous+ or an affiliated crew is active against your sector, plan for the ~44 Gbps joint-operation figure, not the ~12 Gbps solo baseline — alliance activity can arrive with little warning once a shared target is announced.
- **Government, telecom, and finance sites tied to any active geopolitical flashpoint should assume opportunistic targeting.** With nearly half of the March 2026 surge's targets in government and no consistent ideological filter on the group's broader target list, exposure tracks current events more than any specific policy your organization has taken.
- **Treat platform takedowns as disruption, not resolution.** EliteStress's survival through at least one name change, and its use by unrelated crews, follows the same pattern seen with NoName057(16)'s DDoSia after Operation Eastwood: seizing servers slows a for-hire platform down — it rarely ends it while the operators and paying customer base stay reachable.

Keymous+'s real innovation isn't a new attack technique — DNS amplification and SYN floods are decades old. It's the business model: hacktivist framing for free marketing, a subscription platform for revenue, and alliance networks for the volume neither could reach alone.

*Further reading: [CybelAngel's "The Hacktivists That Launched 700 DDoS Attacks"](https://cybelangel.com/blog/keymous-ddos-warfare/), [Orange Cyberdefense's Keymous+ threat profile (PDF)](https://www.orangecyberdefense.com/fileadmin/global/CyberIntelligenceBureau/Gangs_Investigations/Keymous/Keymous_Plus_Group.pdf), [Radware's analysis of the post-Iran-strike hacktivist DDoS wave](https://www.rescana.com/post/global-surge-149-hacktivist-ddos-attacks-target-scada-and-critical-infrastructure-across-16-countri), [The Hacker News on the 149-attack, 110-organization campaign](https://thehackernews.com/2026/03/149-hacktivist-ddos-attacks-hit-110.html), and [Mallory.ai's EliteStress infrastructure profile](https://mallory.ai/malware/019e21be-eae1-7714-a6ca-8cd2c4da57fd).*
