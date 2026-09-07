# vps provider comparison: what to actually compare beyond price, with BandwagonHost plans broken down tier by tier

When you search "vps provider comparison," what you're usually after isn't a giant table of 50 providers with their RAM and price columns. You already know a $5 box with 1GB RAM exists at ten different companies. What you actually want to know is which differences matter and which are marketing noise — and then, ideally, see one provider's full lineup laid out so you can see what a real decision looks like.

This is that. We'll cover the variables that genuinely change your experience, then walk through BandwagonHost's entire current plan catalog (Basic KVM, CN2 GIA-E, E-Commerce with SLA, the Ultra Hong Kong / Tokyo / Singapore / Osaka lines, plus Dubai) so you can see how the theory maps onto something concrete.

## What most VPS comparisons get wrong

Most comparison posts line up providers by price-per-GB-of-RAM and call it a day. That works for picking a cheap dev box. It falls apart the moment your workload cares about network quality, peak-hour stability, or where the server physically sits.

A few things that get underweighted in typical comparisons:

- **Network routing matters more than bandwidth.** Two providers can both advertise "1 Gbps" and one gives you 30% packet loss to Asia at 9 PM while the other holds steady. The number on the spec sheet is the ceiling, not the experience.
- **vCPU is not CPU.** A "2 vCPU" plan might be 50% of one core or 100% of two. BandwagonHost publishes core allocations per plan in their TOS — many providers don't.
- **Traffic vs bandwidth.** 1 Gbps port with 1 TB/month is a very different product from 1 Gbps unmetered. Both say "1 Gbps."
- **Billing cycle changes the real price.** A plan at $49.99/quarter and the same plan at $169.99/year is a ~15% difference for clicking "annual" instead of "quarterly."
- **Managed vs self-managed is a price multiplier, not a feature.** Self-managed is why BandwagonHost can sell a usable box for $49.99/year. If you need someone to fix Apache at 2 AM, that's a different product category.

Let's go through the variables that actually decide whether a VPS works for you.

## The specs that actually decide whether a VPS is good for you

### RAM and CPU — but read the fine print

RAM is the honest spec. 1GB is 1GB. CPU is where it gets slippery. Look for whether the provider publishes CPU core allocation, not just "vCPU" count. BandwagonHost's TOS lists, for example, that the 80G Basic plan gets 100% of 1 core, the 160G gets 100% of 1 core + 50% of a second, and so on. That's the kind of detail that tells you whether a "4 vCPU" plan is real or shared.

For most personal workloads — a blog, a small app, a VPN, a dev environment — 1–2GB RAM is genuinely enough. People routinely overbuy here.

### Storage type and RAID

NVMe in RAID-10 beats SATA SSD beats single SSD. BandwagonHost has been rolling AMD EPYC + NVMe RAID-10 into New York, Hong Kong (HK3/HK8), and Los Angeles DC9. Older locations still run E5 + RAID-10 SAS. Both are fine; the NVMe nodes are faster on disk-heavy workloads.

### Bandwidth vs monthly traffic

Don't confuse port speed with traffic allowance. BandwagonHost Basic plans give 1 Gbps with 1–6 TB/month depending on tier. CN2 GIA-E starts at 2.5 Gbps. Ultra lines are 1–1.5 Gbps but with much smaller traffic buckets (500GB–8TB) because premium routing is expensive. If you're pushing real volume, the traffic cap matters more than port speed.

### Network routing — the spec nobody puts in the comparison table

This is where BandwagonHost is genuinely differentiated, and it's worth understanding even if you end up buying elsewhere.

China Telecom sells four tiers of IP transit. The cheapest (AS4134 ChinaNet) is congested during peak hours — packet loss can hit 30%+. CN2 GT (AS4809) was supposed to fix this but is now nearly as congested. **CN2 GIA (AS4809 Global Internet Access)** is the premium tier: stable, low packet loss, but transit pricing can reach $120/Mbps in some markets. CTGNet (AS23764) is the newest and performs similarly to CN2 GIA.

