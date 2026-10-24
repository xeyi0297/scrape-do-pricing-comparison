# scrape.do pricing: Full Plan and Credit Costs Explained, Plus a ScraperAPI Comparison for Heavy Targets

scrape.do's pricing runs from a free plan with 1,000 credits per month up to $699/month for 10 million credits, and every tier — including the free one — unlocks the entire feature set: residential and mobile proxies, JavaScript rendering, geo-targeting across 160+ countries, sticky sessions, and unlimited bandwidth. There are no feature gates to climb past, which is unusual in this market and worth knowing before you compare anything.

The part most reviews skip: what a single request actually costs you. That's where the real decision lives, so this guide covers the plan table first, then the billing mechanics that change your math, then a side-by-side look at how ScraperAPI prices the same jobs.

> **Quick take:** Start on the free plan (1,000 successful credits/month, no credit card, every feature unlocked) and upgrade only when your monthly volume outgrows it. Hobby at **$29/month for 250,000 credits** covers most small projects. If you're scraping protected targets like Google, Amazon, or LinkedIn at scale, check the per-domain credit costs below before committing — and if the math doesn't work for you, [👉 compare ScraperAPI's current plans and per-domain pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) as the alternative.

## scrape.do pricing at a glance

Six tiers, all billed monthly, all with the same features. Here's the complete current lineup from scrape.do's pricing page:

| Plan | Monthly price | Credits/month | Concurrent requests | Support |
| --- | --- | --- | --- | --- |
| Free | $0 | 1,000 | 5 | Full feature access for testing |
| Hobby | $29 | 250,000 | 10 | Email support |
| Pro | $99 | 1,250,000 | 50 | Priority email support |
| Business *(Most Popular)* | $249 | 3,500,000 | 100 | Dedicated support + team management |
| Advanced | $699 | 10,000,000 | 200 | Custom SLA, dedicated Slack channel |
| Custom / Enterprise | Custom quote | Unlimited | Unlimited | Tailored infrastructure |

A few things worth pulling out of that table. The per-credit price drops as you go up: Hobby works out to $0.11 per 1,000 credits, Pro $0.08, Business $0.07, and Advanced $0.06. Business is the first tier with premium residential and mobile proxies called out, plus the ability to create and manage teams. Advanced is where custom WAF bypass strategies and a custom SLA enter the picture, along with a dedicated Slack support channel. Enterprise is built around your volume, concurrency, and infrastructure needs.

Also note what's *not* tiered: bandwidth is unlimited on every plan, and there are no long-term contracts — you can cancel, upgrade, or downgrade whenever you want.

## What one request actually costs: the credit system explained

scrape.do only charges for successful responses. Failed requests cost nothing — timeouts, blocks, and errors don't touch your balance. And if you get a 200 OK but the content that comes back is garbage, you can contact support and claim back the credits you spent. That refund policy is written directly into their pricing FAQ, and it materially de-risks the free plan: you can test the full platform without bleeding credits on failures.

For domains without special handling, the base cost depends on two parameters you control:

| Request type | Credits |
| --- | --- |
| Normal request (datacenter proxy) | 1 |
| Datacenter + headless browser (`render=true`) | 5 |
| Residential / mobile (`super=true`) | 10 |
| Residential / mobile + headless browser (`super` + `render`) | 25 |

Here's the catch that changes your planning: for a list of high-protection domains, scrape.do applies a default proxy or render profile **server-side**, and you're charged that cost whether or not you pass the parameters yourself. Some examples from their documentation:

- `amazon.*` — 1 credit (routed through their Amazon Scraper API, returns structured JSON)
- `google.*`, `idealista.*`, `leboncoin.fr`, `capterra.com` and several others — 10 credits (residential proxy applied automatically)
- `linkedin.com` — 30 credits (custom infrastructure)
- `shein.*`, `g2.com`, `realestate.com.au` — 25 credits
- `aircanada.com`, `jd.com` — 75 credits
- `shopee.*` — 100 credits (contact support for access)
- `sainsburys.co.uk` — 200 credits (custom anti-detection)

Two practical details most reviews miss. First, every successful response ships with two headers you can read directly: `Scrape.do-Request-Cost` shows what that request consumed, and `Scrape.do-Remaining-Credits` shows what's left in your balance. You don't have to guess or reconcile invoices after the fact. Second, if a target you care about keeps failing on default parameters, you can contact them with the URL pattern and sample responses to get it added to the per-domain list — the infrastructure for this negotiation already exists.

> If your whole project revolves around one expensive domain — say 100 credits per Shopee request — a 250,000-credit Hobby plan is roughly 2,500 successful pages, not 250,000. Do that division before picking a tier.

## Annual billing: pay for 10 months, get 12 — but you have to ask

Annual billing on scrape.do gives up to 20% off, structured as "pay for 10 months and get 12." The confirmed yearly prices:

- Hobby: **$290/year** (vs. $348 billed monthly)
- Pro: **$990/year** (vs. $1,188)
- Business: **$2,490/year** (vs. $2,988)
- Advanced: **$6,990/year** (vs. $8,388)

One friction point to know about: this is currently set up manually. There's no toggle on the pricing page — you reach out via chat or email to support@scrape.do to switch. Enterprise is excluded from annual billing entirely. If you're budgeting for the year, factor in a day or two for that email exchange.

## How scrape.do compares to ScraperAPI on the same jobs

If you're researching scrape.do pricing, you're probably also weighing alternatives. ScraperAPI is the closest structural comparison — a scraping-focused API rather than a raw proxy list, with proxy rotation, retries, CAPTCHA handling, and optional JS rendering handled behind a single endpoint. Here's ScraperAPI's complete current plan lineup:

| Plan | Monthly | Annual (10% off) | Credits/month | Concurrency | Get started |
| --- | --- | --- | --- | --- | --- |
| Free plan | $0 | — | 1,000 | 5 | [ Start free with 1,000 credits](https://www.scraperapi.com/?fp_ref=coupons) |
| Hobby | $49 | $44.10/mo | 100,000 | 20 | [ Check Hobby's current rate](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | $149 | $134.10/mo | 1,000,000 | 50 | [ See Startup plan pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | $299 | $269.10/mo | 3,000,000 | 100 | [ View Business plan details](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling *(Most Popular)* | $475 | $427.50/mo | 5,000,000 | 200 | [ Check the Scaling plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | $975 | $877.50/mo | 10,500,000 | 300 | [ View Professional pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50/mo | 21,500,000 | 500 | [ See Advanced plan pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | — | 22,000,000+ | 500+ | [ Talk to sales about Enterprise](https://www.scraperapi.com/contact-sales/?fp_ref=coupons) |

Every paid ScraperAPI plan includes JS rendering, premium residential and mobile IPs, advanced bypassing, parsing and structured data APIs, DataPipeline, full crawler access, and pay-as-you-go. On top of the monthly plans there's a 7-day free trial with 5,000 credits and no credit card required — separate from the standing free plan that gives 1,000 credits (5 concurrent connections) on signup.

Now the comparison that actually matters — the same domain, priced by each service:

| Target | scrape.do cost | ScraperAPI cost |
| --- | --- | --- |
| Amazon | 1 credit | 5 credits |
| Google | 10 credits | 25 credits |
| LinkedIn | 30 credits | 30 credits |
| Generic datacenter page | 1 credit | 1 credit |
| Cloudflare / Datadome / PerimeterX bypass | Included in per-domain profile | +10 credits per request |

At scale, that Google gap is real: 25 credits per request on ScraperAPI versus 10 on scrape.do means a fixed credit budget covers 2.5x more Google SERP pages on scrape.do. Amazon flips the other way — 1 credit versus 5. One caveat on the table: ScraperAPI prices Google *and* Bing (including subdomains) at 25 credits, but scrape.do's published per-domain list covers `google.*` and doesn't mention Bing, so treat the Bing column as unpriced for scrape.do rather than assuming parity.

Where ScraperAPI argues back:

- **Cost control per request.** You can set a `max_cost` per scrape so a single request can never blow past a limit you define, and the Domain Cost Estimator in the dashboard shows the exact credit cost of any URL before you run it. scrape.do's per-domain pricing is fixed by their server-side profiles; you can see the cost in the response header, but you can't cap it per request the same way.
- **Overage handling.** ScraperAPI offers auto-upgrade on Hobby through Professional (your account moves to the next plan automatically when credits run out) and pay-as-you-go on Scaling and above (keep scraping at a fixed per-credit rate up to a monthly cap you set). scrape.do stops requests once you hit your monthly limit unless you upgrade or buy extra credits — though they do proactively contact you before your balance runs dry.
- **Geo-targeting breadth at the entry tier.** scrape.do includes 160+ country geo-targeting on every plan including the free one. ScraperAPI's Hobby and Startup plans limit geotargeting to US and EU regions; country-level targeting starts at Business ($299/month).
- **Concurrency overage behavior.** Exceed your ScraperAPI plan's thread limit and you get a 429 response — the request is rejected, not queued, and you're not charged. That's a different failure mode than a credit shortage, and worth knowing if you run parallel jobs.

A 2026 third-party review by an operator who has used ScraperAPI since 2023 mainly for price monitoring and SERP tracking put the core criticism plainly: "The credit system punishes exactly the jobs people sign up for." Their math: on a job needing `render=true` plus `premium=true` against a protected target, a single successful scrape can cost 20–30x the headline per-credit price — scraping Amazon search pages with JS rendering enabled, they estimate 1,000,000 credits might cover only 40,000–100,000 actual pages. The same reviewer's verdict on fit: solo developers or small teams running price monitoring, SERP rank tracking, or lead-gen against standard e-commerce targets at 20,000–200,000 pages a month, who don't want to build their own rotation and retry logic. They also flagged the `session_number` sticky sessions capping out around one hour, which matters for account operations or ad verification workflows.

## Questions that come up before you pick a plan

**Does the scrape.do free plan require a credit card?** No. The free plan includes 1,000 successful API calls per month with residential and mobile proxies, geo-targeting, CAPTCHA handling, and JavaScript rendering — no credit card required.

**What happens when I run out of credits mid-month?** scrape.do will contact you before your balance runs low. Once you hit the monthly limit, requests stop until you upgrade or purchase additional credits. There are no surprise overage charges.

**How do I pay?** Credit card or cryptocurrency. Monthly plans over $500 can also be paid by bank wire transfer.

**Can I test with real targets before paying?** On scrape.do, yes — the free plan includes every feature, so you can throw residential proxies and JS rendering at your actual targets on day one. ScraperAPI's approach is a 7-day trial with 5,000 credits, no credit card, which is enough to run real jobs rather than just ping a test endpoint.

**Do I need the paid tiers for serious features?** Not on scrape.do — the tier ladder is about volume, concurrency, and support level, not functionality. On ScraperAPI, the feature set is also uniform across paid plans, but geo-targeting breadth and overage options do vary by tier, as noted above.

## Which plan should you actually pick

A few decision rules based on the verified numbers:

- **Under 250,000 successful requests a month, mixed targets:** scrape.do's Hobby at $29/month is the cheapest paid entry point between the two, and the free plan's 1,000 credits will tell you within days whether your targets clear reliably.
- **Google SERP or Amazon structured data as your main job:** scrape.do's per-domain pricing (10 credits for Google, 1 for Amazon) gives it a clear per-page cost advantage at volume — on Amazon, a 3.5M-credit Business plan covers a lot of product pages.
- **Needs per-request cost caps or automatic overage handling:** ScraperAPI's `max_cost` and Domain Cost Estimator give you tighter spend control per request, and auto-upgrade keeps jobs running without manual intervention. If that operational safety net matters more than raw per-credit price, start there: [👉 see ScraperAPI's plans and start the 7-day free trial](https://www.scraperapi.com/?fp_ref=coupons).
- **Country-level geo-targeting on a budget:** scrape.do includes 160+ countries even on the free plan; ScraperAPI restricts Hobby and Startup to US/EU, so if non-US/EU targets are core to your project and you're staying under $299/month, that's a deciding factor.
- **Long session requirements:** neither service suits hour-spanning sticky sessions at the entry tiers — scrape.do offers sticky sessions across plans, but ScraperAPI's `session_number` caps around an hour per its documentation and third-party reviews, so account-operations use cases should test that behavior before committing.

One last check before you click buy on either: take your three busiest target domains, multiply your monthly page count by the per-request cost for each, and compare that number against the plan credits. The per-domain cost tables — not the headline plan prices — are what determine whether your budget survives the month. If you want a second quote to compare against, [👉 ScraperAPI's full pricing and free trial are here](https://www.scraperapi.com/?fp_ref=coupons).
