---
layout: post
title: "SaaS Pricing Strategy Workshop"
categories: [playbooks]
---

SaaS Pricing Strategy Workshop

frameworks · models · teardowns · implementation

`SaaS` 
`Pricing` 
`MBA Workshop` 
`Revenue Growth` 
`Monetisation` 

Pricing is the most underleveraged growth lever in SaaS. Most companies spend hundreds of hours on acquisition, dozens on retention, and approximately zero on pricing. This is a mistake. A 10% improvement in pricing yields a 12.7% improvement in profit — more than a 10% improvement in volume (3.3%) or a 10% reduction in variable costs (7.8%).

This workshop is designed to give you the frameworks, models, and practical tools to audit, design, and implement pricing for any SaaS product. Every section includes worked examples, real company teardowns, and templates you can apply immediately.

**Who this is for:** MBA interns working on growth strategy, product managers owning monetisation, founders setting pricing for the first time, and anyone who has ever said "we should probably raise our prices" but didn't know where to start.

---


Part I

Pricing Foundations

Before you touch a pricing page, you need to understand why pricing matters more than you think, what a value metric is, and how to measure what customers are actually willing to pay.

# 01 Why Pricing Is the #1 Lever

Here is a simple truth that most SaaS operators ignore: **a 10% price increase is a 10% ARR increase at zero incremental CAC**. No new leads. No new pipeline. No new reps. Just more revenue from the same customers.

Compare the three growth levers side by side:

| Lever | Action | Effort | Impact on Profit | Timeline |
| --- | --- | --- | --- | --- |
| **Pricing** | Raise prices 10% | **Low** | **+12.7%** | Immediate |
| **Churn Reduction** | Reduce churn by 10% | **Medium** | +6.7% | 6–12 months |
| **Acquisition** | Increase volume 10% | **High** | +3.3% | 3–6 months |
| **Cost Reduction** | Cut variable costs 10% | **Medium** | +7.8% | 1–3 months |

Source: McKinsey & Company pricing study across 2,400+ companies. The profit impact numbers assume typical SaaS cost structures.

Despite this, most SaaS companies underprice by **20–40%**. Why?

- **Fear of churn.** Founders are terrified that raising prices will cause customers to leave. In practice, a 10% price increase rarely causes more than 1–2% incremental churn — the math overwhelmingly favours the increase.
- **Anchoring to competitors.** "Our competitor charges $49/mo, so we charge $39/mo." This ignores that your product may deliver different (or more) value. Competing on price is a race to the bottom.
- **Set and forget.** The founding team set pricing in 2019 based on vibes. It's 2026. The product has 10x more features. The price hasn't changed.
- **No ownership.** Nobody owns pricing. It falls between Product, Sales, Marketing, and Finance. Everyone assumes someone else is handling it.

> **Insight:** Pricing is the highest-leverage, lowest-effort growth lever in SaaS. If you haven't touched your pricing in the last 12 months, you are almost certainly leaving money on the table.

## The Pricing Impact Calculator

Here's a worked example. Assume a SaaS company with these metrics:

| Metric | Current | After 10% Price Increase | Delta |
| --- | --- | --- | --- |
| ARR | $5,000,000 | $5,500,000 | **+$500,000** |
| Customers | 1,000 | 985 (1.5% churn from increase) | -15 |
| ARPU | $5,000 | $5,584 | **+$584** |
| Net Revenue Impact | — | — | **+$425,000** |
| CAC to acquire $425K via new logos | — | — | **~$340,000** (at 5:1 LTV:CAC) |

> **The math:** A 10% price increase on a $5M ARR business nets ~$425K after accounting for 1.5% incremental churn. To get that same $425K through new customer acquisition, you'd need to spend ~$340K in sales and marketing. **Pricing is free. Acquisition is not.**

---

# 02 The Value Metric

The **value metric** is what customers pay for that scales with the value they receive. It is the single most important decision in your pricing architecture. Get it right and revenue grows naturally as customers succeed. Get it wrong and you either leave money on the table or create perverse incentives.

## What Makes a Good Value Metric

| Criteria | What it means | Example |
| --- | --- | --- |
| **Aligned with value** | As the customer gets more value, the metric increases | Stripe charges % of revenue processed — as you sell more, they earn more |
| **Easy to understand** | The customer can predict their bill | "$10/seat/month" is clear. "0.03 credits per API compute unit" is not. |
| **Scales with the customer** | Revenue grows as the customer grows, without renegotiation | Seats scale as a team grows. Flat rate does not. |
| **Hard to game** | Customers can't manipulate the metric to reduce their bill | Seats can be shared (gameable). Revenue processed cannot (not gameable). |

## Common SaaS Value Metrics

| Value Metric | Companies Using It | Pros | Cons |
| --- | --- | --- | --- |
| **Seats / Users** | Slack, Salesforce, Figma, Notion | Easy to understand, predictable | Seat-sharing, resistance to adding users |
| **Usage / Volume** | Twilio (messages), Stripe (transactions), Snowflake (compute) | Perfect value alignment, natural expansion | Unpredictable bills, harder to forecast |
| **Contacts / Records** | HubSpot, Mailchimp, Intercom | Grows with business size, easy to track | Penalises data hygiene (keeping old contacts) |
| **Revenue Processed** | Stripe, Shopify Payments, Paddle | Direct value capture, scales perfectly | Only works for payment/financial products |
| **Projects / Workspaces** | Vercel, Linear, Notion | Scales with organisational complexity | Can be gamed by consolidating projects |
| **Features / Tier** | Most SaaS (Starter/Pro/Enterprise) | Simple, encourages upgrades | No natural expansion within a tier |

## How to Find Your Value Metric

