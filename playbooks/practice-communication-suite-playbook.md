# Clairvance — Practice Communication Suite
## Sales & Delivery Playbook | Medical Practice Edition
**Version:** 1.0 | Confidential — Internal Use Only

---

## What This Bundle Is

The **Practice Communication Suite** is Clairvance's bundled automation offer for independent medical practices. It combines two systems that address the same root problem — **patients who tried to reach the practice and didn't get a response** — from two different entry points.

| System | What It Solves | Response Time |
|---|---|---|
| Missed Call Recovery | Patient called, no one answered | < 60 seconds |
| Inbox Triage Bot | Patient emailed, no one prioritized it | < 1 hour |

Sold separately, these are two products. Sold together, they are a **complete patient communication recovery layer** — the safety net that catches every patient who tried to reach the practice and almost fell through the cracks.

---

## Infrastructure Model — Who Owns What

**Clairvance owns and manages all infrastructure.** This is non-negotiable for managed service delivery.

| Component | Owner | How It Works |
|---|---|---|
| Twilio master account | Clairvance | One account, one subaccount per client — isolated numbers, usage, logs |
| Twilio phone number | Clairvance (subaccount) | Number lives in client's subaccount; portable to client if they leave |
| Railway account | Clairvance | One project per client; isolated env vars and deployments |
| Google Sheets log | Client | Client's own Google Sheet — they own their data |
| Gmail OAuth access | Client grants, Clairvance manages | Client authorizes; credentials stored in Railway env vars |

**Infrastructure cost per client (included in retainer):**
- Twilio number: ~$1.10/month
- Twilio SMS usage: ~$0.0079/message (~$5–20/month typical)
- Railway deployment: ~$5–15/month
- Claude API: ~$5–20/month
- **Total: ~$20–65/month** against a $1,500/month minimum retainer

Never itemize these costs to the client. They're not buying infrastructure. They're buying a managed system.

---

## Email Provider Qualification — Know Before You Pitch

The Inbox Triage Bot currently supports **Gmail and Google Workspace only.**

Add this question to every Discovery call: *"What email system does your practice use for day-to-day operations?"*

| Their Answer | Inbox Triage Available? | Your Move |
|---|---|---|
| Gmail / Google Workspace | Yes | Full bundle available |
| Microsoft 365 / Outlook | Not yet | Lead with Missed Call Recovery only; position inbox triage as "coming Q[next quarter]" |
| GoDaddy / generic hosting | Not yet | Same as above |
| Not sure | Clarify | Ask: "When you open your email, what app do you use — Gmail or Outlook?" |

**This is not a deal-killer.** Missed Call Recovery stands alone as a complete product. If they're on Outlook, you close the missed call system, deliver it, build trust, and add inbox triage when the Microsoft 365 version is ready. Do not position this as a limitation — position it as a roadmap.

> *"The missed call system works with any phone setup — that's what we're deploying for you today. The email triage system is built specifically for Google Workspace, which I see you're [using / not using]. We'll [include it now / add it when your Microsoft integration is ready in Q[X]]."*

---

## The Prospect Profile

**Who buys this:** Independent medical practices (family medicine, internal medicine, pediatrics, OB/GYN, urgent care) with:
- 1–5 providers
- 3–15 front desk / admin staff
- 100–400 patient visits per week
- An office manager or practice administrator who owns the operational pain (this is your buyer, not the physician)

**Who does NOT buy this (yet):** Hospital-affiliated practices, large multi-location groups, practices with a dedicated IT function. They have enterprise contracts. Don't waste time there.

**The emotional profile of your buyer:**
The office manager is overwhelmed. She is managing phones, insurance verification, scheduling, patient questions, and staff issues simultaneously. She is not hostile to technology — she's skeptical that it will actually work without creating more problems for her. She has been burned before by a tool that required constant maintenance. Your job is not to sell her AI. Your job is to sell her **relief**.

---

## The ROI Framework — Run This Math Before Every Call

Fill this in using numbers from your Workflow Audit before quoting anything.

### Missed Call ROI
```
Missed calls per day:           ______
Days open per month:            ______
Total missed calls/month:       ______ (A)

% that are new patient inquiries: ______ (estimate 20-30%)
New patient inquiries/month:    ______ (B = A × %)

New patient visit value:        $______ (family medicine avg: $250-$350)
Recovery rate with SMS follow-up: 30% (conservative)

Monthly recovered revenue:      $______ (C = B × recovery rate × visit value)
Annual recovered revenue:       $______ (C × 12)
```

### Inbox Triage ROI
```
Emails processed per day:       ______
Avg staff minutes per email:    ______ (estimate 4-6 min without triage)
Staff hourly cost (loaded):     $______ (estimate $22-$28/hr for front desk)

Hours saved per month:          ______ 
Monthly labor cost recovered:   $______
Annual labor cost recovered:    $______
```

