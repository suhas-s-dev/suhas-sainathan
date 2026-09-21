---
title: "NoName057(16) got hit by an international takedown in 2025. It came back 80% louder."
date: 2026-08-31
week: "Aug 24 – Aug 30, 2026"
category: "DDoS"
severity: "High"
excerpt: >-
  NoName057(16) is the most persistent pro-Russian DDoS operation running against NATO and
  Ukraine-aligned states — crowdsourced through Telegram, paid in crypto, and still expanding
  more than a year after Europol seized its servers. The data shows why a takedown alone didn't work.
---
Most DDoS actors that make headlines burn bright and disappear. NoName057(16) has done the opposite: it has been running continuously since the week Russia invaded Ukraine, survived a coordinated international law-enforcement operation that seized over a hundred of its servers, and by mid-2026 was hitting more targets per day than before that operation happened. It is, by volume and longevity, the most persistent pro-Russian hacktivist DDoS operation currently active.

## What it's been doing in 2026

The group's target list this year reads like a running commentary on whichever country most recently drew Kremlin displeasure. On January 1, 2026, it claimed attacks on France's postal and banking services (La Poste and La Banque Postale). Through January and February, working alongside a second pro-Russian crew called ServerKillers, it targeted UK public-sector and infrastructure sites and, separately, Spanish government portals and EU-affiliated websites. In early February, it turned toward Italy ahead of the Milano Cortina 2026 Winter Olympics — targeting Olympic websites, hotels in Cortina d'Ampezzo, and Italian Foreign Ministry offices including the embassy in Washington and consulates in Sydney, Toronto, and Paris, framed explicitly as retaliation for Italy's pro-Ukraine stance. Italian authorities said the attacks were mitigated and "not extremely powerful," while acknowledging the group has access to larger botnets that could pose a bigger threat later.

By mid-March, the operational tempo had picked back up: between March 17 and 23, 2026, the group ran its most intensive weekly campaign of the year, generating 13,716 recorded attack instances against 148 unique domains and 134 unique IP addresses. Romania alone absorbed 64.5% of that week's volume — 8,852 of the total — making it by far the single heaviest-hit target of the campaign.

## Who it actually targets

Despite the group's branding as an anti-NATO, anti-Europe operation, the single largest share of its activity over the past year has gone somewhere else entirely.

![Horizontal bar chart showing NoName057(16) targeting by country, July 2024 to July 2025: Ukraine 29.47%, France 6.09%, Italy 5.39%, Sweden 5.29%, Germany 4.60%.](/images/blog/noname05716-top-targets.svg)