Interview 20 customers. Ask these three questions:

---

**Value Metric Discovery Interview** · 3 core questions

**Q1:** "If you had to measure whether our product is worth what you pay, what number would you look at?"  
  
**Q2:** "What does success look like for you when using our product? How would you measure it?"  
  
**Q3:** "If our price doubled tomorrow, what would you need to see more of to justify it?"  
  

Listen for patterns. If 12 of 20 customers say "the number of reports generated" or "the number of team members using it" — that's your value metric.

---

> **The test:** A good value metric passes this sentence: "The more \_\_\_\_\_ the customer uses, the more value they get, and the more they should pay." If you can fill in the blank and it feels fair to both sides, you've found it.

---

# 03 Willingness to Pay Research

You cannot set prices by guessing. You need data on what customers will actually pay. Two proven methods:

## Method 1: Van Westendorp Price Sensitivity Meter

The Van Westendorp method uses four questions to map the boundaries of acceptable pricing. Survey at least 100 prospects or customers.

---

**The Four Van Westendorp Questions**

**Q1 — Too Cheap:** "At what price would you consider this product to be so cheap that you'd question its quality?"  
  
**Q2 — Cheap / Good Deal:** "At what price would you consider this product a bargain — a great deal for the money?"  
  
**Q3 — Expensive / Getting Pricey:** "At what price would you consider this product to be getting expensive — not out of reach, but you'd have to think about it?"  
  
**Q4 — Too Expensive:** "At what price would you consider this product too expensive to consider purchasing?"

---

### How to Interpret the Results

Plot cumulative distributions of all four answers. The intersections give you:

| Intersection | What it means | How to use it |
| --- | --- | --- |
| **Point of Marginal Cheapness (PMC)** | "Too Cheap" crosses "Expensive" | Your price floor — below this, customers won't trust you |
| **Point of Marginal Expensiveness (PME)** | "Too Expensive" crosses "Cheap" | Your price ceiling — above this, too many say no |
| **Indifference Price Point (IDP)** | "Cheap" crosses "Expensive" | The "expected" price — where equal numbers say cheap vs expensive |
| **Optimal Price Point (OPP)** | "Too Cheap" crosses "Too Expensive" | Where the fewest people reject the price on either extreme |

> **Example result:** You survey 150 mid-market SaaS buyers about a project management tool. PMC = $12/seat/mo, OPP = $18/seat/mo, IDP = $22/seat/mo, PME = $35/seat/mo. **Your acceptable range is $18–$35/seat/mo.** Most companies would have guessed $10–$15 and left 40%+ on the table.

## Method 2: Gabor-Granger (Simpler)

When you don't have 100+ survey respondents, Gabor-Granger works with smaller samples. It's simpler but less nuanced.

---

**Gabor-Granger Method**

**Step 1:** Show a price. Ask: "Would you buy this product at $X/month?"  
  
**Step 2:** If YES → increase price by 20%. Ask again.  
  
**Step 3:** If NO → decrease price by 20%. Ask again.  
  
**Step 4:** Continue until you find the threshold. Repeat across 30+ respondents.  
  
**Output:** A demand curve showing % of people who would buy at each price point. Multiply price × demand to find the revenue-maximising price.

---

> **When to use which:** Use Van Westendorp when you have access to 100+ respondents and want the full picture (acceptable range, optimal point). Use Gabor-Granger when you have fewer respondents (30–50) and just need a revenue-maximising price quickly.

---


Part II

The Six Pricing Models

Every SaaS product uses one (or a combination) of these six models. Understanding the tradeoffs of each is essential before you design or redesign your pricing.

# 04 Flat Rate Pricing

One product, one price, every customer pays the same thing. The simplest possible model.

| Attribute | Detail |
| --- | --- |
| **How it works** | Single price for all features, all users, unlimited usage. $99/mo and you get everything. |
| **When it works** | Simple product, single persona, narrow use case. No meaningful difference between a small and large customer. |
| **When it fails** | No expansion revenue. A 10-person team and a 500-person team pay the same. You leave enormous value on the table with larger customers. |

## Case Study: Basecamp

---

**Basecamp Pricing Teardown**

**Model:** Flat rate — $349/month for unlimited users, unlimited projects  
  
**Why they chose it:** Basecamp's philosophy is simplicity. They don't want customers thinking about per-seat costs when adding team members. They believe "pricing shouldn't be a spreadsheet exercise."  
  
**The tradeoff:** A 5-person startup pays $349/mo ($69.80/user). A 500-person company pays $349/mo ($0.70/user). Basecamp is effectively giving away 99% of the value to large customers.  
  
**Why it works for them:** Their brand is built on being the anti-enterprise tool. Their TAM is SMBs who value simplicity. The flat rate *is* the product positioning.  
  
**Why it wouldn't work for you:** If you have customers ranging from 5 to 5,000 users, flat rate means your largest customers get an incredible deal and your smallest customers subsidise them. You also have zero expansion revenue — no net revenue retention above 100%.

---

> **The flat rate trap:** Flat rate pricing caps your NRR (Net Revenue Retention) at 100%. You can never earn more from an existing customer. In SaaS, the best companies have NRR of 120–140%+. Flat rate makes that mathematically impossible.

---

# 05 Per Seat Pricing

The most common B2B SaaS model. Each user (seat) costs a fixed amount per month.

## Mechanics

| Element | How it works |
| --- | --- |
| **Price structure** | $X per user per month. Typically $8–$30 for team tools, $50–$200 for enterprise platforms. |
| **Billing** | Usually monthly or annual. Annual gets a 15–20% discount. |
| **Expansion** | Revenue grows naturally as companies add team members. This is the primary expansion vector. |
| **Minimums** | Enterprise deals often include seat minimums (e.g., 50-seat minimum at $150/seat/mo = $90K ARR floor). |

