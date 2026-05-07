---
layout: post
title: "TAM/SAM/SOM Calculator — Playbook"
categories: [playbooks]
---

TAM/SAM/SOM Calculator
market sizing guide · worksheets · worked examples

Market Sizing
TAM Analysis
Strategy
Pitch Decks
MBA Intern Playbook

"We're in a $50 billion market" is the most common lie in pitch decks. It tells investors nothing except that you Googled an analyst report and picked the biggest number you could find. That's not market sizing — that's theatre.

Real market sizing is bottom-up, specific, and defensible. It answers a simple question: **how many companies would actually buy this product, and how much would they pay?** This playbook teaches you to do that math honestly, present it credibly, and avoid the mistakes that make smart investors stop reading your deck.

**Who this is for:** MBA interns doing market sizing for strategy projects, founders building investor decks, and anyone who needs to answer "how big is this market?" without embarrassing themselves.

---

 PART I: DEFINITIONS 

Part I
Definitions
Before you calculate anything, you need to understand what these three acronyms actually mean, why they exist, and why getting them wrong destroys your credibility with anyone who's seen more than five pitch decks.

# 01 TAM vs SAM vs SOM

Three concentric circles. Each one smaller than the last. Each one more important than the last.

| Term | Definition | Question It Answers | Who Cares |
| --- | --- | --- | --- |
| **TAM**   Total Addressable Market | The total revenue opportunity if you had 100% market share. Every possible customer, every possible dollar. No constraints. | "How big is the universe of demand for this type of product?" | Sets the ceiling. Shows you're not building in a niche too small to matter. |
| **SAM**   Serviceable Addressable Market | The portion of TAM you can actually reach with your go-to-market. Filtered by geography, company size, industry vertical, tech stack, language, and channel. | "Of the total market, which companies can we actually sell to with our current GTM?" | Shows you've thought about constraints. More credible than TAM alone. |
| **SOM**   Serviceable Obtainable Market | The realistic share of SAM you can capture in the near term (12–24 months). Accounts for competition, sales capacity, brand awareness, and adoption curves. | "How much revenue can we actually generate in the next 1–2 years?" | This is what investors care about most. It's your revenue plan with a market-sizing wrapper. |

Investors have seen 10,000 pitch decks. They know your TAM is inflated. They're looking at your SOM to see if you're delusional or grounded. A founder who says "our SOM is $15M in year one and here's exactly how we get there" is 10x more credible than one who says "we're in a $50B market."

## The Concentric Circles

Think of it as a funnel:

- TAM: Every company on earth that could theoretically use a product like yours = $10B
- SAM: Companies in your target geography + size + vertical that you can reach = $800M
- SOM: What you'll realistically close in the next 12–24 months = $12M

**The ratio matters:** If your SOM is less than 1% of your SAM, investors wonder why it's so hard to penetrate. If your SOM is more than 10% of your SAM in year one, they think you're being unrealistic. The sweet spot for a Series A B2B SaaS: 1–5% of SAM as your year-one target.

---

# 02 Why Most TAM Analyses Are Fiction

The standard approach to market sizing goes like this: Google "[your industry] market size," find a Gartner or Grand View Research report that says "$47.2 billion by 2028," put it on slide 4 of your pitch deck, and move on. This is lazy, and everyone knows it.

## The Top-Down Trap

Here's why analyst-report TAMs are almost always meaningless for startups:

| Problem | Why It Happens | Example |
| --- | --- | --- |
| **Includes revenue you'll never capture** | Analyst reports count the entire category, including legacy on-premise vendors, services revenue, and hardware. | The "CRM market" is $80B. But $60B of that is Salesforce, Oracle, and SAP. Your startup isn't competing for that revenue. |
| **Wrong geography** | Reports are typically global. Your Series A startup sells in the US and maybe UK. | "Global HR tech: $35B." But you only sell in North America. Your relevant market is maybe $12B. |
| **Wrong customer segment** | Reports include enterprise, mid-market, and SMB. You might only serve one. | "DevOps tools: $15B." But you sell to companies with 50–500 engineers. The enterprise segment (where most of the spend is) isn't your market. |
| **Category is too broad** | Analysts define categories broadly to sell bigger reports. | "Cloud security: $45B" includes firewalls, identity, compliance, SIEM, and 20 other sub-categories. Your product does one of those. |
| **Double-counting** | If you sell to both "data analytics" and "business intelligence," those overlap in every analyst report. | Adding "data analytics market ($25B)" + "BI market ($30B)" = $55B. Except half the companies appear in both. |

A credible TAM is one you built yourself, from the bottom up, by counting actual companies. An incredible (literally: not credible) TAM is one you copied from a Gartner report. Investors can tell the difference in five seconds.

LAZY TAM

 "The global observability market is projected to reach $62B by 2028 (Gartner). We're well-positioned to capture a significant share of this rapidly growing market."
 

CREDIBLE TAM

 "There are 14,200 companies running Kubernetes in production with 50+ engineers (source: CNCF survey + LinkedIn). At our average ACV of $48K, that's a $682M SAM. We're targeting the 3,800 companies in North America first ($182M)."
 

---

 PART II: METHODS 

Part II
Methods
Three ways to calculate market size. Each has its place. The bottom-up method is the one that matters most. The other two are supporting evidence.

# 03 Top-Down Method

Start with the total market (from analyst reports), then apply filters to narrow it down to your addressable segment. This is the weakest method, but it's useful as a sanity check and for pitch decks where the audience expects a big number on slide 4.

## When to Use

- Sanity check. "Does our bottom-up number fall within a plausible range of the top-down estimate?"
- Pitch deck context. Investors expect to see a TAM slide. Give them the Gartner number, but immediately follow it with your bottom-up SAM.
- Early-stage exploration. When you're still validating ICP and don't have enough data for bottom-up yet.

## The Formula

**Total Market (analyst report)**  

 × Geography filter (e.g., 40% is North America)  

 × Segment filter (e.g., 30% is mid-market)  

 × Use-case filter (e.g., 25% is relevant to your specific product)  

 = **Filtered TAM**

## Worked Example: API Security Platform

Global application security market (Gartner 2025)

$18.5B

North America share
×
42%

API security sub-segment
×
18%

Companies with 100+ engineers (our ICP)
×
55%

**Filtered TAM**
=
**$770M**

**Limitations:** Every percentage you apply is a guess. "42% North America" might be 38% or 46%. "18% API security" might be 12% or 25%. Compound four guesses together and your error bars are enormous. This is why top-down alone isn't enough.

## Where to Find Analyst Reports

| Source | Cost | Quality | Best For |
| --- | --- | --- | --- |
| **Gartner** | $$$$ (enterprise subscriptions) | High | Enterprise software categories |
| **IDC** | $$$$ (enterprise subscriptions) | High | Infrastructure and cloud markets |
| **Forrester** | $$$ (enterprise subscriptions) | High | Marketing and CX technologies |
| **Grand View Research** | $$ (individual reports $3–5K) | Medium | Broad industry overviews |
| **Statista** | $$ ($200/mo) | Medium | Quick data points, charts |
| **CB Insights** | $$ (varies) | Medium | Startup-specific market maps |
| **Investor pitch decks (public)** | Free | Varies | Seeing how similar companies sized their markets |
| **SEC filings (S-1s)** | Free | High | How public companies described their TAM pre-IPO |

Pro tip: search "[company] S-1 TAM" for any recently-IPO'd company in your space. Their S-1 filing will have a market sizing section vetted by lawyers and bankers. It's the most credible public source.

---

# 04 Bottom-Up Method

This is the credible way. Instead of starting with a big number and filtering down, you start with actual customers and build up. The formula is dead simple:

Bottom-Up TAM = Number of potential customers × Average revenue per customer. That's it. Everything else is about getting those two numbers right.

## Step 1: Define Your ICP

Your Ideal Customer Profile is the company that gets the most value from your product, has the fastest sales cycle, the highest win rate, and the lowest churn. Be specific:

| ICP Dimension | Vague (bad) | Specific (good) |
| --- | --- | --- |
| **Company size** | "Mid-market and enterprise" | "200–2,000 employees" |
| **Industry** | "Technology companies" | "B2B SaaS with a product-led growth motion" |
| **Geography** | "Global" | "US and UK, English-speaking markets" |
| **Tech stack** | "Cloud-native" | "Running Kubernetes on AWS or GCP" |
| **Buying signal** | "Growing companies" | "Raised Series B-D in the last 18 months" |
| **Decision maker** | "Technical leadership" | "VP Engineering or CTO, reports to CEO" |

## Step 2: Count the Companies

This is where most people get lazy and guess. Don't guess. Count.

| Data Source | What You Can Find | Cost | Accuracy |
| --- | --- | --- | --- |
| **LinkedIn Sales Navigator** | Companies by size, industry, geography, growth rate, tech keywords in job postings | $100/mo | High |
| **ZoomInfo** | Company count by revenue, employees, industry, tech stack | $$$ | High |
| **Apollo.io** | Similar to ZoomInfo, more affordable. Good company filters. | Free–$100/mo | Medium-High |
| **Crunchbase** | Companies by funding stage, total raised, industry, location | $50/mo | High for VC-backed |
| **BuiltWith** | Companies using specific technologies (Kubernetes, Snowflake, etc.) | $$ | Medium |
| **Census / Government Data** | Total business count by NAICS code, size, geography | Free | High (but lagging) |
| **Industry associations** | Member directories, industry surveys | Free–$$ | Medium |

## Step 3: Determine Realistic ACV

Don't use your aspirational pricing. Use what customers are actually paying (or what comparable products charge).

- If you have customers: Use your actual average ACV from the last 12 months.
- If pre-revenue: Look at comparable products. Check G2 and pricing pages. Talk to 10 potential customers about willingness to pay.
- Segment your ACV: Different company sizes pay different amounts. A 200-person company pays $24K/yr. A 2,000-person company pays $120K/yr. Weight your calculation accordingly.

## Step 4: Multiply

Companies matching ICP (from Sales Nav / ZoomInfo)

8,400

Weighted average ACV
×
$52,000

**Bottom-Up SAM**
=
**$437M**

**Why this is credible:** Every number is traceable. An investor can say "where did 8,400 come from?" and you can answer "LinkedIn Sales Nav filter: B2B SaaS, 200–2,000 employees, US+UK, Series B–D funding. Here's the screenshot." That's a conversation. "$50B market (Gartner)" is a dead end.

---

# 05 Value-Theory Method

The value-theory method asks a different question: **what is the total economic value your product creates, and what percentage of that value can you capture as revenue?**

This method is especially useful when you're creating a new category (no analyst reports exist) or when the value you deliver is dramatically larger than what you charge.

## The Formula

**Economic value per customer** (cost savings + revenue gains + time saved)  

 × **Number of potential customers**  

 = **Total value pool**  
  

**Total value pool** × **Capture rate** (typically 5–15% of value created)  

 = **Value-Theory TAM**

## Worked Example: Compliance Automation Platform

**Value per customer:**

  Replaces 2 FTE compliance analysts ($85K each)

$170,000

  Reduces audit prep time by 300 hours ($150/hr loaded)
+
$45,000

  Avoids 1 compliance failure per 3 years (avg fine: $500K)
+
$167,000

**Total economic value per customer**
=
**$382,000/yr**

Companies needing SOC 2 / ISO 27001 with 100–2,000 employees

22,000

Total value pool (22,000 × $382K)
=
$8.4B

Capture rate (10% of value = $38K ACV)
×
10%

