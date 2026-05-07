---
layout: post
title: "Growth Experiment Tracker"
categories: [playbooks]
---

Growth Experiment Tracker

frameworks · templates · 20 starter experiments

Growth
Experimentation
AARRR Metrics
ICE Framework
MBA Intern Playbook

Growth isn't magic. It isn't "going viral." It isn't hiring a growth hacker who sprinkles fairy dust on your funnel. Growth is a systematic process: form a hypothesis, design an experiment, run it, measure the result, learn something, and repeat. The teams that grow fastest are the ones that run the most experiments — because each experiment, win or lose, compounds into knowledge about your customers that competitors don't have.

This playbook gives you the system: how to prioritize experiments, how to design them properly, a tracker to log everything, and 20 starter ideas organized by funnel stage so you can begin running experiments this week.

**Who this is for:** MBA interns running growth experiments, product managers building experiment culture, founders who want a structured approach to growth, and anyone tired of guessing what will move the needle.

---


Part I

The Experiment Mindset

Before you run a single experiment, you need to understand why experimentation matters and how to decide which experiments to run first. Most teams have more ideas than capacity — the framework for prioritization matters more than the ideas themselves.

# 01 Why Experiments

Every successful growth team operates on a simple belief: **opinions are cheap, data is expensive, and only experiments produce data.**

The math is compelling:

| Experiment Velocity | Win Rate | Avg Lift per Win | Compounded Annual Impact |
| --- | --- | --- | --- |
| 2 experiments/week | ~20% | +5% on target metric | ~70% annual improvement |
| 5 experiments/week | ~20% | +5% on target metric | ~170% annual improvement |
| 10 experiments/week | ~20% | +5% on target metric | ~340% annual improvement |

Most experiments fail. That's the point. A 20% win rate is excellent. If you're winning more than 30% of your experiments, you're not being ambitious enough — you're testing things you already know will work.

The compound effect is what matters. Each winning experiment makes every future visitor, user, or customer slightly more valuable. Over a year, a team running 5 experiments per week with a 20% win rate and 5% average lift per win will more than **double** their core metric. That's not theory — that's math.

## The Alternative: Guessing

Without experiments, growth decisions look like this:

- The CEO says "our homepage needs a redesign" because they're tired of looking at it.
- The PM says "let's add a free tier" because a competitor did.
- The marketing lead says "let's try TikTok" because they read a blog post.

These might all be good ideas. They might all be terrible. **Without experiments, you'll never know which.** And you'll spend 3 months on a homepage redesign that turns out to decrease conversion by 8%, but nobody will know because nobody measured it.

**The cost of not experimenting:** A homepage redesign takes 3 months and costs $50K in design + engineering time. An experiment to test the new headline takes 3 days and costs nothing. If the headline test shows a 15% lift, you know the redesign direction is right. If it shows no lift, you just saved $50K and 3 months.

---

# 02 The ICE Framework

You'll always have more experiment ideas than capacity to run them. The ICE framework helps you prioritize ruthlessly.

| Dimension | What It Measures | Scale | How to Score |
| --- | --- | --- | --- |
| **Impact** | How much will this move the target metric if it works? | 1–10 | **10:** Could double conversion. **5:** 10–20% improvement. **1:** Marginal, <5% improvement. |
| **Confidence** | How confident are you that it will work? | 1–10 | **10:** Strong data/evidence. **5:** Qualitative evidence (user feedback). **1:** Pure gut feeling. |
| **Ease** | How easy is it to implement and run? | 1–10 | **10:** Copy change, 1 hour. **5:** Small feature, 1 week. **1:** Full rebuild, 1+ month. |

**ICE Score = Impact × Confidence × Ease**  
  
Higher score = do it first. Simple as that.

## Worked Examples

| Experiment | I | C | E | ICE | Priority |
| --- | --- | --- | --- | --- | --- |
| Change homepage headline from feature-focused to outcome-focused | 7 | 6 | 9 | **378** | Do this week |
| Add social proof (customer logos) above the fold | 6 | 7 | 8 | **336** | Do this week |
| Reduce onboarding from 7 steps to 3 steps | 8 | 5 | 4 | **160** | Queue for next sprint |
| Build a referral program with double-sided incentives | 8 | 4 | 3 | **96** | Backlog |
| Complete redesign of pricing page | 9 | 3 | 2 | **54** | Deprioritize — test components first |