## Per Seat Pricing: Pros and Cons

| Pros | Cons |
| --- | --- |
| **Predictable revenue** — easy for both you and the customer to forecast | **Seat-sharing** — teams share logins to avoid paying for more seats |
| **Scales with adoption** — as more people use it, revenue grows | **Resistance to expansion** — managers hesitate to add seats because of direct cost |
| **Simple to explain** — "$15/user/month" requires zero explanation | **Doesn't capture usage value** — a power user and a light user pay the same |
| **Aligns with org growth** — as the company hires, your revenue increases | **Discourages adoption** — champions may not roll out to full team to keep costs down |

## Real Company Teardowns

| Company | Per Seat Price | Annual Discount | Free Tier | Enterprise |
| --- | --- | --- | --- | --- |
| **Slack** | Pro: $8.75/user/mo   Business+: $12.50/user/mo | ~15% (billed annually) | Yes (limited history) | Custom pricing |
| **Salesforce** | Starter: $25/user/mo   Professional: $80/user/mo   Enterprise: $165/user/mo | Annual only (no monthly option) | No | $330/user/mo |
| **Figma** | Professional: $15/editor/mo   Organisation: $45/editor/mo | ~20% (billed annually) | Yes (3 projects) | $75/editor/mo |

### How to Set Your Per-Seat Price

1. **Calculate value delivered per user.** If your tool saves each user 5 hours/week and their loaded cost is $75/hr, you deliver ~$1,500/mo in value per user.
2. **Apply the 10:1 value ratio.** Customers should get 10x the value they pay. $1,500 value / 10 = $150/user/mo maximum. This is the ceiling.
3. **Run willingness-to-pay research.** Van Westendorp or Gabor-Granger to find the acceptable range.
4. **Set price at 70–80% of the WTP ceiling.** Leave room for annual discounts and enterprise negotiation.

> **Insight:** Slack's genius move: they only charge for active users. If someone on your team hasn't used Slack in 14 days, they're automatically deactivated and you don't pay. This removes the biggest objection to per-seat pricing ("I'm paying for people who don't use it") and dramatically increases willingness to roll out company-wide.

---

# 06 Usage-Based Pricing

The customer pays per unit consumed. No fixed fee, no seats — you pay for what you use. This is the fastest-growing pricing model in SaaS.

## How It Works

| Component | Detail |
| --- | --- |
| **Unit** | API calls, messages sent, compute hours, GBs stored, transactions processed |
| **Pricing** | Per-unit rate, often with volume tiers (first 10K at $0.01, next 100K at $0.008, etc.) |
| **Billing** | Monthly in arrears. Customer is billed for actual usage after the fact. |
| **Minimums** | Often includes a monthly minimum commit (e.g., $500/mo minimum, usage above that billed per unit) |

## Usage-Based Pricing: Pros and Cons

| Pros | Cons |
| --- | --- |
| **Perfect value alignment** — customers only pay for what they use | **Revenue unpredictability** — hard to forecast next quarter's revenue |
| **Natural expansion** — as usage grows, revenue grows automatically | **Customer anxiety** — "how much will I owe this month?" |
| **Low barrier to entry** — start small, scale up. No upfront commitment. | **Hard to budget** — procurement teams hate unpredictable costs |
| **NRR can exceed 150%+** — the best usage-based companies see massive expansion | **Churn sensitivity to macro** — in downturns, usage drops and so does revenue |

## Real Company Teardowns

| Company | Value Metric | Pricing | NRR |
| --- | --- | --- | --- |
| **Stripe** | Revenue processed | 2.9% + $0.30 per transaction | **>100%** |
| **Twilio** | Messages / calls | $0.0079/SMS, $0.015/min voice | **~131%** |
| **Snowflake** | Compute credits + storage | $2–$4/credit (varies by tier), $23/TB/mo storage | **~158%** |
| **Datadog** | Hosts monitored + logs ingested | $15/host/mo + $0.10/GB logs | **~130%** |

> **Why usage-based NRR is insane:** Snowflake's NRR of 158% means the average customer spends 58% more each year without any upselling effort. That's because as their data grows, compute usage grows. Revenue is a function of customer success. This is the holy grail of SaaS monetisation.

### How to Set Usage-Based Rates

1. **Calculate your cost per unit.** Infrastructure cost (compute, bandwidth, storage) per unit of consumption. Add a healthy margin (70–85% gross margin target).
2. **Benchmark against competitors.** If Twilio charges $0.0079/SMS and you charge $0.05/SMS, you need to justify 6x with differentiated value.
3. **Design volume tiers.** Reward growth: higher volume = lower per-unit price. This encourages consolidation onto your platform.
4. **Consider committed-use discounts.** "Commit to $10K/mo and get 30% off per-unit rates." This gives you revenue predictability while giving them savings.

---

# 07 Tiered Packages

The Starter / Pro / Enterprise model. The most common pricing page design in SaaS. Three (sometimes four) packages at escalating price points with increasing features, limits, and support levels.

## How to Design Tiers

| Tier | Target Buyer | Key Characteristics | Typical Price Range |
| --- | --- | --- | --- |
| ****Starter**** | Solo users, small teams, evaluators | Core features. Low limits. Self-serve. No support SLA. | $0–$49/mo |
| ****Pro / Growth**** | Growing teams, mid-market companies | Advanced features. Higher limits. Priority support. Integrations. | $49–$299/mo |
| ****Enterprise**** | Large organisations, regulated industries | Full feature set. Unlimited or custom limits. SLA. SSO/SAML. Dedicated support. Custom contracts. | "Contact Sales" |