**Value-Theory TAM**
=
**$840M**

**Why 10% capture rate?** The rule of thumb: enterprise software can capture 10–20% of the value it creates. If you save a company $382K/yr, charging $38K (10%) is easy to justify in an ROI calculation. Charging $76K (20%) is possible with strong proof. Charging more than 20% of value makes the ROI shaky and slows deals.
**When to lead with value-theory:** If you're creating a new category (no Gartner Magic Quadrant for your product yet), value-theory is the strongest method. It tells investors: "this market doesn't exist yet in analyst reports, but the economic pain is real and quantifiable."

---

 PART III: THE CALCULATOR 

Part III
The Calculator
Blank worksheets you can fill in for your own company, plus three fully worked examples so you can see the math in action.

# 06 Step-by-Step TAM Worksheet

Print this out. Fill it in with real data. Every number should have a source you can cite.

## SAM Calculation

| # | Step | Your Number | Source |
| --- | --- | --- | --- |
| **A** | Total companies in target industry | ___________ | ___________ |
| **B** | Filter: company size (employees or revenue range) | ___________ | ___________ |
| **C** | Filter: geography (where you can sell) | ___________ | ___________ |
| **D** | Filter: tech stack or behavioral signals | ___________ | ___________ |
| **E** | **= Target accounts (A × B × C × D)** | ___________ |  |
| **F** | Average ACV (weighted by segment) | ___________ | ___________ |
| **G** | **= SAM in dollars (E × F)** | ___________ |  |

## SOM Calculation

| # | Step | Your Number | Notes |
| --- | --- | --- | --- |
| **G** | SAM (from above) | ___________ |  |
| **H** | Realistic penetration rate (Year 1) | ___________ | 1–3% for new entrant. 3–5% if strong brand or channel. |
| **I** | **= SOM (G × H)** | ___________ | This should match your revenue plan. |

## Sanity Checks

| Check | Pass Condition | If Fails |
| --- | --- | --- |
| SOM < 5% of SAM? | Yes | You might be overestimating penetration rate. Very few startups capture >5% in year one. |
| SAM < 30% of TAM? | Yes | Your filters might not be tight enough. Are you really excluding segments you can't serve? |
| SOM aligns with your hiring plan? | Yes | If SOM = $5M but you have 2 AEs, the math doesn't work. 2 AEs × $1.2M quota = $2.4M max. |
| ACV is defensible? | Yes | Is this what customers actually pay, or what you wish they'd pay? |
| Bottom-up within 2x of top-down? | Yes | If they're wildly different, one of your assumptions is wrong. Investigate. |

---

# 07 Three Worked Examples

## Example 1: Developer Tools Company

Product: CI/CD optimization platform for engineering teams. Sells to companies running large monorepos.

Software companies with 50+ engineers (LinkedIn Sales Nav)

28,000

Filter: using GitHub Actions or GitLab CI (BuiltWith)
×
62%

Filter: North America + Europe
×
71%

Filter: monorepo architecture (GitHub public signal + surveys)
×
35%

**Target accounts (SAM)**
=
**4,310**

Weighted ACV: ($36K for 50–200 eng, $84K for 200+ eng)
×
$48,000

**SAM**
=
**$207M**

Year 1 penetration (2% — new category, limited sales team)
×
2%

**SOM (Year 1)**
=
**$4.1M**

**Sanity check:** $4.1M SOM = ~86 customers in year one. With 4 AEs closing ~2 deals/month each, that's 96 deals/year. Math checks out. Credible.

## Example 2: HR SaaS Platform

Product: Employee engagement and pulse survey platform. Sells to HR leaders at mid-market companies.

Companies with 200–5,000 employees in US (Census Bureau + LinkedIn)

62,000

Filter: knowledge workers (excludes manufacturing, logistics, etc.)
×
45%

Filter: have an HR team of 3+ people (proxy for maturity)
×
80%

