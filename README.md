# ScraperAPI Credits Explained: What One Request Really Costs, Why Your Balance Drains So Fast, and Which Plan Fits Your Volume (Full Plan Table Inside)

A ScraperAPI credit covers one ordinary page request. Point that same request at Amazon and it costs 5 credits, at Google or Bing 25, at LinkedIn 30, and a page sitting behind Cloudflare, Cloudflare Turnstile, DataDome, PerimeterX or Akamai adds 10 credits once the bypass mechanism activates. The cheapest per-credit rate on the public price list is on Advanced, $1,975 a month for 21,500,000 credits, which works out to about $0.092 per 1,000 credits at the monthly rate.

What follows converts credits into money per task, works out how much allowance a given workload actually needs, and covers the billing behaviour (no rollover, 429s instead of surprise overage charges, annual credits handed out upfront) that decides whether a plan feels cheap or expensive by week three.

## Which plan should most people start on?

Start with the trial, then buy the smallest tier that covers your monthly credit burn rather than the one with the most impressive headline number.

- **Testing the API at all:** 7-day trial with 5,000 API credits, no credit card. The permanent free plan gives 1,000 credits a month and 5 concurrent connections.
- **Plain HTML pages, modest volume:** Hobby at $49/month for 100,000 credits covers 100,000 ordinary pages.
- **Amazon, Walmart or eBay at real volume:** divide credits by 5. 1,000,000 credits buys 200,000 product pages, which puts most catalogue jobs on Startup or Business.
- **SERP or LinkedIn work:** divide by 25 or 30. Google at 25 credits a request means 100,000 credits buys 4,000 queries, so these workloads usually belong on Scaling or above.
- **Country-level targeting outside the US and EU:** Business, $299/month, is the entry point.