## The Decoy Effect (Asymmetric Dominance)

The middle tier should be designed to look like the obvious best deal compared to the other two. This is called the **decoy effect** — the lower and upper tiers make the middle tier look like incredible value.

---

**Worked Example: Project Management SaaS**

**Starter — $12/user/mo**  
5 projects, 10GB storage, email support  
  
**Pro — $24/user/mo** **MOST POPULAR**  
Unlimited projects, 100GB storage, priority support, integrations, reporting  
  
**Enterprise — $45/user/mo**  
Everything in Pro + SSO/SAML, audit logs, 99.9% SLA, dedicated CSM, custom integrations  
  

The jump from Starter ($12) to Pro ($24) doubles the price but adds 10x the value (unlimited projects, 10x storage, integrations). The jump from Pro ($24) to Enterprise ($45) nearly doubles the price but mainly adds compliance features most mid-market companies don't need. Result: 60–70% of customers choose Pro.

---

> **The psychology:** Good/Better/Best works because humans avoid extremes. Given three options, most people pick the middle one. If you design your tiers so the middle option has the best value-to-price ratio, you can predict that 60–70% of customers will land there — and you can set that tier's price accordingly.

## Real Company Teardown: HubSpot

| Tier | Price | Key Limits | Target |
| --- | --- | --- | --- |
| **Free** | $0 | 1,000 contacts, basic CRM, email marketing | Solo founders, evaluators |
| **Starter** | $20/mo | 1,000 contacts, remove HubSpot branding, basic automations | Small teams getting started |
| **Professional** | $890/mo | 2,000 contacts, full automation, reporting, ABM, custom properties | Growing mid-market teams |
| **Enterprise** | $3,600/mo | 10,000 contacts, advanced reporting, custom objects, predictive lead scoring | Large marketing organisations |

Notice the massive price jump from Starter ($20) to Professional ($890). HubSpot's value metric is contacts, but the real gate is features. The Professional tier is where the product becomes genuinely useful for a real marketing team. This is intentional — the free and Starter tiers exist to get you hooked.

## Tier Design: What Goes Where

| What to Gate | Where to Put It | Why |
| --- | --- | --- |
| Core functionality | **Starter / Free** | If the base product isn't useful, nobody upgrades |
| Collaboration features (sharing, teams, permissions) | **Pro** | Collaboration = more users = more seats = natural expansion trigger |
| Automation / workflows | **Pro** | Automation delivers measurable ROI that justifies the upgrade |
| Integrations | **Pro** | Once embedded in their stack, switching costs skyrocket |
| Reporting / analytics | **Pro** or **Enterprise** | Managers and execs need reporting — they authorise budgets |
| SSO / SAML / audit logs | **Enterprise** | Compliance requirements. Only large companies need this. High willingness to pay. |
| SLA / uptime guarantee | **Enterprise** | Only enterprise procurement requires contractual SLAs |
| Dedicated support / CSM | **Enterprise** | High cost to deliver. Only viable at enterprise price points. |

---

# 08 Hybrid Pricing

Most modern SaaS companies don't use a single model — they combine two or more. This is **hybrid pricing**, and it's increasingly the default for companies at scale.

## Common Hybrid Structures

| Structure | How it works | Example |
| --- | --- | --- |
| **Platform Fee + Usage** | Fixed monthly fee for access. Usage billed on top. | Datadog: $15/host/mo (platform) + $0.10/GB logs (usage) |
| **Per Seat + Usage Overage** | Per-seat price includes a usage allowance. Overage billed per unit. | Intercom: per-seat price includes 1,000 conversations/mo. Above that, $0.99/conversation. |
| **Tiered Package + Seat-Based** | Choose a tier (features), then pay per seat within that tier. | Salesforce: choose Starter/Professional/Enterprise tier, then pay per seat. |
| **Free Tier + Usage** | Generous free tier. Pay only when you exceed free limits. | Vercel: free for hobby projects. Pro plan at $20/mo + usage for bandwidth/builds/functions beyond included limits. |
| **Base + Modules** | Core platform at a fixed price. Add-on modules at incremental cost. | HubSpot: buy Marketing Hub, then add Sales Hub, Service Hub as separate line items. |

## How to Structure a Hybrid Model

---

**Hybrid Pricing Design Framework**

**Step 1: Identify your base value.**  
What does every customer need? This becomes the platform fee or base tier. It should cover your cost to serve + margin.  
  
**Step 2: Identify your expansion vector.**  
What grows as the customer gets more value? Seats? Usage? Contacts? This becomes the variable component.  
  
**Step 3: Set the ratio.**  
Aim for 60–70% of revenue from the predictable component (platform fee + seats) and 30–40% from the variable component (usage). This balances predictability with expansion.  
  
**Step 4: Include a buffer.**  
Give each tier a usage allowance so customers don't get surprised by overage charges. The allowance should cover the 50th percentile of usage. Only the top 25–30% of customers should trigger overage billing.

---

> **The hybrid advantage:** Platform fee gives you revenue predictability (CFO loves it). Usage component gives you natural expansion (CRO loves it). Tiered features give you an upgrade path (Product loves it). Hybrid is harder to design but dramatically better for the business.

---

# 09 Freemium

Freemium is not a pricing model — it's a **customer acquisition strategy**. You give away a limited version of your product for free, and convert a small percentage to paid. It works spectacularly well for some companies and is a slow death sentence for others.

## When Freemium Works