Filter: not already locked into Workday/SAP SuccessFactors suite
×
60%

**Target accounts (SAM)**
=
**13,400**

ACV: $8/employee/month × avg 800 employees × 12 months
×
$76,800

**SAM**
=
**$1.03B**

Year 1 penetration (1.5% — crowded market, competing with Culture Amp, Lattice)
×
1.5%

**SOM (Year 1)**
=
**$15.4M**

**Sanity check:** $15.4M SOM = ~200 customers at $77K ACV. That requires a sales team of 8–10 AEs at ~$1.5M quota each. Doable for a Series B company. Tight for a Series A.

## Example 3: Fintech Platform (Payments Infrastructure)

Product: Embedded payments API for B2B SaaS platforms. Revenue model is take-rate on payment volume.

B2B SaaS platforms processing payments (Crunchbase + BuiltWith)

4,200

Filter: processing $1M–$500M in annual payment volume
×
65%

Filter: US-based (regulatory scope)
×
58%

Filter: not already on Stripe Connect or Adyen for Platforms
×
40%

**Target accounts (SAM)**
=
**633**

Avg payment volume per platform: $28M/yr × 0.45% take rate
×
$126,000

**SAM**
=
**$79.8M**

Year 1 penetration (3% — high-touch sales, long implementation)
×
3%

**SOM (Year 1)**
=
**$2.4M**

**Sanity check:** $2.4M SOM = 19 platform customers. With 6–9 month sales cycles for payments infrastructure, 2 senior AEs can close 2–3 deals/quarter each. 19 in year one is achievable. The expansion story is strong: as each platform's payment volume grows, revenue grows without new sales effort.
**Notice the pattern:** In all three examples, the SOM is a small, specific, defensible number. Nobody is claiming to capture 20% of a $50B market. These are real numbers that map to real sales plans with real headcount. That's what credibility looks like.

---

 PART IV: PRESENTATION 

Part IV
Presentation
You've done the math. Now you need to present it in a way that makes investors, board members, and executives nod instead of squint.

# 08 How to Present Market Size

## The Wedge-and-Expand Narrative

The most effective market-size story isn't "here's a big number." It's "here's where we start, and here's how we get bigger." Investors call this the **wedge strategy**:

1. The wedge (SOM): "We're starting with 4,300 companies using monorepos with 50+ engineers. That's a $207M SAM, and we'll capture $4M in year one."
2. The expand (SAM growth): "As we add polyrepo support and self-hosted CI, our SAM expands to 18,000 companies and $620M."
3. The vision (TAM): "The broader developer productivity market is $4.2B and growing 25% YoY. We're building toward the full platform."

**The key insight:** Start narrow, prove you can win, then expand. Amazon started with books. Uber started with black cars in SF. Slack started as an internal tool at a gaming company. Every massive company started with a wedge that looked "too small."

## Pitch Deck Structure (Market Size Slide)

| Element | What to Include | What to Avoid |
| --- | --- | --- |
| **Visual** | Three concentric circles with dollar amounts. SOM highlighted. | Just a big number with no breakdown. Pie charts. |
| **TAM number** | Top-down from credible source. Cite the source. | Unattributed numbers. "Based on internal estimates." |
| **SAM number** | Bottom-up calculation. Show the filters. "14,200 companies × $48K ACV." | Vague filters. "We estimate 20% of the market is addressable." |
| **SOM number** | Tied to your revenue plan. "2% penetration = $4.1M = 86 customers." | Aspirational numbers untied to sales capacity. |
| **Growth path** | How SAM expands over 3–5 years as you add products/segments/geos. | Static market size with no expansion story. |

## For Board Meetings

Board members want to see:

- Market share progress: "We're at 1.2% of SAM, up from 0.6% a year ago." This shows momentum.
- SAM expansion: "We launched the mid-market tier, which adds 8,000 companies and $340M to our SAM."
- Competitive landscape: "Of the $207M SAM, we estimate competitors hold $45M (22%). $162M is greenfield."
- Win rate by segment: "We win 35% of deals in our core ICP but only 12% outside it — confirming our SAM definition is right."