*Source: [Picus Security's analysis of DDoSia targeting data](https://www.picussecurity.com/resource/blog/how-noname05716-uses-ddosia-to-attack-nato-targets), July 2024–July 2025.*

Ukraine took 29.47% of all recorded targets over that twelve-month window — more than France, Italy, Sweden, and Germany combined (21.37%). Sector-wise, government and public-sector sites made up 41.09% of targets, followed by transportation and logistics (12.44%) and telecommunications (10.19%). The pattern is consistent with a group whose real organizing purpose is sustaining pressure on Ukraine and its most vocal backers, using whatever NATO-adjacent headline (an Olympics, a state visit, a policy announcement) gives that week's specific target a news hook.

## How DDoSia actually works

DDoSia is the group's purpose-built crowdsourcing tool, written in Go for portability, distributed to volunteers through Telegram. It runs a two-stage process: a client checks in with a command-and-control server (sending basic system details and receiving a validation token), then requests an encrypted target list containing victim IPs, ports, and protocol parameters designed to vary requests enough to slip past basic filtering. The infrastructure behind it is tiered for resilience — short-lived public-facing proxy servers, averaging roughly nine days before rotation, sit in front of longer-lived backend servers that stay shielded from takedown attempts.

The attack traffic itself is unremarkable by design: Slow Loris-style connection exhaustion accounts for about 31.5% of methods used, SYN floods 17.6%, ACK floods 16.1%, and HTTP GET floods 15.4%, with roughly two-thirds of all traffic aimed at ports 80 and 443. None of this is novel tradecraft — the group's advantage is entirely in scale and persistence, not sophistication.

What makes the model durable is the incentive structure. Volunteers don't need any technical skill beyond running an app; they're paid in cryptocurrency for successful attacks, with a 2026 academic study from Aalto University's School of Business — led by Assistant Professor Hadi Ghanbari — describing rewards as high as $1,200 per successful attack. The researchers frame this explicitly as "gamified" warfare: a leaderboard-and-reward structure borrowed from cybercrime-for-hire models, wrapped in hacktivist and nationalist messaging, aimed at a psychological objective — undermining public trust in institutions — as much as a technical one. Their case study cites Finland specifically: 23 separate rounds of attacks since January 2025, affecting 129 organizations.

## Operation Eastwood: a real takedown that didn't stick

In July 2025, Europol and Eurojust coordinated Operation Eastwood — simultaneous action across Czechia, France, Finland, Germany, Italy, Lithuania, Poland, Spain, Sweden, Switzerland, the Netherlands, and the United States. The results were genuinely substantial for a hacktivist-DDoS case: more than 100 servers seized, two arrests (one in France, one in Spain), seven European arrest warrants issued, 24 house searches, and 13 individuals questioned. Authorities also sent direct Telegram warnings to roughly 1,100 DDoSia participants and 17 channel administrators, putting them on notice of potential criminal liability — a deliberate attempt to shrink the volunteer pool through deterrence, not just infrastructure loss.

It worked, briefly. The group went quiet for about five days immediately after the raids. Then it came back larger than before.

![Bar chart showing average daily targeted sites before and after Operation Eastwood: 10 per day from June 24 to July 13, 2025, rising to 18 per day from July 24 to August 13, 2025 — an 80 percent increase.](/images/blog/noname05716-eastwood-before-after.svg)

*Source: [Imperva's post-operation impact analysis](https://www.imperva.com/blog/operation-eastwood-measuring-the-real-impact-on-noname05716/).*

Comparing the twenty days before the operation to the twenty days after it, the group's average daily target count rose from about 10 sites per day to about 18 — an 80% increase. Its post-operation targeting also shifted noticeably toward the countries that had participated in the raid: Germany alone absorbed roughly half of the group's attacks in the weeks that followed, hitting municipalities, police departments, and government portals specifically in the nations that had gone after it. Researchers also logged 13 separate claims of deeper system intrusions beyond simple DDoS in the weeks after Eastwood — including claims against water-treatment facilities in Romania and Czechia, industrial control systems in Lithuania, and a desalination plant in Spain, though the extent of verified impact behind those specific claims is less well established than the DDoS volume data.

The honest read on Eastwood, echoed across the researchers who studied it afterward, is that it delivered "a significant, though not decisive, blow." It proved international law enforcement can cooperate effectively against this kind of crowdsourced infrastructure, and it did impose real cost and real fear on part of the volunteer base. What it couldn't do is reach the leadership or infrastructure sitting inside Russia, where there's no cooperating law enforcement partner to make an arrest or a server seizure. Take away the servers and volunteers you can reach, and the operators rebuild what's reachable while the unreachable core stays untouched.

## Why it matters beyond one group

- **A takedown against a state-tolerated actor is containment, not resolution.** Eastwood is a genuinely well-executed multinational operation, and it still didn't reduce the group's output a month later. When the actor's core infrastructure and leadership sit in a jurisdiction that won't cooperate, expect displacement and rebound rather than a clean win — the same pattern seen with IoT DDoS botnets after takedowns.
- **The psychological objective is the point, not a side effect.** Framing these campaigns as "gamified" isn't just a colorful description — the Aalto University research argues the actual goal is eroding public confidence in targeted institutions, which changes what a successful defense looks like. Mitigating the traffic isn't sufficient if the story that gets told afterward is "the government's website was down."
- **Retaliation shifted onto the countries that fought back.** The post-Eastwood targeting tilt toward Germany is not a coincidence — it's the group publicly demonstrating that participating in a takedown carries a cost, which is itself a psychological-warfare move aimed at future law-enforcement cooperation as much as at Germany specifically.

## What it means for defenders

- **The attack methods are commodity floods, not zero-days.** Slow Loris variants, SYN/ACK floods, and HTTP GET floods dominate DDoSia's toolkit. Standard L7 DDoS mitigation, rate limiting, and WAF coverage in front of ports 80/443 handles the overwhelming majority of what this group actually throws — the gap is usually deployment, not defense technology.
- **Government, transport, and telecom sector organizations in NATO and Ukraine-aligned states should assume they're on a rotating target list.** With government/public-sector targets making up over 40% of recorded activity, any public-facing agency site in a country that takes a visible pro-Ukraine or anti-Russia position should treat DDoSia-style floods as a "when," not "if" — timed to line up with news events, summits, or symbolic dates.
- **Plan your communications response as seriously as your technical one.** Since the campaign's actual goal is reputational and psychological, a fast, transparent public statement that a mitigated attack occurred and service was maintained undercuts the narrative the group is trying to build far more than silence does.
- **Don't expect a single law-enforcement action to end sustained harassment from this actor.** Track Eastwood as the template: real disruption, real cost imposed, but plan your defenses assuming the group's operational tempo returns to — or exceeds — pre-takedown levels within weeks.

NoName057(16) isn't dangerous because any single attack is sophisticated. It's dangerous because it has proven, across four years and one major international takedown, that it can keep showing up.

*Further reading: [Picus Security's technical breakdown of DDoSia](https://www.picussecurity.com/resource/blog/how-noname05716-uses-ddosia-to-attack-nato-targets), [Imperva's analysis of Operation Eastwood's real impact](https://www.imperva.com/blog/operation-eastwood-measuring-the-real-impact-on-noname05716/), [SOCRadar's coverage of the March 2026 Romania campaign](https://socradar.io/blog/romania-under-ddos-25-mar26/), [Security Affairs on the Milano Cortina Olympics attacks](https://securityaffairs.com/187654/hacktivism/pro-russian-group-noname05716-launched-ddos-attacks-on-milano-cortina-2026-winter-olympics.html), and [coverage of the Aalto University "gamified DDoS" research](https://techxplore.com/news/2026-08-gamified-ddos-wage-psychological-warfare.html).*