| Condition | Why it matters | Example |
| --- | --- | --- |
| **Product-led growth (PLG)** | Users discover, adopt, and expand without talking to sales | Slack, Notion, Figma |
| **Viral / network effects** | Free users invite other users, creating organic growth | Dropbox (shared folders), Calendly (scheduling links) |
| **Large TAM** | You need millions of free users to get enough paid conversions at 2–5% | Canva (1B+ potential users globally) |
| **Low marginal cost (COGS)** | It costs you nearly nothing to serve a free user | Software with no compute-heavy features |
| **Self-serve onboarding** | Users can get value without human help — otherwise free users just create support tickets | Notion (templates), Figma (tutorials) |

## When Freemium Does NOT Work

| Condition | Why it fails | What to do instead |
| --- | --- | --- |
| ****High COGS**** | If each free user costs you $5–10/mo in compute, you bleed money | Free trial (14–30 days) instead of freemium |
| ****Complex onboarding**** | If users need hand-holding to get value, free users create support costs with zero revenue | Guided demo / POC instead of free tier |
| ****Small TAM**** | If your TAM is 5,000 companies, 2–5% conversion gives you 100–250 paying customers. Not enough. | Free trial + sales-assisted conversion |
| ****Enterprise-only product**** | Enterprise buyers don't "try" products for free. They run POCs and evaluations through procurement. | POC / pilot program with sales involvement |

## Freemium Benchmarks

| Metric | Good | Great | Best in Class |
| --- | --- | --- | --- |
| **Free-to-Paid Conversion Rate** | 2–3% | 4–5% | **7%+ (Slack, Zoom)** |
| **Time to Convert** | 30–90 days | 14–30 days | **<14 days** |
| **Free User Activation Rate** | 20–30% | 40–50% | **60%+** |
| **Free User Cost (COGS/user)** | <$1/mo | <$0.25/mo | **<$0.05/mo** |

### Designing the Free Tier

The free tier should be **valuable enough to be useful, limited enough to create upgrade pressure**. Two approaches:

FEATURE-LIMITED

---

Give full access to core features but limit advanced functionality.  
  
**Example (Notion):**  
Free: Unlimited pages, basic blocks, 5MB file uploads, 7-day page history  
Paid: Unlimited file uploads, 30-day history, databases, API access, bulk export

---

USAGE-LIMITED

---

Give full features but cap usage volume.  
  
**Example (Mailchimp):**  
Free: All email features, up to 500 contacts, 1,000 sends/mo  
Paid: Unlimited contacts, unlimited sends, automation, A/B testing

---

> **The free tier mistake:** If your free tier is too generous, nobody upgrades. If it's too restrictive, nobody gets enough value to care. The sweet spot: 80% of free users should hit a limit within 30 days that makes them *want* to upgrade, not *need* to. The trigger should feel like growth, not frustration.

---


Part III

The Pricing Audit

You've learned the models. Now apply them. This section gives you an 8-step framework to audit any SaaS company's pricing and a guide to designing the pricing page.

# 10 How to Audit Your Current Pricing

Use this 8-step framework to evaluate any SaaS product's pricing — whether it's your own company or a case study target.

## Step 1: Map Current Pricing Structure

Document exactly what you charge, how you charge it, and what's included at each level.

---

**Pricing Structure Map Template**