If your audience is in mainland China, or you're running cross-border VOIP/video/gaming, regular transit is a functional problem, not a luxury one. BandwagonHost runs 8×10G CN2 GIA/CTGNet links in Los Angeles across two datacenters, plus CN2 GIA in Hong Kong, Tokyo, Osaka, and Singapore. Most comparison tables will never tell you this.

### Datacenter locations and migration

How many locations, and can you move between them? BandwagonHost lets you migrate between datacenters from the KiwiVM panel without data loss. Basic plans cover ~7 locations; CN2 GIA-E covers ~17. That matters when traffic patterns shift or a specific route degrades.

### Virtualization

KVM means real resource isolation. OpenVZ or container-style sharing lets noisy neighbors tank your performance. BandwagonHost is KVM-only. When comparing providers, check this — it's not always prominent.

### Support model

Self-managed means the provider handles hardware, network, and infrastructure; you handle everything above the OS. BandwagonHost is self-managed, and that's the main reason the entry plan is $49.99/year. If you need managed support, cPanel, or someone to call about your Apache config, this category isn't for you regardless of provider.

### Billing cycle and renewal

Always check whether the price is monthly, quarterly, or annual, and whether discounts recur. BandwagonHost's recurring promo codes apply to every renewal, not just checkout — that compounds.

## BandwagonHost's plan tiers, explained

The catalog looks confusing at first because the price range is enormous: $49.99/year up to $18,989.99/year. The mental model is four tiers.

**Basic KVM** — budget entry, standard international routing, ~7 datacenters (Los Angeles DC2/DC4/DC8, Fremont, New Jersey, New York, Vancouver, Amsterdam). Best for personal sites, dev environments, learning Linux, anything where cross-Pacific latency isn't a concern.

**CN2 GIA-E (E-Commerce)** — mid-tier with premium routing. CN2 GIA + CMIN2 + China Unicom Premium triple-network routing, ~17 datacenters including DC6/DC9 in LA, Japan Softbank (Osaka), Netherlands 9929. This is what most people who need reliable cross-Pacific performance should buy. Entry at $49.99/quarter or $169.99/year.

**E-Commerce + SLA** — same routing as CN2 GIA-E but with a 99.99% SLA guarantee, dedicated CPU resources, and IP change every 2 weeks. For e-commerce sellers, TikTok operations, and business apps where uptime is the priority. Priced ~30% higher than standard E-Commerce.

**Ultra (Hong Kong / Tokyo / Singapore / Osaka CN2 GIA)** — premium tier, physically closest to mainland China, lowest latency. Hong Kong and Tokyo start at $89.99/month. Singapore and Osaka are the value picks inside Ultra at $49.99/month entry. For situations where single-digit-ms latency to China actually matters to revenue.

There's also a **Dubai** line (1 Gbps, standard routing) and periodic limited-edition plans ("THE PLAN," "MINICHICKEN") that restock occasionally at a fraction of regular pricing — these sell out fast and are community-tracked.

## Full BandwagonHost plan comparison

Below is every plan currently on the official catalog, grouped by tier. Prices are in USD. Locations and routing notes are included where they meaningfully differ.

### Standard KVM (Basic) — standard international routing