👉 [Start the 7-day trial with 5,000 credits](https://www.scraperapi.com/signup?fp_ref=coupons)

## Every ScraperAPI plan and price

All plans share the same core feature set: JS rendering, premium residential and mobile IPs, anti-bot bypass, autoparse, rotating proxy pools, custom headers, CAPTCHA handling, automatic retries, unlimited bandwidth and a 99.9% uptime commitment. What changes between tiers is credits, concurrency, geotargeting, analytics history and whether pay-as-you-go is available.

| Plan | Monthly price | Annual (per month, 10% off) | Credits per month | Concurrent threads | Get it |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | — | 1,000 | 5 | [Free signup](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Hobby | $49 | $44.10 | 100,000 | 20 | [Hobby pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 | [Startup pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 | [Business pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | $475 | $427.50 | 5,000,000 | 200 | [Scaling pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 | 300 | [Professional pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 | 500 | [Advanced pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | [Enterprise quote](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

The columns that decide the upgrade:

| Plan | Geotargeting | Analytics history | Pay-as-you-go |
| --- | --- | --- | --- |
| Free / Hobby / Startup | US and EU only | 30 days (free plan not applicable) | No |
| Business | Country-level, global | Unlimited | No |
| Scaling | Country-level, global | Unlimited | Yes |
| Professional | Country-level, global | Unlimited | Yes, plus priority support |
| Advanced | Country-level, global | Unlimited | Yes, plus priority routing |
| Enterprise | Country-level, global | Unlimited | Yes, dedicated team and Slack |

Paying annually takes exactly 10% off every tier. Multiply the annual monthly figure by twelve to see the actual yearly outlay: Hobby $529.20, Startup $1,609.20, Business $3,229.20, Scaling $5,130, Professional $10,530, Advanced $21,330. Those totals are arithmetic on the published rates, not quoted list prices.

## What one request costs: base rates, bypass surcharges and parameter add-ons

Every request starts from a base rate set by the target domain, because ScraperAPI maintains custom scraping logic for the hard ones.

| Target type | Credits per request | Examples |
| --- | --- | --- |
| Standard page | 1 | Most public websites |
| E-commerce | 5 | Amazon, Walmart, eBay |
| SERP | 25 | Google, Bing, including all subdomains |
| Social media | 30 | LinkedIn |

Anti-bot bypass is charged on top, at 10 credits per scrape, for Cloudflare, Cloudflare Turnstile, DataDome, PerimeterX/Human and Akamai. That surcharge lands automatically when the bypass logic fires. You never request it, so a "cheap" page on a protected domain can quietly cost 11 credits.

Parameters add more:

| Parameter | Extra credits per request |
| --- | --- |
| `premium=true` | 10 |
| `render=true` | 10 |
| `screenshot=true` | 10 |
| `ultra_premium=true` | 30 (paid plans only) |
| `premium=true` + `render=true` | 25 |
| `ultra_premium=true` + `render=true` | 75 (paid plans only) |

Those two combined rates are the ones worth memorising. Premium plus rendering is billed at 25, and ultra-premium plus rendering at 75, which is well above the 30 + 10 you get by adding the individual lines. Custom-discount accounts also carry a higher credit cost on ultra-premium domains, to hold their minimum rate of $3 per thousand requests unrendered and $7 rendered.

Seven parameters cost nothing extra: `wait_for_selector`, `country_code`, `session_number`, `device_type`, `output_format`, `keep_headers=true` and `autoparse=true`. Structured output through autoparse and per-request country selection are free levers, so use them rather than avoiding them.

## Why your credit balance drops faster than the page count suggests

Because the multiplier comes from the target and the parameters, not from your plan. The same 100,000 credits on Hobby is 100,000 plain pages, 20,000 Amazon pages, 4,000 Google queries, or about 1,333 pages with ultra-premium proxies plus rendering.

Here is what 1,000 requests cost at the monthly rate, using Hobby's $0.49 per 1,000 credits against Advanced's roughly $0.092:

| 1,000 requests to | Credits | Cost on Hobby | Cost on Advanced |
| --- | --- | --- | --- |
| A plain page | 1,000 | $0.49 | ~$0.09 |
| Amazon | 5,000 | $2.45 | ~$0.46 |
| Amazon with `render=true` | 15,000 | $7.35 | ~$1.38 |
| A Cloudflare-protected plain page | 11,000 | $5.39 | ~$1.01 |
| Google or Bing | 25,000 | $12.25 | ~$2.30 |
| LinkedIn | 30,000 | $14.70 | ~$2.76 |

Two things fall out of that table. First, search and LinkedIn work costs 25 to 30 times what plain pages cost, which is the single most common reason a plan runs dry mid-month. Second, per-credit price matters less than the multiplier: the gap between Hobby and Advanced is about five times per credit, while the gap between a plain page and a Google query is twenty-five times.

The bypass surcharge deserves its own warning because nobody opts into it. A crawl of 10,000 pages on a Cloudflare-protected site consumes 110,000 credits, more than the entire Hobby allowance, before any rendering or premium proxy settings.

## Which plan fits your workload?

Do the multiplication first: monthly requests × credits per request = credits needed, then buy the tier above that number.

- **Crawl 80,000 plain pages a month.** 80,000 credits. Hobby covers it with room to spare.
- **Track 150,000 Amazon products a month.** 750,000 credits. Startup ($149) covers it. Add `render=true` to those pages and you need 2,250,000, which pushes you to Business.
- **Run 50,000 Google queries a month.** 1,250,000 credits. Startup's 1,000,000 falls 20% short, and Hobby, Startup and Business have no pay-as-you-go, so the realistic options are Business at $299 or Scaling at $475 with PAYG as a buffer.
- **Need non-US/EU geo data.** Business is the floor, regardless of volume. Hobby and Startup are limited to US and EU routing.
- **Volume swings month to month.** Scaling and up, because PAYG at a fixed per-credit rate beats jumping a whole tier for two weeks of peak load.

👉 [Compare every plan and the annual rates](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Billing rules that only show up in the documentation

Credits reset at each renewal date. Unused credits expire, they do not accumulate, so buying a tier you use at 40% is a straight donation.

Annual plans work differently: you receive the full year's credits upfront and can spend them on any timeline. If you burn through them early, you can renew the same annual plan ahead of schedule for a fresh allocation, or fall back on auto-upgrade or PAYG. For a team with lumpy seasonal demand, that upfront allocation is the strongest argument for annual billing, ahead of the 10% discount.

Running out mid-cycle does not trigger a silent overage charge. On Hobby, Startup and Business, scraping pauses until renewal unless you have switched on auto-upgrade, which moves you to the next tier when credits run out. Requests beyond the limit come back as a 429 and cost nothing. On Scaling, Professional, Advanced and Enterprise you can enable pay-as-you-go, billed at a fixed per-credit rate on top of the subscription, with a monthly spending cap you set in the dashboard. PAYG is a limit, not a prepayment, and it is not available below Scaling.

Exceeding your concurrent thread limit also returns a 429. The request is refused rather than queued, and there is no extra charge for hitting the ceiling.

Cancellation is free at any time from the dashboard, and there is a 7-day no-questions-asked refund if the credit math turns out worse than expected.

## How to price a URL before you spend a credit

Three tools remove the guesswork, and they are worth using before any large run rather than after.

The cost endpoint `https://api.scraperapi.com/account/urlcost` accepts every ScraperAPI parameter, so you can get the exact credit cost of a URL and parameter combination before sending a single production request. Every response also carries an `sa-credit-cost` header showing what that request actually consumed, which is the fastest way to catch a multiplier you did not anticipate. Inside the dashboard, the Domain Cost Estimator does the same job on a single URL, and the `max_cost` parameter caps what any one call is allowed to spend.

A practical routine: price ten representative URLs from each target domain, average the `sa-credit-cost` values from a small live batch, multiply by your monthly page count, then compare against the plan table. That number is usually different from the one you estimated from page count alone, and it is the number that should decide your tier.

## ScraperAPI credits FAQ

**Does one credit equal one request?**
Only for standard pages without extra parameters. Amazon, Walmart and eBay cost 5, Google and Bing 25, LinkedIn 30, and anti-bot bypass adds 10 when it triggers.

**Do unused credits roll over?**
No. The balance resets at every renewal date. Annual plans are the exception in practice, since the full year's credits arrive upfront and can be spent on any schedule.

**What happens when credits run out?**
Scraping pauses by default until renewal, or you can enable auto-upgrade to move up a tier. Requests beyond the limit return a 429 with no charge. Pay-as-you-go, which continues past the limit at a fixed per-credit rate with a cap you set, exists only on Scaling, Professional, Advanced and Enterprise.

**Is annual billing really 10% cheaper?**
Yes, exactly 10% off the monthly rate on every public tier, with no difference in credits or features.

**Can I get a refund?**
Within 7 days, no questions asked, via support. Cancelling is free at any point.

**Why is Google so much more expensive than a normal page?**
SERP requests carry a 25-credit base because they run against search infrastructure with dedicated parsing. That is 25 times the cost of a plain page, so budget SERP work separately from your crawling volume.

## Final decision rules

Match the tier to the multiplier, not to the page count in your head. Plain pages only, under 100,000 a month: Hobby at $49. Amazon, Walmart or eBay catalogues up to roughly 200,000 pages: Startup at $149. Needing country-level geotargeting, or more than 600,000 Amazon pages: Business at $299. Any meaningful SERP or LinkedIn workload, or a need for PAYG as an overflow valve: Scaling at $475. Continuous multi-source pipelines past 10 million credits: Professional or Advanced, where the per-credit rate bottoms out around $0.092 monthly.

Two checks before you pay. Run the trial and measure real credits per page with the `sa-credit-cost` header rather than trusting an estimate, and confirm the geotargeting tier you need, since Hobby and Startup will not route outside the US and EU. Get those two right and the plan choice is arithmetic.

👉 [Check current ScraperAPI prices and start the trial](https://www.scraperapi.com/pricing/?fp_ref=coupons)