**The scoring trap:** Everyone inflates Impact and deflates Ease. Be honest. If you've never tested headlines before, your Confidence should be 4, not 8. If the change requires backend work, Ease is a 4, not a 7. Dishonest scoring defeats the purpose of the framework.

**Common mistake:** Scoring by committee. ICE works best when one person scores and the group challenges. Group scoring regresses to the mean — everything becomes a 5, and you've learned nothing about priorities.

---


Part II

The Experiment Framework

A good experiment has a clear hypothesis, a defined category, and a proper design. Most failed experiments fail because they were poorly designed, not because the idea was bad.

# 03 Hypothesis Format

Every experiment starts with a hypothesis. Not "let's try changing the button color" — that's a task, not a hypothesis. A hypothesis is a falsifiable prediction about cause and effect.

## The Template

We believe that [change] will cause [effect] for [segment], which we'll measure by [metric] over [timeframe]. We'll consider this successful if [threshold].

## Good vs Bad Hypotheses

BAD

"Let's test a new onboarding flow."

No prediction. No metric. No success criteria. You'll learn nothing.

GOOD

"We believe that **replacing the 7-step onboarding wizard with a 3-step quick-start** will cause **higher activation rates** for **new free trial users**, measured by **% of users who complete core action within 24 hours** over **3 weeks**. Success = **activation rate increases from 34% to 42%+**."

Specific change. Named segment. Defined metric. Clear timeframe. Quantified threshold.

## More Examples

| Category | Hypothesis |
| --- | --- |
| Acquisition | "We believe that **switching our homepage headline from 'The Modern Data Stack' to 'Cut Your Data Pipeline Build Time by 80%'** will increase **demo request rate from 2.1% to 2.8%+** among **direct traffic visitors** over **2 weeks**." |
| Activation | "We believe that **sending a personalized 'getting started' email 1 hour after signup (vs. generic welcome)** will increase **Day-1 retention from 45% to 55%+** for **self-serve signups** over **3 weeks**." |
| Revenue | "We believe that **defaulting the pricing toggle to annual billing (vs. monthly)** will increase **annual plan selection from 28% to 40%+** among **pricing page visitors** over **4 weeks**." |
| Retention | "We believe that **sending a 'you're falling behind' email when usage drops below 2 logins/week** will reduce **30-day churn from 6.2% to 5.0%** for **accounts in months 2–6** over **6 weeks**." |
| Referral | "We believe that **adding a 'Give $50, Get $50' referral prompt after the first successful project** will generate **0.15+ referrals per activated user** for **users who complete onboarding** over **4 weeks**." |

---

# 04 Experiment Categories — The AARRR Framework

Dave McClure's pirate metrics framework gives you five categories to organize experiments. Every experiment should map to exactly one stage.

| Stage | Question | Key Metrics | Example Experiments |
| --- | --- | --- | --- |
| **Acquisition** | How do users find us? | Traffic, signup rate, CAC, channel efficiency | Landing page tests, ad creative, SEO content, referral sources |
| **Activation** | Do they have a great first experience? | Onboarding completion, time-to-value, "aha moment" rate | Onboarding flow, welcome emails, first-use guidance, feature discovery |
| **Revenue** | Do they pay us? | Conversion rate, ARPU, ACV, expansion revenue | Pricing, upsell triggers, paywall placement, billing defaults |
| **Retention** | Do they come back? | DAU/MAU, churn rate, NPS, feature adoption | Re-engagement emails, health scores, QBR cadence, in-app prompts |
| **Referral** | Do they tell others? | Referral rate, viral coefficient, NPS, invite acceptance rate | Referral incentives, sharing mechanics, testimonial collection |

**Where to start:** Most teams over-invest in Acquisition and under-invest in Activation and Retention. A 10% improvement in Activation has the same revenue impact as a 10% increase in traffic — but it's usually 5x cheaper to achieve. **Fix your leaky bucket before pouring more water in.**

## The Funnel Math

Here's why Activation and Retention experiments often have the highest ROI:

**Scenario A: Improve Acquisition by 20%**  
10,000 visitors → **12,000 visitors** → 1,200 signups → 408 activated → 204 paying → $204K MRR  
  
**Scenario B: Improve Activation by 20% (same traffic)**  
10,000 visitors → 10,000 visitors → 1,000 signups → **408 activated** → 204 paying → $204K MRR  
  
**Same result. But Scenario B cost $0 in ad spend.**

---

# 05 Experiment Design

A poorly designed experiment is worse than no experiment. It gives you false confidence in a wrong conclusion. Here's how to design experiments that produce real learnings.

## Control vs Variant

| Term | Definition | Rule |
| --- | --- | --- |
| **Control** | The current experience. Nothing changes. | Always have a control. "Before/after" comparisons without a control are unreliable (seasonality, external factors). |
| **Variant** | The changed experience you're testing. | Change one thing at a time. If you change the headline AND the CTA AND the image, you won't know which change caused the result. |
| **Split** | Traffic is randomly divided between control and variant. | 50/50 is standard. For high-risk changes, start with 90/10 and increase if no negative impact. |

## Sample Size — When Is n Big Enough?

You don't need to be a statistician. But you do need to know the basics:

| Baseline Conversion | Minimum Detectable Effect | Required Sample Size (per variant) | At 1,000 visitors/day, how long? |
| --- | --- | --- | --- |
| 2% | +0.5% (2% → 2.5%) | ~6,000 | 12 days |
| 5% | +1% (5% → 6%) | ~4,700 | 10 days |
| 10% | +2% (10% → 12%) | ~3,600 | 7 days |
| 30% | +5% (30% → 35%) | ~1,500 | 3 days |