**Model type:** [Flat / Per Seat / Usage / Tiered / Hybrid / Freemium]  
**Value metric:** [What do customers pay per unit of?]  
**Tiers:** [List each tier, price, and key inclusions]  
**Add-ons:** [Any optional modules or overages]  
**Discounts:** [Annual, volume, enterprise negotiated]  
**Free tier:** [Yes/No, what's included]  
**Last price change:** [Date and nature of change]

---

## Step 2: Revenue Per Customer Distribution

Pull a histogram of revenue per customer. You're looking for the shape of the distribution.

| Distribution Shape | What it means | Action |
| --- | --- | --- |
| **Tight cluster** (most customers pay similar amounts) | Your pricing may be too flat. No expansion happening. | Introduce usage-based or tiered components |
| **Long right tail** (a few customers pay much more) | Healthy. Your large customers are expanding. | Protect these accounts. Consider dedicated enterprise tier. |
| **Bimodal** (two clusters) | You likely have two distinct segments with different needs. | Design tiers explicitly for each segment. |
| **Lots of very low-paying customers** | Your entry price may be too low, or free-to-paid conversion is happening but upgrade isn't. | Raise entry price or redesign upgrade triggers. |

## Step 3: Value Metric Alignment

Ask: **Are customers paying in proportion to the value they receive?**

- Identify your top 10 happiest customers (highest NPS or CSAT). What do they pay? What value do they get?
- Identify your top 10 churned customers. What did they pay? Did they feel they were paying too much for too little?
- If happy customers are paying very little (value >> price), you're underpricing.
- If churned customers felt the price was too high relative to value, your value metric is misaligned.

## Step 4: Churn Analysis by Price Tier

| Tier | Monthly Churn Rate | Signal |
| --- | --- | --- |
| Free | N/A (they never paid) | Track activation and conversion instead |
| Starter | **5–8%** (high for Starter is normal) | SMBs churn more. If above 8%, your product isn't delivering enough value at this tier. |
| Pro | **2–4%** | If above 4%, investigate. These customers are invested enough to pay more — what's failing? |
| Enterprise | **<1%** | Enterprise rarely churns. If above 2%, it's a product-market fit or implementation issue. |

## Step 5: Competitive Comparison

Map your pricing against the top 3–5 competitors on these dimensions:

- Price per unit (seat, API call, etc.) at equivalent tiers
- What's included at each tier vs what's gated
- Value metric used (are they charging for the same thing?)
- Free tier / trial structure
- Enterprise pricing model (per-seat, custom, consumption)

> **Important:** Competitive analysis informs — it doesn't dictate. If you deliver 2x the value of a competitor, you should charge more, not match their price. The goal is to understand the market context, not to race to the bottom.

## Step 6: Willingness to Pay Survey

Run a Van Westendorp or Gabor-Granger study (see Section 03). Segment by company size, use case, and buyer persona. Different segments will have very different WTP.

## Step 7: Identify Expansion Gaps

Look for moments where customers hit a limit but have no way to upgrade incrementally.

---

**Common Expansion Gaps**

**Gap 1: Cliff between tiers.** Pro is $49/mo and Enterprise is $499/mo. Customers at $49 who need *one* enterprise feature (like SSO) can't justify 10x the price. **Fix:** add SSO as a $50/mo add-on to Pro.  
  
**Gap 2: No usage overage.** Pro includes 10,000 API calls. Customer hits 12,000. They either upgrade to Enterprise (overkill) or stay on Pro and lose data. **Fix:** add per-unit overage at $0.01/call above the limit.  
  
**Gap 3: Seat bundles too large.** You sell in packs of 10 seats. A team of 12 has to buy 20 seats and pay for 8 empty ones. **Fix:** allow individual seat purchases or smaller bundles.  
  
**Gap 4: Annual-only Enterprise.** A growing startup wants Enterprise features but can't commit to annual. **Fix:** offer monthly Enterprise at a premium (20–30% more than monthly equivalent of annual price).

---

## Step 8: Model Three Pricing Scenarios

Build a financial model with three scenarios and project the impact over 12 months:

| Scenario | Change | Model These Metrics |
| --- | --- | --- |
| ****A: Raise 10%**** | Increase all prices by 10% for new customers | New ARR, churn impact (assume 1–3% incremental), net revenue change |
| ****B: Restructure Tiers**** | Redesign tiers based on WTP data and expansion gaps | Conversion rates by tier, ARPU change, upgrade rate change |
| ****C: Add Usage Component**** | Introduce usage-based billing on top of existing structure | NRR impact, expansion revenue, bill shock risk, forecast accuracy |

> **Insight:** The most underrated step is #7 (expansion gaps). Most SaaS companies lose 15–25% of potential expansion revenue because customers hit ceilings with no incremental way to pay more. Finding and fixing these gaps is often the single highest-ROI pricing change you can make.

---

# 11 Pricing Page Design

Your pricing page is the most visited page on your site after the homepage. It's where buyers decide if they can afford you, if you're serious, and which plan to choose. Here's what the best pricing pages get right.

## The Anatomy of a Great Pricing Page

| Element | Best Practice | Why |
| --- | --- | --- |
| **Number of tiers** | 3 tiers visible. 4 max (if you include Free). | More than 4 = choice paralysis. Conversion drops. |
| **Highlighted tier** | Visually emphasise the "recommended" tier (usually middle). Larger card, different colour, "Most Popular" badge. | Anchoring + social proof. 60–70% of customers pick the highlighted one. |
| **Comparison table** | Full feature comparison below the pricing cards. Checkmarks and X marks. | Enterprise buyers need to justify the purchase. They send this table to procurement. |
| **Annual/Monthly toggle** | Default to annual. Show monthly price with annual savings badge ("Save 20%"). | Annual billing improves cash flow and reduces churn. The toggle makes the discount visible. |
| **Enterprise tier** | "Contact Sales" with a short list of enterprise-specific features (SSO, SLA, custom contracts). | Signals you serve enterprise. Prevents sticker shock. Lets sales customise. |
| **Social proof** | Logos of customers, testimonials, or "X,000 companies trust us" below the pricing cards. | Reduces perceived risk. "If Stripe uses it, it must be good enough for us." |
| **FAQ section** | Answer the 5–8 most common pricing questions (billing cycle, cancellation, overages, team plans). | Removes friction. Every unanswered question is a reason to delay the purchase. |

## Pricing Page Teardown: Notion

---

**What Notion Gets Right**

**1. Four clear tiers:** Free, Plus ($10/user/mo), Business ($18/user/mo), Enterprise (Contact Sales)  
  
**2. Annual default:** Toggle defaults to annual pricing. Monthly shows a higher price, making annual feel like a deal.  
  
**3. "Most Popular" on Business:** The Business tier is highlighted. This is their target tier for growing teams.  
  
**4. Feature comparison below:** A detailed table with every feature and which tier includes it. This is the page enterprise buyers screenshot and send to their manager.  
  
**5. Free tier is generous:** Unlimited pages for individuals. This is the PLG hook — get individuals addicted, then the team plan sells itself.  
  
**6. Simple value metric:** "Per member per month." Everyone understands it. No compute units, credits, or confusing metrics.

---

> **The pricing page test:** Show your pricing page to someone who has never seen your product for 10 seconds, then take it away. Ask: (1) How many plans are there? (2) Which one would you pick? (3) What does the product do? If they can answer all three, your pricing page works. If they can't, simplify.

---


Part IV

Experiments & Implementation

You've audited your pricing. You know the models. Now it's time to make changes — and that means raising prices, running experiments, managing discounts, and building a process for ongoing review.

# 12 How to Raise Prices

Raising prices is the scariest thing most SaaS teams do. It doesn't have to be. Here's the playbook that minimises risk and maximises revenue impact.

## The Price Increase Playbook

| Step | Action | Detail |
| --- | --- | --- |
| **1** | **Test on new cohorts first** | Raise prices only for new customers. Existing customers keep their current price. Measure conversion rate, ACV, and churn at 30/60/90 days. |
| **2** | **Grandfather existing customers** | Give existing customers 6–12 months at their current price. Communicate early and clearly: "Your price stays the same until [date]." |
| **3** | **Communicate value, not price** | The announcement should lead with what's improved (new features, better performance, expanded support), not the price change. Frame it as "we've invested significantly in the product." |
| **4** | **Offer an early lock-in** | "Lock in your current rate for 2 years by switching to annual billing before [date]." This converts monthly customers to annual AND reduces churn from the price change. |
| **5** | **Measure at 30/60/90 days** | Track: conversion rate (new customers), churn rate (existing customers at new price), support ticket volume, NPS change. |
| **6** | **Roll back if needed** | If churn exceeds 5% incremental or conversion drops by more than 20%, roll back and try a smaller increase. |

## Price Increase Communication Template

---

To: **All Customers** · Email

**Updates to [Product] plans**

Hi [Name],  
  
Over the past 12 months, we've shipped [specific improvements — 3–4 bullet points]. These investments have made [Product] significantly more powerful, and our customers are seeing real results: [1–2 customer proof points].  
  
To continue investing at this pace, we're updating our pricing effective [date — 60+ days out]. Your current plan of [current plan] at [current price] will move to [new price].  
  
**What this means for you:**  
• Your price stays the same through [grandfather date].  
• If you'd like to lock in your current rate for the next 2 years, switch to annual billing before [date].  
• All features you currently have will remain — nothing is being removed.  
  
If you have any questions, reply to this email or book time with your account manager: [link].  
  

[CEO Name]  
Founder & CEO, [Company]

---

> **Why this template works:** (1) Leads with value delivered, not cost increase. (2) Gives 60+ days notice. (3) Offers a lock-in option that converts monthly-to-annual. (4) Comes from the CEO (signals importance and respect). (5) Grandfather period reduces churn shock.

> **Expected impact of a well-executed 15–20% price increase:** Incremental churn of 1–3%. Net ARR increase of 12–17%. 20–30% of monthly customers convert to annual (lock-in offer). Support ticket volume spikes for 2 weeks, then normalises. NPS dips 2–5 points for 1 quarter, then recovers.

---

# 13 Pricing Experiments

How to test pricing changes without betting the company on a guess.

## A/B Testing Pricing: The Rules

| Rule | Why |
| --- | --- |
| **Never show different prices to the same segment simultaneously** | If Customer A tells Customer B they pay different prices for the same product, you destroy trust. Regulators in some jurisdictions consider this discriminatory pricing. |
| **Use cohort-based tests, not user-level A/B tests** | Test new pricing on a new cohort (all signups in April get Price B). Compare to the previous cohort (all signups in March had Price A). |
| **Test for 60–90 days minimum** | Pricing impacts show up in churn at 30–60 days, not at conversion. A 7-day test tells you nothing useful. |
| **Measure LTV, not just conversion** | Price A may convert better but churn faster. Price B may convert worse but retain longer. You need the full picture. |

## What to Measure in a Pricing Experiment

| Metric | Timeframe | What it tells you |
| --- | --- | --- |
| **Conversion Rate** | Immediate | Is the price deterring signups? |
| **Average Contract Value (ACV)** | At close | Are customers choosing higher or lower tiers? |
| **Time to Close** | First 30 days | Is the price creating more friction in the sales cycle? |
| **30-Day Churn** | 30 days post-conversion | Early signal of price-value mismatch |
| **90-Day Churn** | 90 days post-conversion | True retention signal. The most important metric. |
| **NRR (Net Revenue Retention)** | 6–12 months | The ultimate test. Does the new pricing generate more or less revenue from each cohort over time? |
| **LTV** | 12+ months | Lifetime revenue per customer. The north star. |

## Experiment Design: Worked Example

---

**Experiment: Testing a 20% price increase on Pro tier**

**Hypothesis:** Increasing Pro tier from $49/mo to $59/mo will reduce conversion by <10% but increase ACV by 20%, resulting in net positive revenue impact.  
  
**Control (Cohort A):** All signups in March — see $49/mo Pro pricing.  
**Test (Cohort B):** All signups in April — see $59/mo Pro pricing.  
  
**Sample size:** Need 200+ signups per cohort for statistical significance on conversion.  
  
**Measurement window:** 90 days from start of each cohort.  
  
**Success criteria:**  
• Conversion drop < 10% (from 5.0% to no less than 4.5%)  
• 90-day churn no more than 1.5% higher  
• Revenue per cohort (ACV × conversions × retention) is higher for Cohort B  
  
**Decision:** If all criteria met, roll $59 pricing to all new customers. If conversion drops >10% but retention is identical, try $54 as a middle ground.

---

---

# 14 Discount Strategy

Discounts are the most abused tool in SaaS sales. Used well, they accelerate deals and lock in long-term revenue. Used poorly, they destroy pricing integrity and train buyers to always ask for less.

## When to Discount

| Scenario | Discount Type | Typical Range | Why It's Okay |
| --- | --- | --- | --- |
| **Annual prepay** | Monthly → Annual | **15–20% off** | You get cash upfront + lower churn. The discount pays for itself. |
| **Multi-year commit** | 1-year → 2-year or 3-year | **20–30% off** | Locked-in revenue. Reduces churn risk to near zero for that period. |
| **Strategic logo** | Below-standard pricing for a marquee customer | **Up to 40% off** | The logo is worth it for marketing, case studies, and social proof. But only for genuinely strategic accounts. |
| **Volume commitment** | Higher seat count or usage volume | **10–25% off** | Higher volume = lower cost to serve per unit. Pass some savings through. |

## When to NEVER Discount

| Scenario | Why It's Destructive | What to Do Instead |
| --- | --- | --- |
| ****To close a deal faster**** | Trains the buyer that "if I wait, I get a discount." Every future deal starts with "what discount can I get?" | Add value instead. Include extra onboarding, a premium support tier, or an extended pilot — same price, more value. |
| ****To match a competitor**** | You've now established that your product is worth no more than the competitor's. You've erased your differentiation. | Compete on value, not price. Show the ROI delta. If your product saves them $200K/yr and theirs saves $100K, your higher price is justified. |
| ****End-of-quarter panic**** | The buyer knows your quarter ends. They wait until the last week. You cave. Now every deal closes in the last week of the quarter at a discount. | Build pipeline discipline. If a deal needs a discount to close this quarter, it probably shouldn't close this quarter. |
| ****To retain a churning customer**** | If the customer is leaving because of price, discounting only delays the inevitable. They'll churn anyway. You've just reduced revenue in the meantime. | Understand the real reason for churn. If it's product fit, no discount helps. If it's genuine budget, offer a downgrade path instead. |

## Discount Authority Matrix

| Discount Level | Who Can Approve | Required Justification |
| --- | --- | --- |
| ****0–10%**** | AE (Account Executive) | Annual commitment or 50+ seat deal |
| ****11–20%**** | Sales Manager | Multi-year commitment or 200+ seat deal |
| ****21–30%**** | VP Sales | Strategic logo with case study commitment |
| ****31–40%**** | CEO | Exceptional strategic value (top-10 logo, platform partnership) |
| ****40%+**** | Never | At this level you're paying the customer to use your product. Walk away. |

## The Trade-for-Trade Framework

Never give a discount without getting something in return. Every concession should be a trade.

---

**Trade-for-Trade Examples**

"I can do **15% off** if you sign a **2-year term** instead of 1-year."  
  
"I can do **10% off** if you commit to **100 seats** instead of 50."  
  
"I can do **20% off** if you agree to a **published case study** within 6 months."  
  
"I can waive the **onboarding fee** if you pay **annually upfront**."  
  
"I can match that price if you **sign by Friday** and remove the **legal redlines**."  
  

The psychology: when you give something, ask for something. It signals that your pricing has integrity. The buyer respects you more, not less.

---

> **Insight:** The best sales teams have a discount rate under 8% of list price on average. The worst have 25%+. The difference is not generosity — it's discipline, value selling, and a clear discount policy that everyone follows.

---

# 15 The Pricing Committee

Pricing is too important to be owned by one person and too cross-functional to be owned by one team. You need a Pricing Committee.

## Who Sits on the Pricing Committee

| Role | Why They're There | What They Bring |
| --- | --- | --- |
| **CEO / Founder** | Pricing is a strategic decision that affects positioning, brand, and investor narrative | Long-term vision. Willingness to make bold moves. |
| **VP Sales / CRO** | Sales deals with pricing objections daily. They know what customers say and what competitors charge. | Win/loss data. Discount patterns. Competitive intelligence. |
| **VP Product** | Product owns the features that define tiers and the value metric. | Feature roadmap. Usage data. Product-market fit signals. |
| **VP Finance / CFO** | Finance models the revenue impact of pricing changes and owns the P&L. | Financial models. Scenario analysis. Margin requirements. |
| **VP Marketing** (optional) | Marketing owns the pricing page, positioning, and competitive messaging. | Competitive landscape. Messaging. Conversion data from pricing page. |

## How Often to Review Pricing

| Frequency | What to Review | Typical Outcome |
| --- | --- | --- |
| **Quarterly** | Discount trends, win/loss by price, churn by tier, competitive moves, expansion revenue trends | Minor adjustments: discount policy tweaks, tier limit changes, add-on pricing |
| **Bi-annually** | Full pricing audit (8-step framework from Section 10). WTP research if available. | Moderate changes: price increases, tier restructuring, new add-ons |
| **Annually** | Strategic pricing review. Does our model still fit our market? Are we in the right model (per-seat vs usage vs hybrid)? | Major changes: model shift, new value metric, pricing page redesign |

## The Quarterly Pricing Review: What to Bring

---

**Pricing Committee Quarterly Agenda**

**1. Revenue Dashboard** (Finance)  
• ARR, ARPU, NRR by tier  
• Revenue per customer histogram  
• Expansion and contraction revenue trends  
  
**2. Win/Loss Analysis** (Sales)  
• Win rate by tier  
• Average discount given (by tier, by AE, by deal size)  
• Top 5 losses where price was the stated reason  
• Competitive pricing intelligence updates  
  
**3. Product Usage Data** (Product)  
• Feature usage by tier (are Pro features being used? Are Enterprise features worth the price?)  
• Usage patterns near tier limits (are customers hitting ceilings?)  
• Upcoming features that could justify price changes  
  
**4. Churn & Retention** (Finance / CS)  
• Churn by tier and by price point  
• Downgrade patterns (who's moving to lower tiers and why)  
• NPS by price tier  
  
**5. Recommendations** (All)  
• Proposed changes with financial models  
• Experiment designs for testing changes  
• Timeline for implementation

---

> **The discipline:** Companies that review pricing quarterly grow revenue 30% faster than companies that set-and-forget. The review doesn't have to result in changes every quarter — often the data confirms your current pricing is right. But when it's wrong, you catch it 3 months earlier than everyone else.

---

**The Pricing Strategy Checklist**  
  
Know your value metric       what scales with value received  
Measure willingness to pay    Van Westendorp or Gabor-Granger, not guessing  
Pick the right model         flat, seat, usage, tiered, hybrid, or freemium  
Design tiers for upgrade     middle tier = best value, clear path up  
Audit quarterly            revenue distribution, churn by tier, expansion gaps  
Test before you ship        cohort-based experiments, 90-day measurement window  
Raise prices annually       grandfather existing, test on new, communicate value  
Never discount without a trade   every concession earns something back  
  
Pricing is not a launch decision. It is a continuous process. Revisit it every quarter.