## For Strategic Plans

Internal strategy docs should be more granular:

- Break SAM by segment (enterprise / mid-market / SMB)
- Break SAM by vertical (fintech / healthtech / e-commerce)
- Map each segment to a specific GTM motion (outbound / PLG / channel)
- Show SAM evolution over 3 years as product roadmap unlocks new segments

---

# 09 Common TAM Mistakes

These are the errors that make investors cringe, board members skeptical, and strategy documents useless. Every one of these is real — we've seen them in hundreds of decks and memos.

| Mistake | Why It's Wrong | How to Fix It |
| --- | --- | --- |
| **Using total industry revenue as TAM** | "The healthcare IT market is $250B." This includes hospital EHR systems, medical devices, consulting services, and hardware. Your SaaS product competes for approximately 0.3% of that. | Define your specific sub-category. If you sell appointment scheduling software, your TAM is appointment scheduling, not "healthcare IT." |
| **Double-counting across categories** | Adding "CRM ($65B)" + "sales engagement ($5B)" + "revenue intelligence ($3B)" when your product sits in one category and these markets overlap significantly. | Pick the single category that best describes your product. Reference adjacent categories as expansion opportunities, not base TAM. |
| **Ignoring competition's share** | Presenting a $500M SAM without acknowledging that Salesforce owns 40% of it, and they're not giving it back. | Show addressable SAM = total SAM minus entrenched incumbent share. Be honest about which accounts are contestable vs locked in. |
| **Confusing TAM with demand** | TAM measures the theoretical maximum. It doesn't mean $500M of companies are actively looking to buy. Many are satisfied with their current solution or don't feel the pain yet. | Distinguish between TAM (theoretical) and active demand (companies with budget allocated, actively evaluating). SOM should reflect actual demand, not theoretical potential. |
| **Static market sizing** | Calculating TAM once and never updating it. Markets shift, new segments emerge, pricing changes. | Recalculate quarterly. Every time you add a product, expand a geography, or change pricing, your SAM changes. |
| **Using aspirational ACV** | "Our target ACV is $120K." But your actual average is $45K because most customers buy the base tier. TAM calculated with $120K is 2.7x overstated. | Use actual ACV from closed deals. If pre-revenue, use the lower end of comparable pricing. |
| **"We only need 1% of the market"** | This sounds modest but is actually the laziest argument. It implies you haven't thought about how you'll get that 1%. It also often translates to $500M, which is not modest at all. | Never say this. Instead, show exactly which accounts you'll win, with which sales team, at what ACV, at what win rate. That's a plan, not a wish. |
| **Mixing up serviceable and obtainable** | Labeling your SAM as SOM. If your SAM is $400M and you call it SOM, investors think you plan to generate $400M in revenue next year. | SAM = could theoretically reach. SOM = will realistically close. SOM is 1–5% of SAM for most startups in year one. |

The best market-sizing presentations acknowledge uncertainty. "Our bottom-up SAM is $207M, with a range of $160M–$260M depending on how we define the tech stack filter. Even at the low end, there's more than enough market for a $50M ARR business." That's honest. That's credible. That's what gets funded.

---

**The Market Sizing Checklist**  
  

Bottom-up, not top-down       count actual companies, not Gartner numbers  

Every number has a source     "LinkedIn Sales Nav" not "internal estimates"  

ACV is actual, not aspirational   what customers pay, not what you wish  

SOM ties to sales plan        X reps × Y quota = Z revenue  

Penetration rate is 1–5%      anything higher in year one is delusion  

Show the wedge narrative      start narrow, expand over time  

Acknowledge competition       don't pretend incumbents don't exist  

Sanity-check the math        does bottom-up match top-down within 2x?  

  

A credible small number beats an incredible large one. Every time.