### The Close Number
> "Based on what you've shared, your practice is losing approximately **$[X]/month** in missed patient opportunities and **$[Y]/month** in staff time on email management. That's **$[X+Y]/month** — or **$[(X+Y)×12]/year** — leaving through two holes that are completely fixable. The system I'm proposing recovers that within 60 days of going live."

---

## Pricing — Practice Communication Suite

### Bundle Pricing

| | Sold Separately | Bundle Price |
|---|---|---|
| Missed Call Recovery (build) | $2,500 | |
| Inbox Triage Bot (build) | $3,500 | |
| **Combined Build Fee** | **$6,000** | **$4,997** |
| **Monthly Retainer** | $1,750/mo | **$1,500/mo** |

Bundle saves the client $1,003 upfront and $250/month. You save time on delivery because you're configuring one Google Sheets log, one Railway account, and one credential set per client.

### Value-Based Override
If the audit reveals monthly leakage above $8,000/month, do not quote the standard bundle price. Use value-based pricing:
- Build fee: $7,500–$10,000
- Monthly retainer: $2,000–$2,500
- Anchor: "Your payback period on this investment is under 45 days."

### What the Retainer Covers
Be explicit with every client. Include this in your MSA and your onboarding doc:
- System monitoring (both systems)
- SMS delivery failure alerts
- Monthly performance report (calls recovered, emails triaged, draft reply rate)
- Unlimited minor prompt and message copy adjustments
- Quarterly technology review — proactive briefing on improvements
- Issue resolution within 24 hours (Essential tier SLA)

---

## The Sales Conversation — Full Script

### Opening (after introductions)
> "I want to start by asking you one question, and I want you to be honest with me — on a typical Tuesday, how many times does a patient try to reach your office and not get a response before the end of the day? Phone calls that go to voicemail, emails that sit until someone has a free minute?"

*Let them answer. Don't interrupt. Whatever number they give you, write it down visibly.*

> "That number is the starting point for everything I'm going to show you today. Because every one of those is a patient who needed something, didn't get it, and may not try again."

---

### The Demo — Missed Call Recovery (do this first, always)
> "I'm going to call this number right now and not pick up. Watch what happens."

*Call your Twilio demo number from your cell. Don't answer. In 10–15 seconds, your phone receives the SMS. Show them both screens.*

> "That patient just got a response in under 15 seconds. They didn't go to a competitor's website. They didn't leave a bad review about never being called back. They got a text that told them someone was paying attention."

*Open your laptop. Show the Google Sheet row that just logged.*

> "And your front desk just got a record of that call, the number, and the SMS status — without touching anything. That's running 24 hours a day, seven days a week, including after hours."

---

### The Demo — Inbox Triage (second)
> "Now let me show you what happens on the email side."

*Screen share your Google Sheets triage log. Walk through 3–4 rows: one URGENT, one MEDIUM, one LOW.*

> "Every email that comes into the practice inbox gets classified — patient emergency, appointment, billing, prescription, general. The urgent ones surface immediately. Your staff sees a draft reply already written. The promotions and newsletters are filtered out automatically. Nobody has to read 40 emails to find the three that actually need a human response."

---

### Handling the HIPAA Question
This will come up. Have this answer ready — word for word.

> "That's exactly the right question to ask, and I want to give you a straight answer. The system is designed specifically to minimize contact with protected health information. Before any email content reaches the AI, it runs through a PII scrubbing layer that removes names, phone numbers, dates of birth, and other identifiers. The AI classifies and drafts based on the anonymized content. For the missed call system, the only data the AI ever sees is a phone number — no clinical information, no patient records.

> Now — I'm not going to tell you this replaces your HIPAA compliance program, because it doesn't. What I will tell you is that this system is built with the same care your staff should apply when discussing patient information, and we can walk through the data flow together so your compliance person is comfortable before we go live. I've had that conversation with other practices and it's usually a 20-minute call."

*If they push for a BAA:* "Anthropic — the company whose AI powers the email triage — does offer a Business Associate Agreement for healthcare clients. That's part of the onboarding conversation and I'll connect you directly with the right information."

---

### The Objection Table

| Objection | What It Really Means | Your Response |
|---|---|---|
| "We already have Weave/Solutionreach" | They have a reminder tool, not a recovery tool | "Weave sends reminders to scheduled patients. This catches the patient who called and never got scheduled. Different problem — complementary systems." |
| "Our staff handles that" | They haven't quantified the cost | "I believe you. Walk me through what happens when all three lines are ringing at once. Which call gets missed?" |
| "We need to think about it" | Price shock or missing stakeholder | "Completely fair. Who else needs to be in the room when you make this decision? Let's get them on a call before you decide." |
| "Can't we just hire someone?" | They haven't done the math | "A part-time hire at $18/hour, 20 hours/week, is $1,440/month — before taxes, training, and turnover. This runs 24/7 for $1,500/month and doesn't call in sick." |
| "What if the AI says something wrong?" | They want to know who's liable | "The SMS is a fixed template — no AI generates it. The inbox drafts require staff review before sending. Nothing goes out without a human checkpoint on the patient-facing side." |
| "It's too expensive" | They don't believe the ROI yet | "Let me show you the math we did earlier. At [X] missed calls per month with a 30% recovery rate, this pays for itself in [Y] weeks. What number would make you comfortable?" |