| Plan | RAM | CPU | Storage | Traffic | Link speed | Billing | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 20G KVM | 1 GB | 2 vCPU | 20 GB RAID-10 SSD | 1 TB/mo | 1 Gbps | annual | $49.99/yr | [Get the 20G KVM plan](https://bwh81.net/aff.php?aff=77528&pid=44) |
| 40G KVM | 2 GB | 3 vCPU | 40 GB RAID-10 SSD | 2 TB/mo | 1 Gbps | half-year / annual | $52.99/half-yr or $99.99/yr | [Get the 40G KVM plan](https://bwh81.net/aff.php?aff=77528&pid=45) |
| 80G KVM | 4 GB | 4 vCPU | 80 GB RAID-10 SSD | 3 TB/mo | 1 Gbps | monthly | $19.99/mo | [Get the 80G KVM plan](https://bwh81.net/aff.php?aff=77528&pid=46) |
| 160G KVM | 8 GB | 5 vCPU | 160 GB RAID-10 SSD | 4 TB/mo | 1 Gbps | monthly | $39.99/mo | [Get the 160G KVM plan](https://bwh81.net/aff.php?aff=77528&pid=47) |
| 320G KVM | 16 GB | 6 vCPU | 320 GB RAID-10 SSD | 5 TB/mo | 1 Gbps | monthly | $79.99/mo | [Get the 320G KVM plan](https://bwh81.net/aff.php?aff=77528&pid=48) |
| 480G KVM | 24 GB | 7 vCPU | 480 GB RAID-10 SSD | 6 TB/mo | 1 Gbps | monthly | $119.99/mo | [Get the 480G KVM plan](https://bwh81.net/aff.php?aff=77528&pid=49) |

### CN2 GIA-E (E-Commerce) — premium CN2 GIA + CMIN2 + CUP routing

| Plan | RAM | CPU | Storage | Traffic | Link speed | Billing | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| CN2 GIA-E 20G | 1 GB | 2 vCPU | 20 GB SSD | 1 TB/mo | 2.5 Gbps | quarterly / annual | $49.99/qtr or $169.99/yr | [Get the CN2 GIA-E 20G plan](https://bwh81.net/aff.php?aff=77528&pid=87) |
| CN2 GIA-E 40G | 2 GB | 3 vCPU | 40 GB SSD | 2 TB/mo | 2.5 Gbps | quarterly / annual | $89.99/qtr or $299.99/yr | [Get the CN2 GIA-E 40G plan](https://bwh81.net/aff.php?aff=77528&pid=88) |
| CN2 GIA-E 80G | 4 GB | 4 vCPU | 80 GB SSD | 3 TB/mo | 2.5 Gbps | monthly / annual | $56.99/mo or $549.99/yr | [Get the CN2 GIA-E 80G plan](https://bwh81.net/aff.php?aff=77528&pid=89) |
| CN2 GIA-E 160G | 8 GB | 6 vCPU | 160 GB SSD | 5 TB/mo | 5 Gbps | monthly / annual | $86.99/mo or $879.99/yr | [Get the CN2 GIA-E 160G plan](https://bwh81.net/aff.php?aff=77528&pid=90) |
| CN2 GIA-E 320G | 16 GB | 8 vCPU | 320 GB SSD | 8 TB/mo | 5 Gbps | monthly / annual | $159.99/mo or $1599.99/yr | [Get the CN2 GIA-E 320G plan](https://bwh81.net/aff.php?aff=77528&pid=91) |
| CN2 GIA-E 640G | 32 GB | 10 vCPU | 640 GB SSD | 10 TB/mo | 10 Gbps | monthly / annual | $289.99/mo or $2759.99/yr | [Get the CN2 GIA-E 640G plan](https://bwh81.net/aff.php?aff=77528&pid=92) |
| CN2 GIA-E 1280G | 64 GB | 12 vCPU | 1280 GB SSD | 12 TB/mo | 10 Gbps | monthly / annual | $549.99/mo or $5399.99/yr | [Get the CN2 GIA-E 1280G plan](https://bwh81.net/aff.php?aff=77528&pid=93) |

### E-Commerce + SLA — 99.99% SLA, dedicated CPU, IP rotation

| Plan | RAM | CPU | Storage | Traffic | Link speed | Billing | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| E-Comm SLA 20G | 1 GB | 2 vCPU | 20 GB SSD | 1 TB/mo | 2.5 Gbps | quarterly | $65.89/qtr | [Get the E-Comm SLA 20G plan](https://bwh81.net/aff.php?aff=77528&pid=164) |
| E-Comm SLA 40G | 2 GB | 3 vCPU | 40 GB SSD | 2 TB/mo | 2.5 Gbps | quarterly | $116.99/qtr | [Get the E-Comm SLA 40G plan](https://bwh81.net/aff.php?aff=77528&pid=165) |
| E-Comm SLA 80G | 4 GB | 4 vCPU | 80 GB SSD | 3 TB/mo | 2.5 Gbps | monthly | $69.99/mo | [Get the E-Comm SLA 80G plan](https://bwh81.net/aff.php?aff=77528&pid=166) |
| E-Comm SLA 160G | 8 GB | 6 vCPU | 160 GB SSD | 5 TB/mo | 5 Gbps | monthly | $109.99/mo | [Get the E-Comm SLA 160G plan](https://bwh81.net/aff.php?aff=77528&pid=167) |
| E-Comm SLA 320G | 16 GB | 8 vCPU | 320 GB SSD | 8 TB/mo | 5 Gbps | monthly | $199.99/mo | [Get the E-Comm SLA 320G plan](https://bwh81.net/aff.php?aff=77528&pid=168) |

### Ultra — Hong Kong CN2 GIA (lowest latency to China, 1 Gbps)

| Plan | RAM | CPU | Storage | Traffic | Link speed | Billing | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| HK CN2 GIA 40G | 2 GB | 2 vCPU | 40 GB SSD | 500 GB/mo | 1 Gbps | monthly / annual | $89.99/mo or $899.99/yr | [Browse Hong Kong CN2 GIA plans](https://bwh81.net/aff.php?aff=77528&gid=1) |
| HK CN2 GIA 80G | 4 GB | 4 vCPU | 80 GB SSD | 1 TB/mo | 1 Gbps | monthly / annual | $155.99/mo or $1559.99/yr | [Browse Hong Kong CN2 GIA plans](https://bwh81.net/aff.php?aff=77528&gid=1) |
| HK CN2 GIA 160G | 8 GB | 6 vCPU | 160 GB SSD | 2 TB/mo | 1 Gbps | monthly / annual | $299.99/mo or $2999.99/yr | [Browse Hong Kong CN2 GIA plans](https://bwh81.net/aff.php?aff=77528&gid=1) |
| HK CN2 GIA 320G | 16 GB | 8 vCPU | 320 GB SSD | 4 TB/mo | 1 Gbps | monthly / annual | $589.99/mo or $5899.99/yr | [Browse Hong Kong CN2 GIA plans](https://bwh81.net/aff.php?aff=77528&gid=1) |
| HK CN2 GIA 640G | 32 GB | 10 vCPU | 640 GB SSD | 6 TB/mo | 1 Gbps | monthly / annual | $989.99/mo or $9989.99/yr | [Browse Hong Kong CN2 GIA plans](https://bwh81.net/aff.php?aff=77528&gid=1) |
| HK CN2 GIA 1280G | 64 GB | 12 vCPU | 1280 GB SSD | 8 TB/mo | 1 Gbps | monthly / annual | $1889.99/mo or $18989.99/yr | [Browse Hong Kong CN2 GIA plans](https://bwh81.net/aff.php?aff=77528&gid=1) |

### Ultra — Tokyo / Singapore / Osaka CN2 GIA (entry configs shown)

| Plan | RAM | CPU | Storage | Traffic | Link speed | Billing | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Tokyo CN2 GIA 40G | 2 GB | 2 vCPU | 40 GB SSD | 500 GB/mo | 1.2 Gbps | monthly / annual | $89.99/mo or $899.99/yr | [Browse Tokyo CN2 GIA plans](https://bwh81.net/aff.php?aff=77528&gid=1) |
| Singapore CN2 GIA 40G | 2 GB | 2 vCPU | 40 GB SSD | 500 GB/mo | 1.5 Gbps | monthly / annual | $49.99/mo or $499.99/yr | [Browse Singapore CN2 GIA plans](https://bwh81.net/aff.php?aff=77528&gid=1) |
| Osaka CN2 GIA 40G | 2 GB | 2 vCPU | 40 GB SSD | 500 GB/mo | 1.5 Gbps | monthly / annual | $49.99/mo or $499.99/yr | [Browse Osaka CN2 GIA plans](https://bwh81.net/aff.php?aff=77528&gid=1) |

The Tokyo, Singapore, and Osaka lines each mirror the Hong Kong tier structure (40G / 80G / 160G / 320G / 640G / 1280G) with the same RAM/CPU/storage progression. Singapore and Osaka are the value picks inside Ultra — same CN2 GIA routing, roughly 45% cheaper than Hong Kong at entry level, with 1.5 Gbps vs Hong Kong's 1 Gbps. Tokyo matches Hong Kong pricing but offers 1.2 Gbps. The full plan list for each Asian location is on the 👉 [Ultra plan catalog](https://bwh81.net/aff.php?aff=77528&gid=1).

### Dubai — standard routing, Middle East presence

| Plan | RAM | CPU | Storage | Traffic | Link speed | Billing | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Dubai 20G | 1 GB | 2 vCPU | 20 GB SSD | 500 GB/mo | 1 Gbps | monthly / annual | $19.99/mo or $169.99/yr | [Browse Dubai plans](https://bwh81.net/aff.php?aff=77528&gid=1) |
| Dubai 40G | 2 GB | 3 vCPU | 40 GB SSD | 1 TB/mo | 1 Gbps | monthly / annual | $32.99/mo or $299.99/yr | [Browse Dubai plans](https://bwh81.net/aff.php?aff=77528&gid=1) |
| Dubai 80G | 4 GB | 4 vCPU | 80 GB SSD | 2 TB/mo | 1 Gbps | monthly / annual | $56.99/mo or $549.99/yr | [Browse Dubai plans](https://bwh81.net/aff.php?aff=77528&gid=1) |

Dubai scales up to 1280G (12 vCPU / 64 GB / 1280 GB / 6 TB/mo / $549.99/mo) following the same progression as the table above. It uses standard international routing with access to the same ~17 datacenters as the E-Commerce line.

## Matching a plan to what you're actually doing

A few concrete use-case calls, based on the specs and routing above:

**Personal blog, dev environment, learning Linux.** The 20G KVM at $49.99/year is hard to beat. You get 1GB RAM, 20GB RAID-10 SSD, 1TB traffic, full root, KVM isolation. There is no reason to spend more unless you outgrow it.

**Small business site or app with a global audience, no China emphasis.** 40G or 80G Basic KVM. $99.99/year or $19.99/month. Skip CN2 GIA-E — you're paying for routing you won't use.

**Cross-border site, app, or service with users in mainland China.** CN2 GIA-E 20G at $49.99/quarter or $169.99/year. This is the sweet spot. Premium routing, 2.5 Gbps, ~17 datacenters, and you can migrate between them from the panel. Most people who actually need BandwagonHost end up here.

**E-commerce or TikTok operation where downtime costs money.** E-Commerce + SLA. The 99.99% SLA, dedicated CPU, and IP rotation justify the ~30% premium over standard CN2 GIA-E if uptime is the revenue line.

**VOIP, video conferencing, gaming, or anything where 5ms vs 30ms to China is real.** Hong Kong CN2 GIA. The $89.99/month entry is steep, but you're paying for physical proximity. Singapore or Osaka CN2 GIA at $49.99/month is the compromise if you can tolerate slightly higher latency for roughly half the price.

**Heavy workloads, multi-tenant hosting, large databases.** CN2 GIA-E 320G and up. BandwagonHost isn't competing with Hetzner on raw price-per-core at the high end, but the routing and datacenter flexibility are what you're paying for.

## Billing cycles, promo codes, and where the money actually goes

The biggest easy saving on BandwagonHost is billing cycle selection, not promo codes.

On CN2 GIA-E 20G, quarterly billing works out to $199.96/year. Annual is $169.99/year. That's ~$30 saved by picking the longer cycle — automatic, no code needed. The same pattern holds across the E-Commerce line.

**Promo codes.** BandwagonHost has historically run recurring discount codes — meaning the discount applies to every renewal, not just the first payment. The code `BWHCGLUKKB` (6.77% recurring) has been widely cited across community sites through 2025–2026, and BandwagonHost has run event-specific codes for Double 11 (11% sitewide recurring), Black Friday (10%), and New Year (12.22%). Current validity of any specific code should be checked at checkout — BandwagonHost retires and rotates codes, and not every community-listed code is still live. If a code works, it stacks the saving on top of the billing-cycle discount.

**Limited-edition plans.** Watch for restocks of "THE PLAN," "MINICHICKEN," and similar limited runs. These have historically been priced at a fraction of equivalent regular plans and are community-tracked. They sell out fast.

**In-panel upgrades.** KiwiVM lets you upgrade to a higher tier by paying only the price difference, without re-purchasing. This preserves your setup and any recurring discounts attached to your subscription. Useful when you outgrow a plan.

A 30-day refund policy applies, so a wrong-tier choice is recoverable.

## A reality check on "self-managed"

BandwagonHost is self-managed. That's not a downside — it's why a $49.99/year box with enterprise RAID-10 and KVM isolation exists at that price. But it means:

- You install and configure your web stack, databases, firewalls, and SSL.
- You handle OS-level troubleshooting.
- Support covers hardware, network, and infrastructure failures, not "how do I configure nginx."

KiwiVM, the in-house control panel, covers what you actually need for VPS management: start/stop, OS reload (20+ templates including AlmaLinux, RockyLinux, Debian, Ubuntu, CentOS Stream, Fedora), emergency console, rDNS, snapshots, usage stats, datacenter migration, and an API. No cPanel, no managed WordPress, no phone support for app config.

If you're comfortable on a Linux command line — or willing to learn — this is fine and the pricing reflects it. If you're not, you're looking at the wrong product category regardless of provider. 👉 [See all BandwagonHost plans and current availability](https://bwh81.net/aff.php?aff=77528&gid=1).

## Quick FAQ

**Is BandwagonHost the cheapest VPS?** No. Commodity providers like Hetzner, IONOS, and some Contabo plans beat it on raw price-per-GB-RAM. BandwagonHost competes on network routing (CN2 GIA), datacenter flexibility, and the self-managed KVM model — not on being the absolute cheapest box.

**What's the difference between CN2 GIA-E and Hong Kong CN2 GIA?** Routing quality is similar (both CN2 GIA). Hong Kong is physically closer to mainland China, so latency is lower, but traffic allowances are smaller and prices are roughly double. If latency isn't business-critical, Los Angeles CN2 GIA-E gives you the same routing stability at a fraction of the cost.

**Does BandwagonHost support Alipay / UnionPay?** Yes — Alipay, PayPal, credit card, and UnionPay are all supported.

**Can I switch datacenters after purchase?** Yes, from the KiwiVM panel, without data loss. Basic plans cover ~7 locations; CN2 GIA-E covers ~17.

**What's the uptime guarantee?** Standard plans carry a 99.9% SLA. E-Commerce + SLA plans carry 99.99%. There's a 30-day refund policy.

**Should I wait for a promo code?** Only if your timing is flexible and a known event (Double 11, Black Friday, New Year) is close. Otherwise the annual billing-cycle discount is the reliable saving, and it's available now.

## Bottom line

When you're doing a vps provider comparison, the spec sheet is the easy part. The part that actually determines whether you're happy three months in is network routing, CPU allocation honesty, billing-cycle math, and whether the support model matches what you need. BandwagonHost is a useful case study because it publishes all of this — core allocations in the TOS, routing tiers explained on a dedicated page, every plan with explicit traffic and link-speed numbers.

For most readers: if you don't need China-optimized routing, the Basic 20G KVM at $49.99/year is the honest answer. If you do, CN2 GIA-E 20G at $169.99/year is where the value actually sits. Everything above that is a question of workload size or latency requirements, not general "better."

👉 [Browse the full BandwagonHost plan catalog and check current availability](https://bwh81.net/aff.php?aff=77528&gid=1)
