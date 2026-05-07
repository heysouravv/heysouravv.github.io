---
layout: post
title: "Weekly Sales Dashboard Template"
categories: [playbooks]
---

Weekly Sales Dashboard Template

metrics · formulas · benchmarks · cadence

Sales Ops
Dashboard
Forecasting
MBA Intern
Weekly Review

Most sales dashboards are decoration. They look impressive in board decks but nobody actually uses them to make decisions. The numbers are stale by the time anyone reads them, the metrics are vanity (total pipeline! total activities!), and there's no connection between what the dashboard shows and what the team should *do differently*.

This playbook builds a dashboard that a sales leader actually opens every Monday morning, spends 15 minutes on, and walks away with 3 specific actions. It tracks leading indicators (what's about to happen) not just lagging indicators (what already happened). And it's opinionated — every metric has a target, and every missed target has a prescribed action.

**Who this is for:** MBA interns building their first sales dashboard, RevOps analysts designing weekly reporting, and sales leaders who want a template they can ship in a day.

---


Part I

The Dashboard Philosophy

Before building a single chart, you need to understand what makes a dashboard useful versus what makes it a vanity project. The difference is whether it changes behaviour.

# 01 Why Weekly, Not Monthly

Monthly reporting is an autopsy. By the time you see that pipeline coverage dropped or win rate tanked, you've already lost 4 weeks of potential correction. You can't un-lose the deals. You can't un-skip the prospecting.

Weekly reporting is a diagnostic. You catch problems **while they're still fixable**:

- **Pipeline coverage dropped below 3x this week?** You have 3 weeks before it shows up in a missed forecast. Time to run a prospecting blitz.
- **Rep X had zero meetings booked last week?** That means zero new pipeline in 30 days. Intervene now, not after the quarter ends.
- **Average deal size trending down?** Catch it in week 3, not month 3. Are reps discounting? Selling to smaller accounts? Wrong product mix?

A weekly dashboard that takes 15 minutes to review is worth more than a monthly dashboard that takes 3 hours to build and nobody reads.

## The 15-Minute Monday Review

Your dashboard should answer exactly three questions in 15 minutes or less:

1. **Are we on track to hit the number this quarter?** (Forecast vs quota)
2. **Do we have enough pipeline to hit next quarter's number?** (Pipeline coverage)
3. **Is anyone falling behind?** (Rep-level attainment and activity)

If your dashboard requires more than 15 minutes, it has too many metrics. Cut ruthlessly.

---

# 02 Leading vs Lagging Indicators

This is the single most important concept in sales dashboarding. Most dashboards are 90% lagging indicators. Yours should be 60% leading.

| Type | What it tells you | Examples | When you can act |
| --- | --- | --- | --- |
| **Leading** | What's about to happen | Pipeline created, meetings booked, proposals sent, new contacts added | While there's still time to change the outcome |
| **Lagging** | What already happened | Revenue closed, win rate, average deal size, churn | After it's too late to change this quarter |
| **Diagnostic** | Why something happened | Loss reasons, sales cycle by segment, discount rates, stage conversion | To fix the process for next quarter |

**The trap:** Revenue closed is the metric the board cares about. But by the time you see a revenue miss, the deals were already lost 60–90 days ago. The leading indicators — meetings booked, pipeline created, proposals sent — told the story months earlier. Your dashboard should scream "warning" at the leading indicator stage, not at the revenue stage.

**Rule of thumb:** For every lagging metric on your dashboard, you should have at least two leading metrics that predict it. Revenue is predicted by pipeline coverage + win rate. Pipeline is predicted by meetings booked + outbound activity. Work backwards from the number you need to hit.

---


Part II

The Metrics

Every metric below includes the formula, the benchmark target, and what to do if you're below target. If a metric doesn't have a "what to do" action, it doesn't belong on your dashboard.

# 03 Pipeline Metrics

Pipeline is the lifeblood of a sales team. These metrics tell you whether you have enough opportunities, whether they're moving, and whether they're healthy.

| Metric | Formula | Target | If Below Target |
| --- | --- | --- | --- |
| **Pipeline Coverage** | `Total Open Pipeline / Remaining Quota` | 3.0x – 4.0x | Prospecting blitz. Every AE adds 5 net-new opps this week. Cancel non-essential internal meetings. |
| **Pipeline Velocity** | `(# Opps × Win Rate × Avg Deal Size) / Avg Sales Cycle Days` | Trending up or flat WoW | Identify which variable is dragging: fewer opps? Lower win rate? Smaller deals? Longer cycles? Fix the bottleneck. |
| **Pipeline Created This Week** | `Sum of ACV for opps created in the last 7 days` | 15–20% of quarterly quota / 13 weeks | SDR team needs more activity. AEs need to self-source. Review ICP — are we targeting the right accounts? |
| **Aging Deals (>2x avg cycle)** | `# of opps open longer than 2x average sales cycle` | < 10% of total pipeline | Force a decision: close or kill. Zombie deals inflate pipeline coverage and mask real problems. |
| **Stage Conversion Rates** | `Opps moving to Stage N+1 / Opps in Stage N (weekly)` | Varies by stage (see below) | If a stage has low conversion, the exit criteria are wrong, reps lack skills for that stage, or bad deals aren't being disqualified. |

### Stage Conversion Benchmarks (B2B SaaS, Mid-Market)

| Stage | Description | Conversion to Next | Typical Duration |
| --- | --- | --- | --- |
| S1 | Discovery / Qualification | 60–70% | 5–10 days |
| S2 | Needs Analysis / Demo | 50–60% | 7–14 days |
| S3 | Proposal / Evaluation | 40–55% | 10–21 days |
| S4 | Negotiation / Legal | 70–85% | 7–14 days |
| S5 | Closed Won | — | — |

**The pipeline coverage lie:** 4x coverage means nothing if 40% of the pipeline is zombie deals that will never close. Calculate **real coverage**: remove all deals that haven't had activity in 21+ days. If your "real" coverage is below 2.5x, you have a problem — regardless of what the headline number says.

---

# 04 Activity Metrics

Activity metrics are the purest leading indicators. They tell you **right now** whether next month's pipeline will exist.

| Metric | Formula | Target (per AE/week) | If Below Target |
| --- | --- | --- | --- |
| **Meetings Booked** | `Count of qualified meetings scheduled this week` | 4–6 | Outbound volume too low, or messaging isn't converting. Check email reply rates and call connect rates. |
| **Meetings Held** | `Count of meetings that actually happened` | 3–5 (75%+ show rate) | No-show problem. Send calendar reminders. Confirm day-before via email. Call 5 min after no-show. |
| **Calls Made** | `Outbound dials logged in CRM` | 40–60 (AEs doing own prospecting) | AEs spending too much time on non-selling activities. Audit their calendar for unnecessary internal meetings. |
| **Emails Sent** | `Personalised outbound emails (not sequences)` | 30–50 | Prospecting discipline issue. Block 1hr/day for outbound and treat it as non-negotiable. |
| **Proposals Sent** | `Formal proposals or SOWs delivered to prospects` | 2–4 | Deals stalling in discovery. Are reps afraid to ask for the next step? Do they lack proposal templates? |

Activity metrics are not about micromanagement. They're about early warning systems. If an AE's meetings booked drops to zero for two consecutive weeks, that AE will miss quota in 60 days. Guaranteed. The dashboard should make this visible before it's a crisis.

---

# 05 Revenue Metrics

These are the lagging indicators — the scoreboard. They tell you what happened, not what's going to happen. Track them weekly to spot trends, but don't use them as the primary management tool.

| Metric | Formula | Target | If Below Target |
| --- | --- | --- | --- |
| **Closed Won (Weekly)** | `Sum of ACV for deals closed-won this week` | Quota / 13 weeks (linear) | Check forecast accuracy. Were these deals expected? If not, your forecast process is broken. |
| **Closed Lost (Weekly)** | `Sum of ACV for deals closed-lost this week` | Track trend, not absolute | Review loss reasons. If a pattern emerges (price, competitor, timing), escalate to leadership. |
| **ACV Trend** | `4-week rolling average ACV of closed-won deals` | Flat or increasing | If decreasing: reps discounting too heavily, or selling to smaller accounts. Review discount approvals. |
| **Win Rate** | `Closed Won / (Closed Won + Closed Lost)` | 20–30% (mid-market SaaS) | Below 20%: qualification problem (bad deals entering pipeline). Above 35%: not enough pipeline (only pursuing safe bets). |
| **Average Sales Cycle** | `Average days from opp creation to close-won (rolling 90d)` | Varies by segment | If lengthening: deals stalling in a specific stage. Check stage-level conversion to find the bottleneck. |

### Sales Cycle Benchmarks by Segment

| Segment | Typical ACV | Average Cycle | Stakeholders Involved |
| --- | --- | --- | --- |
| SMB | $5K – $15K | 14 – 30 days | 1–2 |
| Mid-Market | $25K – $75K | 30 – 60 days | 3–5 |
| Enterprise | $100K – $500K | 60 – 120 days | 5–10 |
| Strategic | $500K+ | 120 – 270 days | 8–15+ |

---

# 06 Forecast Metrics

Forecasting is where art meets science. The dashboard should track both the forecast itself and how accurate the forecast has been — because most sales teams are terrible at forecasting, and they need to see that fact in writing.

| Metric | Formula | Target | If Below Target |
| --- | --- | --- | --- |
| **Commit** | `Sum of ACV where AE says "will close this quarter" (90%+ confidence)` | ≥ 80% of remaining quota | Gap to quota = amount of pipeline that needs to convert from Upside to Commit. Is that realistic? |
| **Upside** | `Sum of ACV with 50–80% probability, expected this quarter` | 1.5–2x the gap between Commit and Quota | Not enough deals in late stages. Either pipeline was created too late, or deals are stuck. |
| **Best Case** | `Commit + Upside + stretch deals` | 120–140% of quota | If best case < quota, the quarter is already lost barring a miracle. Start planning for next quarter. |
| **Weighted Pipeline** | `Sum of (ACV × Stage Probability) for all open opps` | ≥ Remaining Quota | Not enough pipeline at high enough stages. Need to accelerate deals or create more pipeline. |
| **Forecast Accuracy (trailing)** | `Actual Closed / Forecasted Commit (last 4 weeks)` | 85–110% | Below 85%: reps are committing deals that slip. Above 110%: reps are sandbagging. Both are problems. |
| **Slip Rate** | `Deals that were in Commit last week but didn't close / Total Commit` | < 15% | Reps committing deals without confirmed close plans. Tighten commit criteria: must have verbal yes + legal in progress. |

**The sandbagging tax:** When reps sandbag (hide good deals from the forecast to look like heroes), leadership can't allocate resources, can't plan hiring, and can't set accurate expectations with the board. Sandbagging is just as bad as over-committing. Track forecast accuracy both ways.

---

# 07 Rep-Level Metrics

The team dashboard hides individual performance problems. A team hitting quota can have 2 reps at 150% and 3 reps at 60%. The rep-level view surfaces this.

| Metric | What It Shows | Action Trigger |
| --- | --- | --- |
| **Individual Pipeline** | Each AE's open pipeline vs their individual quota | Coverage < 2.5x → 1:1 prospecting plan |
| **Individual Activity** | Meetings, calls, emails per AE per week | Below 50% of team avg for 2+ weeks → performance conversation |
| **Quota Attainment (QTD)** | Each AE's closed-won vs pro-rated quarterly quota | Below 70% of pro-rata at midpoint → deal review + action plan |
| **Win Rate (Individual)** | Each AE's win rate vs team average | Consistently 10+ pts below avg → ride-alongs, deal coaching |
| **Ramp Status** | New hires: months since start, ramp quota, actual attainment | Behind ramp by month 4 → additional enablement, adjusted territory |

### Ramp Schedule Benchmarks (Mid-Market AE)

| Month | Ramp Quota (% of full) | Expected Pipeline | Expected Closed |
| --- | --- | --- | --- |
| Month 1 | 0% | Learning the product, shadowing calls | $0 |
| Month 2 | 0% | Begin prospecting, first discovery calls | $0 |
| Month 3 | 25% | 1–2x quota in pipeline | First deal possible |
| Month 4 | 50% | 2–3x quota in pipeline | $15K–$25K |
| Month 5 | 75% | 3x+ quota in pipeline | $25K–$40K |
| Month 6+ | 100% | Full quota expectations | Full quota |

---


Part III

Building It

You don't need a BI tool. Google Sheets or Excel with data pulled from your CRM is enough to build a dashboard that's more useful than 90% of what Tableau produces. Here's how.

# 08 Google Sheets / Excel Setup

Your dashboard workbook should have exactly 4 tabs:

| Tab | Purpose | Updated |
| --- | --- | --- |
| **1. Summary** | The one-page view. All key metrics, colour-coded red/yellow/green. This is what you review on Monday. | Auto-calculated |
| **2. Pipeline Data** | Raw CRM export: every open opportunity with stage, ACV, close date, owner, last activity date, days open | Weekly (Monday AM) |
| **3. Activity Data** | Weekly activity totals per rep: calls, emails, meetings booked, meetings held, proposals sent | Weekly (Monday AM) |
| **4. History** | Week-over-week tracking. Each row = one week. Columns = all key metrics. This is how you spot trends. | Append each week |

**The simplicity principle:** Resist the urge to build 12 tabs with pivot tables and conditional formatting. The dashboard you actually use every Monday is better than the beautiful one you stop updating in week 3. Start with 4 tabs. Add complexity only when you've used it for a full quarter.

## Summary Tab Layout

Structure the Summary tab in 5 horizontal sections, top to bottom:

1. **Header:** Quarter, weeks remaining, team quota, closed-won QTD, gap to quota
2. **Forecast:** Commit, Upside, Best Case, Weighted Pipeline
3. **Pipeline:** Coverage, Created this week, Aging deals, Velocity
4. **Activity:** Team totals for meetings, calls, emails, proposals (with WoW change)
5. **Rep Scorecard:** One row per AE with pipeline, attainment %, activity grade

---

# 09 CRM Reports to Pull

Whether you're on Salesforce, HubSpot, Pipedrive, or Close, you need these 5 CRM reports exported weekly:

| # | Report | Fields Needed | CRM Filter |
| --- | --- | --- | --- |
| **1** | Open Pipeline | Opp name, Owner, Stage, ACV, Close date, Created date, Last activity, Days in current stage | Stage != Closed Won/Lost, Close date = this quarter or next |
| **2** | Closed Won (This Week) | Opp name, Owner, ACV, Close date, Sales cycle days, Source | Close date = last 7 days, Stage = Closed Won |
| **3** | Closed Lost (This Week) | Opp name, Owner, ACV, Close date, Loss reason, Competitor | Close date = last 7 days, Stage = Closed Lost |
| **4** | Pipeline Created (This Week) | Opp name, Owner, ACV, Source, Stage | Created date = last 7 days |
| **5** | Activity Report | Owner, Calls logged, Emails sent, Meetings booked, Meetings held, Proposals sent | Activity date = last 7 days, grouped by owner |

**Pro tip:** In Salesforce, save these as scheduled reports that email you a CSV every Monday at 7am. In HubSpot, create saved views with these exact filters. The goal is to make the Monday data pull take less than 5 minutes so you never skip it.

---

# 10 Formulas Reference

Every formula you need for the dashboard, written for Google Sheets. Adapt cell references to your layout.

| Metric | Formula (Google Sheets) | Notes |
| --- | --- | --- |
| **Pipeline Coverage** | `=SUMIF(Pipeline!D:D,"<>Closed*",Pipeline!C:C) / (Quota - ClosedWonQTD)` | Exclude closed stages. Divide by remaining quota, not total quota. |
| **Pipeline Velocity** | `=(NumOpps * WinRate * AvgDealSize) / AvgCycleDays` | Gives you daily revenue velocity. Multiply by remaining days for expected revenue. |
| **Win Rate** | `=COUNTIF(Stage,"Closed Won") / (COUNTIF(Stage,"Closed Won") + COUNTIF(Stage,"Closed Lost"))` | Exclude open deals. Rolling 90-day window is most useful. |
| **Weighted Pipeline** | `=SUMPRODUCT(ACV, StageProbability)` | Assign probability by stage: S1=10%, S2=25%, S3=50%, S4=75%, S5=100% |
| **Aging Deals** | `=COUNTIFS(DaysOpen,">"&(2*AvgCycle), Stage,"<>Closed*")` | Deals open longer than 2x your average sales cycle. |
| **Forecast Accuracy** | `=ActualClosed / CommitForecast` | Calculate weekly. Track in History tab. 4-week rolling average smooths noise. |
| **WoW Change** | `=(ThisWeek - LastWeek) / LastWeek` | Format as percentage. Conditional format: green if positive, red if negative. |

**Conditional formatting rules:** Apply these to your Summary tab for instant visual scanning. Green = at or above target. Yellow = within 10% of target. Red = more than 10% below target. The Monday review should take 15 seconds of scanning colours before you read any numbers.

---


Part IV

The Weekly Cadence

A dashboard without a meeting cadence is just a spreadsheet. These three weekly touchpoints turn data into action.

# 11 Monday Pipeline Review (15 min)

**When:** Monday 9:00–9:15 AM. **Who:** Sales leader + all AEs. **Format:** Standing meeting, screen-sharing the dashboard.

### Agenda

| Time | Topic | What to cover |
| --- | --- | --- |
| **0–3 min** | Scoreboard | QTD closed vs quota. Pipeline coverage. WoW change in key metrics. Green/yellow/red status. |
| **3–8 min** | Pipeline Health | New pipeline created last week. Aging deals (name them). Stage conversion drops. Any deals slip from commit? |
| **8–13 min** | Activity Check | Any rep below activity minimums? Any rep with zero meetings booked? What's the plan to fix it? |
| **13–15 min** | Actions | 3 specific actions for the week. Who owns each. No more than 3. |

**The 15-minute rule:** This meeting must end at 15 minutes. If a deal needs deeper discussion, take it to the Wednesday review. The Monday meeting is a pulse check, not a strategy session. If it consistently runs over, you have too many metrics or too many people talking.

---

# 12 Wednesday Deal Review (30 min)

**When:** Wednesday 2:00–2:30 PM. **Who:** Sales leader + 1–2 AEs (rotate). **Format:** Deep dive on 3–4 specific deals.

### Deal Selection Criteria

Don't review all deals. Review the ones that matter most right now:

- **Commit deals closing this month:** What's the close plan? What could go wrong?
- **Largest deals in pipeline:** Are they progressing? Multi-threaded? Executive sponsor identified?
- **Stuck deals:** No stage movement in 14+ days. What's the blocker?
- **Deals with competitors:** What's our positioning? Do we know the competitor's pricing?

### Questions to Ask for Each Deal

| Category | Question |
| --- | --- |
| **Champion** | Who is our champion? Have they sold internally on our behalf? What happens if they leave? |
| **Decision** | Who is the economic buyer? Have we met them? What's their decision criteria? |
| **Timeline** | Why does this need to happen by the close date? What's the compelling event? Is the timeline theirs or ours? |
| **Competition** | Who else are they evaluating? What do they like about the competitor? Where are we positioned? |
| **Next Step** | What is the specific next step? (If the answer is "follow up" that's not a next step.) |

The best deal reviews don't just ask "what's the status?" — they ask "what's the close plan?" A close plan has a specific next step, a specific date, and a specific person. "I'll follow up next week" is not a close plan. "I'm sending the proposal to the CFO on Thursday, and we have a review call booked for Monday" is a close plan.

---

# 13 Friday Forecast (15 min)

**When:** Friday 4:00–4:15 PM. **Who:** Sales leader (solo or with RevOps). **Format:** Update the forecast categories and submit to leadership.

### The Forecast Update Process

1. **Review each AE's Commit deals:** Did anything slip this week? Is the close plan still intact? Move slipped deals from Commit to Upside.
2. **Review Upside deals:** Did any Upside deals advance enough to become Commit? (Must have: verbal yes, defined close plan, confirmed timeline.)
3. **Calculate the gap:** Remaining Quota minus Commit = Gap. Is the Upside pool large enough to fill the gap at a realistic conversion rate?
4. **Submit the call:** Your forecast to leadership should be: "We will close [Commit number]. Upside of [Upside number]. Risk: [biggest risk to the Commit number]."

| Category | Confidence | Criteria |
| --- | --- | --- |
| **Commit** | 90%+ | Verbal yes from decision maker. Legal/procurement in progress. Close date confirmed. Specific close plan exists. |
| **Upside** | 50–80% | In late stages (S3–S4). Champion identified and active. Expected close this quarter but close plan not yet confirmed. |
| **Best Case** | 20–50% | Viable deals that could close if everything goes right. Early stages or stalled deals that might reactivate. |

**Forecast accuracy goal:** Over time, your Commit number should land within +/- 10% of actual closes each week. If you're consistently off by more than 20%, the team's commit criteria are too loose. Tighten them: verbal yes isn't enough — require a signed order form or PO in progress to count as Commit.

---


Part V

Complete Example Dashboard

A fully worked dashboard for a hypothetical 5-AE mid-market SaaS team. Q2 2026, Week 7 of 13. Quota: $2.5M team ($500K per AE). ACV: $45K average. All numbers are realistic.

# 14 Full Dashboard — NovaCRM (5 AEs, Q2 2026)

NovaCRM — Q2 2026 Sales Dashboard · Week 7 of 13

| KPI | Value | Target | Status |
| --- | --- | --- | --- |
| **Team Quota (Q2)** | $2,500,000 | — | — |
| **Closed Won (QTD)** | $1,180,000 | $1,346,000 (pro-rata W7) | 88% |
| **Gap to Quota** | $1,320,000 | — | — |
| **Weeks Remaining** | 6 | — | — |

## Forecast

| Category | Amount | Target | Status | Notes |
| --- | --- | --- | --- | --- |
| **Commit** | $890,000 | ≥ $1,056,000 (80% of gap) | 84% of target | $166K short of where Commit should be. Need 2 Upside deals to advance to Commit this week. |
| **Upside** | $720,000 | $660,000 (1.5x gap minus Commit) | 109% | Healthy Upside pool. Focus on converting $200K to Commit. |
| **Best Case** | $2,790,000 | $3,000,000 (120% of quota) | 93% | Achievable if win rate holds and no major slips. |
| **Weighted Pipeline** | $1,540,000 | $1,320,000 (gap) | 117% | Weighted pipeline covers the gap. Watch for deal slippage. |
| **Slip Rate (Last 2 weeks)** | 18% | < 15% | Above target | 3 deals slipped from Commit. Two were "verbal yes" with no confirmed close plan. Tighten criteria. |

## Pipeline Health

| Metric | Value | Target | Status | WoW Change |
| --- | --- | --- | --- | --- |
| **Total Open Pipeline** | $4,620,000 | — | — | +$340K (+8%) |
| **Pipeline Coverage** | 3.5x | 3.0–4.0x | On target | +0.3x |
| **Pipeline Created This Week** | $380,000 | $290,000 | 131% | +$120K |
| **Aging Deals (>90 days)** | 7 deals ($510K) | < 5 deals | Above target | +2 deals |
| **Pipeline Velocity** | $12,400/day | $11,000/day | 113% | +$800/day |

**Action needed:** 7 aging deals totaling $510K are inflating pipeline coverage. Without them, real coverage drops to 3.1x. Review all 7 on Wednesday: close, advance, or kill. The 2 new aging deals this week (Meridian Corp $85K and TechFlow $65K) haven't had activity in 28 days.

## Activity (Team Totals — This Week)

| Metric | Total | Per AE Avg | Target/AE | Status | WoW |
| --- | --- | --- | --- | --- | --- |
| **Meetings Booked** | 22 | 4.4 | 4–6 | On target | +3 |
| **Meetings Held** | 18 | 3.6 | 3–5 | On target | +1 |
| **Calls Made** | 185 | 37 | 40–60 | Below avg | -22 |
| **Emails Sent** | 210 | 42 | 30–50 | On target | +15 |
| **Proposals Sent** | 11 | 2.2 | 2–4 | On target | +2 |

## Rep Scorecard

| AE | Quota | Closed QTD | Attain % | Pipeline | Coverage | Meetings | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Sarah Kim** | $500K | $340K | 68% | $980K | 6.1x | 6 | On track |
| **Marcus Reeves** | $500K | $310K | 62% | $860K | 4.5x | 5 | On track |
| **Aisha Patel** | $500K | $280K | 56% | $1,020K | 4.6x | 4 | Watch — large pipeline but low close rate (15%) |
| **Tom Nguyen** | $500K | $160K | 32% | $680K | 2.0x | 5 | At risk — low pipeline, needs 3 new opps this week |
| **Jess Rivera** Ramp M4 | $250K | $90K | 36% | $580K | 3.6x | 2 | On ramp — tracking to ramp target |

**This week's focus:**  
1. **Tom Nguyen:** 1:1 pipeline building session. Coverage at 2.0x is critical. Block 3 hours for prospecting blitz. Review his target account list.  
2. **Aisha Patel:** Deal coaching. High pipeline (4.6x) but low win rate (15% vs team avg 24%). Review her discovery calls — likely not qualifying hard enough.  
3. **Aging deals:** Review all 7 on Wednesday. Kill at least 3. That $510K is inflating everyone's numbers.

## Revenue — This Week

| Metric | This Week | Last Week | WoW | Q2 Total |
| --- | --- | --- | --- | --- |
| **Closed Won** | $185,000 (3 deals) | $140,000 (2 deals) | +32% | $1,180,000 |
| **Closed Lost** | $120,000 (2 deals) | $95,000 (2 deals) | +26% | $680,000 |
| **Average ACV (Won)** | $61,700 | $70,000 | -12% | $45,400 (rolling) |
| **Win Rate (Rolling 90d)** | 24% — On target (20–30% benchmark) | | | |
| **Avg Sales Cycle (Rolling 90d)** | 42 days — On target (30–60 day benchmark for mid-market) | | | |

---

**The Dashboard Checklist**  
  
Update every Monday        5 min data pull, 15 min review  
Leading > Lagging          60% leading indicators, 40% lagging  
Every metric has an action   if below target, what do you DO?  
Rep-level visibility        team averages hide individual problems  
Kill zombie deals           pipeline coverage means nothing if 30% is dead  
Track forecast accuracy     hold yourself accountable to what you commit  
3 actions per week max      focus beats coverage every time  
  
The dashboard doesn't close deals. It tells you where to focus so your team can.