Based on 95% confidence level and 80% statistical power. Use an online calculator (Evan Miller's is the best free one) for your specific numbers.

## Duration Rules

- **Minimum 2 weeks for B2B.** B2B traffic has weekly cycles (Mon–Fri vs weekends). Running for less than 2 weeks means you're comparing weekdays to weekends.
- **Minimum 1 full business cycle.** If your customers have a monthly billing cycle, run for at least one full cycle.
- **Don't peek.** Checking results daily and stopping when it "looks good" is the fastest way to get a false positive. Set the duration upfront and don't stop early.
- **Never stop on a Friday.** Weekend traffic behaves differently. End experiments on the same day of the week you started.

**The "peeking" problem:** If you check your experiment every day and plan to stop when it reaches significance, there's a 26% chance of a false positive (instead of 5%). This is called the "multiple comparisons" problem. Decide your sample size upfront, run until you hit it, then analyze. One look. One decision.

## What to Measure

| Type | Definition | Example |
| --- | --- | --- |
| **Primary metric** | The one metric that determines success or failure. | Signup rate, activation rate, conversion rate. |
| **Secondary metrics** | 2–3 metrics that provide context. | Time on page, bounce rate, feature adoption. |
| **Guardrail metrics** | Metrics that should NOT get worse. | Page load time, support ticket volume, churn rate. |

**Guardrail metrics matter:** You could increase signup rate by 50% by removing all form fields — but activation would plummet because you're now getting unqualified signups. Guardrail metrics prevent you from optimizing one metric at the expense of another.

---


Part III

The Tracker

A growth program without a tracker is just a collection of random acts. The tracker is the institutional memory of your growth team — it prevents you from re-running failed experiments, helps you build on past wins, and creates a playbook that survives team turnover.

# 06 Experiment Log Template

Copy this table into a spreadsheet. Every experiment gets a row. No exceptions. Even failed experiments. **Especially** failed experiments.

| Column | Description | Example |
| --- | --- | --- |
| **ID** | Sequential number. Never reuse. | `GE-042` |
| **Hypothesis** | Full hypothesis statement (use the template from section 3). | "We believe that switching to outcome-focused headline..." |
| **Category** | AARRR stage. | Acquisition |
| **ICE Score** | Impact × Confidence × Ease | 7 × 6 × 9 = **378** |
| **Status** | Queued / Running / Complete / Killed | Complete |
| **Start Date** | When the experiment went live. | 2026-04-14 |
| **End Date** | When you stopped and analyzed. | 2026-04-28 |
| **Primary Metric** | The metric you're optimizing. | Demo request rate |
| **Baseline** | Control group's metric value. | 2.1% |
| **Result** | Variant's metric value. | 2.9% |
| **Lift** | % change from baseline. | +38% |
| **Stat Sig?** | Did it reach 95% confidence? | Yes (p=0.02) |
| **Winner?** | Y / N / Inconclusive | Y |
| **Learning** | What did you learn? (1–2 sentences) | "Outcome-focused headlines outperform feature-focused for direct traffic. Effect stronger on mobile." |
| **Next Action** | What do you do with this result? | "Ship variant to 100%. Test sub-headlines next." |

## Example: A Completed Experiment Log Entry

**GE-042** · Acquisition · ICE: 378 · WINNER

**Hypothesis:** Switching homepage headline from "The Modern Data Platform" to "Build Data Pipelines 80% Faster" will increase demo requests from 2.1% to 2.8%+ among direct traffic over 2 weeks.  
  
**Duration:** Apr 14 – Apr 28 (14 days)  
**Sample:** 4,218 visitors per variant (8,436 total)  
**Baseline (control):** 2.1% demo request rate  
**Result (variant):** 2.9% demo request rate  
**Lift:** +38% (p=0.02, statistically significant)  
**Guardrails:** Bounce rate unchanged. Avg time on page +4 seconds. No negative impact on trial signups.  
  
**Learning:** Outcome-focused headlines significantly outperform feature-focused ones for direct traffic. The effect was stronger on mobile (44% lift) vs desktop (31% lift). Visitors who saw the outcome headline also explored 1.3 more pages on average.  
  
**Next action:** Ship variant to 100%. Run follow-up experiment testing different outcome claims ("80% faster" vs "save 20 hours/week" vs "ship in days, not months").

---

# 07 20 Starter Experiment Ideas

These are proven experiments that work across B2B SaaS companies. Adapt them to your product. Each one includes the hypothesis framing so you can drop it straight into your tracker.

## Acquisition (Top of Funnel)

1. Homepage Headline Test

Ease: 9 · Typical lift: 10–40% · Duration: 2 weeks

Test your current headline against an outcome-focused alternative. "The all-in-one platform for X" vs "Reduce X time by 60%." Almost always, specific outcomes beat vague feature descriptions.

2. Pricing Page Layout

Ease: 7 · Typical lift: 5–20% · Duration: 3 weeks

Test 3 tiers vs 2 tiers. Test highlighting the middle tier as "most popular." Test showing annual pricing by default vs monthly. The pricing page is usually the second-highest-leverage page after the homepage.

3. SEO Content Cluster

Ease: 5 · Typical lift: 50–200% organic traffic · Duration: 8–12 weeks

Publish 8–12 articles around one keyword cluster (e.g., "data pipeline" + long-tail variations). Interlink them. Measure organic traffic growth to the cluster after 8 weeks. This is a slower experiment but often has the highest long-term ROI.

4. LinkedIn Ad Creative Test

Ease: 8 · Typical lift: 15–50% CTR · Duration: 2 weeks

Test 4 ad creatives simultaneously: (A) customer quote, (B) data/stat, (C) pain-point question, (D) product screenshot. Almost always, customer quotes and pain-point questions outperform product screenshots.

5. Referral Landing Page

Ease: 6 · Typical lift: 20–40% referral conversion · Duration: 3 weeks

Create a dedicated landing page for referred visitors (different from homepage). Include the referrer's name, a tailored value prop, and a simplified signup flow. Referred visitors convert at 3–5x the rate of cold traffic when the landing page matches the referral context.

## Activation (Onboarding & Aha Moment)

6. Onboarding Flow Simplification

Ease: 5 · Typical lift: 15–30% completion · Duration: 3 weeks

Cut your onboarding from N steps to N/2 steps. Move non-essential setup to post-activation. The fastest path to the "aha moment" wins. Every additional step loses 10–20% of users.

7. Time-to-Value Reduction

Ease: 4 · Typical lift: 20–50% activation · Duration: 4 weeks

Pre-populate the product with sample data so users see value before doing any work. Figma does this with starter templates. Notion does this with pre-built pages. The first moment of "oh, this is useful" needs to happen in minutes, not days.

8. Checklist vs Guided Tour

Ease: 6 · Typical lift: 10–25% completion · Duration: 2 weeks

Test a static checklist ("Set up your first project, Invite a teammate, Create a dashboard") vs an interactive guided tour that walks them through each step. Some users prefer autonomy (checklist). Some prefer hand-holding (tour). Test which wins for your audience.

9. In-App Tooltip Sequence

Ease: 7 · Typical lift: 10–20% feature discovery · Duration: 2 weeks

After the user completes onboarding, show 3–5 contextual tooltips highlighting features they haven't discovered yet. Trigger them based on behavior, not time. "You created a project — did you know you can automate reports?" beats a random tooltip on day 3.

## Revenue (Pricing & Upsell)

10. Price Increase Test

Ease: 8 · Typical lift: 10–30% ARPU · Duration: 4 weeks

Show new visitors a price that's 20% higher than current pricing. If conversion drops by less than 20%, you've increased revenue. Most B2B SaaS is underpriced. A 20% price increase with a 5% conversion drop = 14% more revenue.

11. Annual Billing Default

Ease: 9 · Typical lift: 15–40% annual plan selection · Duration: 2 weeks

Default the pricing toggle to annual instead of monthly. Show the monthly price crossed out with the annual price highlighted. Annual billing improves cash flow, reduces churn (customers commit for a year), and increases LTV.

12. Upsell Trigger Email

Ease: 7 · Typical lift: 5–15% upsell rate · Duration: 4 weeks

Send an automated email when a user hits 80% of their plan limit (seats, API calls, storage). "You're at 80% of your limit. Upgrade now and get 20% off your first month of Pro." Timing is everything — send it when the pain is real.

13. Feature Gating Experiment

Ease: 5 · Typical lift: 10–25% upgrade rate · Duration: 4 weeks

Take a popular feature currently available on the free tier and gate it behind the paid plan. Measure: does upgrade rate increase more than free-tier churn increases? If yes, the feature was undervalued and should be gated permanently.

## Retention (Churn Reduction)

14. Health Score Alerts

Ease: 5 · Typical lift: 10–20% churn reduction · Duration: 6 weeks

Build a simple health score based on login frequency, feature usage, and support tickets. When a customer's score drops below threshold, auto-assign them to a CSM for proactive outreach. Most churn is predictable 30–60 days in advance.

15. Re-engagement Campaign

Ease: 7 · Typical lift: 5–15% reactivation · Duration: 3 weeks

For users who haven't logged in for 14+ days, send a 3-email sequence: (1) "Here's what you missed" with new feature highlights, (2) "Your teammates are active" with social proof, (3) "Can we help?" with an offer for a 1:1 walkthrough.

16. QBR Cadence Change

Ease: 6 · Typical lift: 10–20% renewal rate · Duration: 8 weeks

Switch from quarterly business reviews to monthly 15-minute check-ins. Shorter, more frequent touchpoints catch problems earlier and keep the relationship warm. Test on half your accounts and measure renewal rate vs control.

17. NPS Follow-Up Automation

Ease: 7 · Typical lift: variable · Duration: 4 weeks

When someone gives an NPS score of 0–6 (detractor), auto-trigger a personal email from the CEO within 1 hour asking what's wrong. When someone gives 9–10 (promoter), auto-ask for a G2 review or referral. Most companies collect NPS and do nothing with it.

## Referral (Viral Loops)

18. Invite Incentive Test

Ease: 6 · Typical lift: 30–80% referral rate · Duration: 4 weeks

Test three referral incentives: (A) $25 credit for both parties, (B) 1 month free for both, (C) exclusive feature unlock. Double-sided incentives (both giver and receiver benefit) consistently outperform one-sided. Test the format, not just the amount.

19. Sharing Mechanics

Ease: 7 · Typical lift: 15–40% share rate · Duration: 3 weeks

Add share prompts at moments of success: after completing a project, after hitting a milestone, after generating a report. The prompt should pre-fill a message like "I just used [product] to [outcome] — worth checking out." Make sharing effortless.

20. Partner Referral Program

Ease: 4 · Typical lift: new channel entirely · Duration: 8 weeks

Recruit 10 partners (consultants, agencies, complementary tools) and give them a custom referral link with a 15–20% revenue share for the first year. Track which partners send qualified leads vs noise. Double down on the top 3.

**How to use this list:** Score each experiment using ICE for your specific situation. A price increase test might be high-impact for an underpriced product but irrelevant for one with price-sensitive customers. Context matters more than the idea itself.

---


Part IV

Running the Program

Ideas and frameworks are worthless without execution. This part covers the weekly cadence, how to build a culture of experimentation, and the hardest decision in growth: when to scale a winner vs kill a loser.

# 08 The Weekly Growth Meeting

30 minutes. Every week. Same time. Non-negotiable. This meeting is the heartbeat of your growth program.

## The Agenda (30 Minutes)

| Time | Block | What Happens | Output |
| --- | --- | --- | --- |
| **0–10 min** | **Review Results** | Go through every experiment that completed in the last week. Read the result, the learning, and the recommended next action. No debate on methodology — that happens offline. | Updated experiment log. Ship/kill decisions made. |
| **10–20 min** | **This Week's Launches** | Review the top 3–5 experiments by ICE score from the backlog. Confirm they're ready to launch (design done, tracking in place, hypothesis written). Assign owners. Set launch dates. | 3–5 experiments launching this week with clear owners. |
| **20–30 min** | **Brainstorm** | Open floor. Anyone can pitch a new experiment idea. Quick ICE scoring. Add to backlog. Keep it high-energy — no idea is too small or too weird at this stage. | 5–10 new experiment ideas in the backlog, ICE scored. |

**The rules of the growth meeting:** (1) Everyone comes prepared — read the results before the meeting. (2) Decisions are final — don't relitigate last week's decisions. (3) No experiment launches without a written hypothesis. (4) The meeting ends at 30 minutes, period. If you need more time, something is broken.

## Who Attends

- **Required:** Growth lead (runs the meeting), PM, 1 engineer, 1 designer, 1 marketer.
- **Optional:** Data analyst (for statistical questions), sales rep (for qualitative input).
- **Never:** More than 8 people. Growth meetings die when they become status updates for leadership.

---

# 09 Building a Growth Culture

The difference between a team that runs 2 experiments/week and one that runs 10 isn't headcount or budget. It's culture. Here's how to build it.

## The Five Principles

### 1. Document Everything

Every experiment goes in the tracker. Every result gets a written analysis. Every learning gets tagged and searchable. In 12 months, you'll have 200+ experiments worth of institutional knowledge. New team members can read the log and understand what works in days, not months.

### 2. Celebrate Learnings, Not Just Wins

A failed experiment that teaches you something is more valuable than a successful experiment you can't explain. When an experiment fails:

- Don't hide it. Share it in Slack. "GE-047 failed: outcome-focused CTAs don't work for enterprise prospects. They prefer specificity ('see how Acme saved $1.2M') over generality ('save 40%')."
- Ask "what did we learn?" not "why did it fail?"
- Update your mental model. Failure + learning = progress. Failure + silence = waste.

The most dangerous outcome of an experiment is not failure. It's success you can't explain. If you don't know WHY something worked, you can't replicate it, scale it, or build on it. Always understand the "why."

### 3. Lower the Bar for Launching

If an experiment requires a design review, a product spec, a legal review, and a VP sign-off, you'll run 2 experiments per month instead of 10 per week. Most experiments are low-risk (copy changes, email sequences, landing page variants). Create a fast lane:

| Experiment Type | Approval Needed | Time to Launch |
| --- | --- | --- |
| Copy/headline change | None — just launch | Same day |
| Email sequence test | Growth lead approval | 1–2 days |
| Landing page variant | Growth lead + designer | 2–3 days |
| Onboarding flow change | PM + engineer sign-off | 1 week |
| Pricing change | VP + finance approval | 2 weeks |
| Core product change | Full product review | Sprint planning |

### 4. Build a Growth Playbook

After 6 months of experiments, you'll notice patterns. Document them:

- "Outcome-focused headlines beat feature-focused headlines 80% of the time (n=12 experiments)."
- "Re-engagement emails work best when sent at Day 14, not Day 7 (n=4 experiments)."
- "Annual billing defaults increase annual plan selection by 20–35% with no measurable drop in total signups (n=3 experiments)."

This playbook is your competitive advantage. It's knowledge that took months and thousands of dollars of experiment time to build. Competitors don't have it.

### 5. Make Data Accessible

If only the data analyst can check experiment results, you've created a bottleneck. Set up dashboards that anyone on the growth team can check. The tools don't matter (Amplitude, Mixpanel, even a Google Sheet that auto-updates). What matters is that any team member can answer "how is GE-042 performing?" in 30 seconds.

---

# 10 When to Scale vs Kill

Every completed experiment leads to one of three decisions: **scale it, kill it, or iterate on it.** This is where most teams get stuck — they don't have clear criteria, so winning experiments sit in limbo for weeks and losing experiments zombie on because nobody wants to admit they failed.

## The Decision Framework

| Result | Criteria | Action | Timeline |
| --- | --- | --- | --- |
| **Clear Winner** | +10% or more improvement, statistically significant (p < 0.05), no guardrail degradation | **Scale immediately.** Ship to 100% of users. Document the learning. Plan follow-up experiments to amplify the effect. | Ship within 48 hours of analysis. |
| **Promising** | +5–10% improvement, statistically significant, guardrails intact | **Scale, but keep monitoring.** Ship to 100% and re-check metrics after 2 weeks. Smaller effects can sometimes be noise amplified by luck. | Ship within 1 week. Re-check at week 3. |
| **Inconclusive** | Small effect (<5%), not statistically significant even with adequate sample | **Kill the experiment, iterate on the hypothesis.** The change wasn't big enough. Try a bolder variant. If you've tested 3 variants with no signal, abandon the hypothesis entirely. | Decision within 24 hours. Don't extend hoping for significance. |
| **Clear Loser** | Negative impact, or guardrail metrics degraded | **Kill immediately.** Revert to control. Document the learning — understanding why it failed is the whole point. | Revert within 24 hours. |

**The sunk cost trap:** "But we spent 2 weeks building this feature for the experiment." Doesn't matter. If the data says it doesn't work, kill it. The 2 weeks are gone whether you ship it or not. Shipping a losing variant because you feel bad about the effort is the most expensive mistake in growth.

## Scaling Checklist

Before scaling a winning experiment to 100%:

- Confirm statistical significance with your data team. Don't trust the A/B tool's dashboard blindly.
- Check segment-level results. Did it work for all segments, or just one? If it only worked for enterprise but hurt SMB, you need a segmented rollout.
- Verify guardrail metrics. A 20% lift in signups means nothing if 30-day retention dropped 15%.
- Document the learning in the experiment log and the growth playbook.
- Plan the follow-up. If the headline test won, what headline variants should you test next? Compounding wins is the game.

## The Velocity Target

Track your team's experiment velocity as a meta-metric:

| Stage | Weekly Experiments | What It Means |
| --- | --- | --- |
| Getting started | 1–2 | Building the muscle. Focus on process and documentation. Speed comes later. |
| Functional | 3–5 | Good cadence. Running multiple experiments across AARRR stages. Learning is accumulating. |
| High-performing | 5–10 | Growth is a core competency. Team has systems, tools, and culture to support high velocity. |
| Elite | 10–15+ | Multiple parallel workstreams. Dedicated experimentation infrastructure. This is where companies like Airbnb, Booking.com, and Netflix operate. |

**Don't compare yourself to Netflix on day one.** Start at 1–2 experiments per week. Get the process right. Build the habit. In 3 months, you'll naturally be at 5/week because you've eliminated the friction. Trying to force 10/week before you have the infrastructure leads to sloppy experiments and bad data.

---

**The Growth Experiment Checklist**  
  
Write the hypothesis first      no hypothesis = no experiment  
ICE score everything         prioritize ruthlessly, don't go by gut  
One change per experiment    if you change two things, you learn nothing  
Set duration upfront         don't peek, don't stop early  
Define guardrail metrics     don't optimize one metric by destroying another  
Log every experiment        wins, losses, and inconclusives  
Ship winners in 48 hours    velocity of scaling matters as much as velocity of testing  
Kill losers immediately     sunk costs are sunk  
  
Growth is not a hack. It's a system. Build the system. Run the system. Trust the math.