---

## Delivery Process — Client Deployment Checklist

### Week 1 — Setup & Configuration

**Missed Call Recovery**
- [ ] Purchase Twilio local number in client's area code
- [ ] Confirm client's phone system supports call forwarding (ask: "What phone system do you use?" — Weave, RingCentral, 8x8, Google Voice, or landline)
- [ ] Set up Railway environment variables for this client
- [ ] Configure `PRACTICE_NAME` and `PRACTICE_CALLBACK_NUMBER`
- [ ] Configure Twilio webhook URL pointing to client's Railway deployment
- [ ] Test: call Twilio number, confirm SMS fires, confirm Sheet logs

**Inbox Triage Bot**
- [ ] Client grants Gmail access (walk them through OAuth — 10 minutes)
- [ ] Confirm "Triage Log" tab exists in client Google Sheet
- [ ] Set Railway environment variables with client's Gmail credentials
- [ ] Run first manual execution, review 5–10 emails with client present
- [ ] Confirm labels appear in Gmail correctly
- [ ] Set cron schedule (every hour during business hours or 24/7 — client preference)

**Call Forwarding Setup (client does this, you guide)**
Exact steps depend on their phone system. Most common:
- *Weave:* Settings → Call Routing → No Answer → Forward to [Twilio number]
- *RingCentral:* Admin Portal → Phone System → Groups → Forward Unanswered
- *Standard landline:* `*72` + Twilio number (carrier call forwarding)
- *Google Voice:* Settings → Calls → Forward to [Twilio number]

### Week 2 — Pilot Monitoring
- [ ] Review Sheets daily for first 7 days — flag any anomalies
- [ ] Check triage labels in Gmail — confirm urgency mapping is accurate for this practice's email volume
- [ ] Adjust SMS copy if client requests different tone or wording
- [ ] Capture: total missed calls recovered, emails triaged, draft reply rate

### End of Pilot — Results Presentation
Present these numbers in a simple one-page summary:
- Missed calls intercepted: [X]
- SMS recovery messages sent: [X]
- Estimated new patient inquiries recovered: [X]
- Emails triaged automatically: [X]
- Staff hours saved (estimated): [X]
- Estimated revenue recovered: $[X]

> "This is what 30 days of the system running looks like. Based on these numbers, the system is returning approximately $[X] per month in recovered revenue and $[Y] per month in staff time. Your investment is $1,500/month. The ROI is [Z]x. Do you want to continue on the managed service plan?"

---

## Monthly Reporting Template

Send this to every retainer client on the 1st of each month.

```
CLAIRVANCE — Monthly Automation Report
Practice: [Name] | Period: [Month Year]

MISSED CALL RECOVERY
Total missed calls intercepted:     ___
Recovery SMS delivered:             ___
SMS delivery failures:              ___
Estimated new patient inquiries:    ___
Estimated recovered revenue:        $___

INBOX TRIAGE
Total emails processed:             ___
Urgent (flagged for immediate action): ___
High:                               ___
Medium:                             ___
Low / Filtered:                     ___
Draft replies generated:            ___
Average processing time:            < 1 hour

SYSTEM HEALTH
Uptime this month:                  ___%
Errors logged:                      ___
Issues resolved:                    ___

NEXT MONTH
[ ] Scheduled review: [date]
[ ] Recommended adjustment: [if any]
```

---

## What Can Go Wrong — And What You Do

| Problem | Likely Cause | Fix |
|---|---|---|
| SMS not sending | Twilio trial account or number not verified | Upgrade to paid Twilio; verify number |
| 403 Forbidden on webhook | Twilio signature mismatch — usually URL mismatch (http vs https) | Confirm Railway URL in Twilio console matches exactly, including protocol |
| Emails not triaging | OAuth token expired or Sheet tab name wrong | Re-run auth flow; confirm tab is named exactly "Triage Log" |
| Wrong urgency classifications | Prompt needs tuning for this practice's email patterns | Update urgency rules in `triage_bot.py`, redeploy |
| Call forwarding not working | Client's phone system needs IT or vendor to configure | Get vendor on a call — this is a 15-minute fix with the right person |
| Client staff overriding drafts with wrong info | Training gap | 30-minute re-training call; update draft template if needed |

---

## Competitive Positioning — One Paragraph

> "There are two types of automation vendors in this market. The first type sells you a tool and disappears — you're on your own when it breaks at 7pm on a Friday. The second type is a managed service partner who owns the system, monitors it, and proactively improves it as the technology evolves. Clairvance is the second type. The $1,500/month you pay isn't for software. It's for a system that runs without you thinking about it, a monthly report that shows you what it's doing, and a partner who brings you improvements before you know you need them."

---

*Clairvance | AI Automation Agency | Confidential — Internal Use Only*
*Practice Communication Suite Playbook v1.0*
