import { useState, useEffect, useRef } from "react";

// ─── CONSTANTS ────────────────────────────────────────────────────────────────
const GOLD = "#C9A84C";
const MONO = "'JetBrains Mono','Courier New',monospace";
const SERIF = "'Georgia','Times New Roman',serif";
const SC = { green:"#4CC980", amber:"#C9A84C", red:"#C94C4C", blue:"#4CA8C9", purple:"#9B4CC9" };

// ─── SAMPLE RESPONSES — baked in for every quick prompt ──────────────────────
const SAMPLES = {
  CEO: {
    "Give me the morning brief":
`Good morning. Bolias Bank opens the day in sound operational health.

Reserve Ratio: 107.3% — 230 bps above the 105% mint floor. Mint status is ACTIVE. Oracle freshness: 4 minutes. BOL-AED supply stands at AED 247.5M.

Three items require my attention today:
  • Travel Rule hold — AED 18,500 outbound to Emirates Digital Exchange. VASP unverified. AI CCO has 18-hour TTL to resolve.
  • Three governance approvals pending: two treasury rebalancing proposals, one compliance policy amendment.
  • VaR utilisation at 68% — elevated but within the 85% limit. AI CRO is monitoring.

No circuit breakers active. LCR 2.61x. System uptime 99.97%.

[LOGGED TO AUDIT TRAIL]`,

    "What is our reserve health today?":
`Reserve health is GREEN with comfortable margin above threshold.

Current reserve ratio: 107.3% against a 105% mint floor. Adjusted reserves: AED 265.2M backing AED 247.5M in circulating BOL-AED.

Asset composition by liquidity tier:
  • T+0  Cash equivalents:       AED  53.0M  (20%)
  • T+1  UAE Sovereign Bills:    AED 159.0M  (60%)
  • T+7  Corporate Sukuk:        AED  53.2M  (20%)

Stress-adjusted ratio under a 30% redemption scenario: 101.6% — above the 100% emergency floor. Net reserve yield: 4.1% annualised.

No reserve concerns at this time. [LOGGED TO AUDIT TRAIL]`,

    "Any decisions pending my approval?":
`Three items are queued for CEO approval:

1. TR-2026-14 — Treasury Rebalancing. CFO requests shifting 5% from Corporate Sukuk to UAE T-Bills to improve T+1 liquidity. Risk: LOW. Recommendation: APPROVE.

2. CP-2026-07 — Compliance Policy Amendment. CCO proposes lowering Travel Rule threshold from AED 3,500 to AED 2,000 to align with anticipated CBUAE guidance. Impact: ~12 additional IVMS101 screenings per day. Recommendation: APPROVE pending legal review.

3. ERA-001 — Emergency Reserve Draw Pre-Authorisation. Standing authority for repo facility drawdown up to AED 25M if reserve ratio falls below 105%. Recommendation: RENEW quarterly.

Items 1 and 2 are subject to a 48-hour timelock. All three are within normal governance parameters.

[LOGGED TO AUDIT TRAIL]`,

    "Why did we pause minting recently?":
`Minting was paused for 4 hours and 9 minutes on Monday due to an oracle freshness breach.

At 14:32 GST, the ReserveOracle timestamp exceeded the 30-minute freshness threshold after a connectivity interruption with the custodian data feed. Our MintController applies an automatic precautionary halt when oracle data ages beyond threshold — this is functioning exactly as designed.

The custodian feed was restored at 18:41 GST. Oracle freshness confirmed, reserve ratio validated at 107.1%, and minting resumed automatically. No BOL-AED was minted during the pause window. Zero client impact — no mint requests were queued at the time.

AI COO has raised a corrective action ticket for a redundant oracle feed from a secondary custodian. ETA: Week 7 sprint.

[LOGGED TO AUDIT TRAIL]`,
  },

  CFO: {
    "What's our adjusted reserve ratio?":
`Adjusted reserve ratio: 107.3% as of this morning's oracle attestation.

AED 265.2M in adjusted reserves backing AED 247.5M in circulating BOL-AED supply.

Portfolio by liquidity:
  • T+0  Cash (20%):              AED  53.0M  — overnight deposits
  • T+1  UAE Sovereign Bills (60%): AED 159.0M  — short-duration HQLA
  • T+7  Corporate Sukuk (20%):   AED  53.2M  — rated BBB+ or above

LCR stands at 2.61x against our 1.25x regulatory floor. Net yield: 4.1% annualised. No margin calls or collateral top-ups outstanding.

The ratio is comfortably above both the 105% mint floor and our internal 107% target band. [TREASURY LOG UPDATED]`,

    "Any reconciliation breaks today?":
`Reconciliation status: CLEAN. Zero breaks across all three reconciliation layers.

Daily reconciliation completed at 06:00 GST:
  • Bank ledger ↔ Internal double-entry ledger:     MATCHED  AED 247,512,480.00
  • Internal ledger ↔ On-chain BOL-AED supply:      MATCHED  247,512,480 tokens
  • Reserve attestation ↔ Custodian statement:      MATCHED  AED 265,248,315.00

Yesterday's payout reconciliation also clean — 7 redemption settlements processed, all confirmed T+1. No suspense items. No unmatched entries.

Next full reconciliation cycle: 06:00 GST tomorrow. Standing instruction: escalate any break above AED 10,000 to CFO immediately. [TREASURY LOG UPDATED]`,

    "Payout queue status?":
`Three payouts pending in the redemption queue, totalling AED 2.1M.

  PAYOUT-2026-0891   AED 850,000   Institutional (Tier 4)   KYC: VERIFIED   PROCESSING     ETA T+1
  PAYOUT-2026-0892   AED 750,000   Corporate (Tier 3)        KYC: VERIFIED   AWAITING BANK  ETA T+1
  PAYOUT-2026-0893   AED 500,000   Institutional (Tier 4)   KYC: VERIFIED   QUEUED         ETA T+2

All three are within normal parameters. No compliance flags. T+0 cash available: AED 53M — sufficient to cover the full queue without liquidating sovereign bills.

[TREASURY LOG UPDATED]`,

    "Reserve yield performance?":
`Net reserve yield: 4.1% annualised on AED 265.2M in adjusted reserves.

Performance by asset class:
  • UAE Sovereign Bills  (60%, AED 159M):  4.35%  — T+1 liquid, high quality
  • Corporate Sukuk      (20%, AED 53.2M): 5.20%  — higher yield, T+7, BBB+ rated
  • Cash equivalents     (20%, AED 53M):   2.80%  — overnight deposit, relationship banks

Blended gross yield: 4.41%. Net of custody and transaction costs: 4.1%.

Annualised reserve yield income at current supply: approximately AED 10.2M. This is the primary revenue pillar of Bolias Bank's business model at AED 247.5M supply. [TREASURY LOG UPDATED]`,
  },

  CRO: {
    "Are we within reserve ratio limits?":
`All reserve ratio limits are observed with adequate margin. Risk posture: MODERATE-GREEN.

Reserve ratio thresholds and current status:
  • 107.3%  Current level                        ← WE ARE HERE
  • 105.0%  Mint halt circuit breaker            NOT triggered ✓
  • 103.0%  Redemption fee escalation            NOT triggered ✓
  • 100.0%  Emergency governance session         NOT triggered ✓
  •  97.0%  Regulatory notification required     NOT triggered ✓

Stress-adjusted ratio (30% 7-day outflow): 101.6% — above the 100% emergency floor. T+0 and T+1 HQLA of AED 212M covers 85.7% of circulating supply in an extreme scenario.

No reserve risk concerns at this time. [RISK POSTURE UPDATED]`,

    "What's our VaR utilization?":
`VaR utilisation: 68% of the 85% daily limit. Trending upward — monitoring closely.

Open interest: AED 142M across 47 active positions. Largest single exposure: AED 18.2M (Institutional Tier 4, BTC/BOL-AED, net long). Portfolio delta: +0.34.

Week-on-week movement: +7 percentage points (61% → 68%). This trajectory is the primary risk monitor item today.

Escalation thresholds:
  • 72%  Internal watch — review position concentrations
  • 75%  Recommend reducing Tier 3 leverage limits
  • 80%  Auto-notify CEO, throttle new position opens

No circuit breakers active. Liquidation engine live, monitoring all margin accounts in real time.

[RISK POSTURE UPDATED]`,

    "Any stress triggers active?":
`No stress triggers active. All five circuit breakers are GREEN.

  Reserve ratio circuit breaker:        INACTIVE   107.3%  (floor 105%)   ✓
  VaR circuit breaker:                  INACTIVE   68%     (limit 85%)    ✓
  Oracle freshness circuit breaker:     INACTIVE   4 mins  (limit 30min)  ✓
  Liquidity (LCR) circuit breaker:      INACTIVE   2.61x   (floor 1.25x)  ✓
  Position concentration circuit bkr:  INACTIVE   12.8%   (limit 20%)    ✓

One item on watch: VaR utilisation increased 7% week-on-week. Not a trigger, but I have set an internal alert at 72% for position concentration review. No action required at this time.

Overall risk posture remains MODERATE-GREEN. [RISK POSTURE UPDATED]`,

    "Simulate a 30% redemption event":
`Stress simulation: 30% redemption over 7 calendar days.

Assumptions: AED 74.25M redeemed uniformly (AED 10.6M/day).

Liquidity waterfall:
  Day 1–2   T+0 cash (AED 53M)               COVERED — cash alone absorbs 5 days
  Day 3–5   T+1 Sovereign Bills (AED 159M)   COVERED — liquidated as needed
  Day 6–7   T+7 Sukuk buffer (AED 53.2M)     AVAILABLE — not required in this scenario

Post-stress outcomes:
  • Reserve ratio:          101.6%   (above 100% emergency floor ✓)
  • LCR:                      1.41x  (above 1.25x floor ✓)
  • Mint status at Day 3:   HALTED automatically (RR crosses 105%)
  • Redemption fee at D3:   0.5% → 1.5%
  • Repo facility available: AED 25M pre-authorised

Assessment: Bolias Bank can withstand a 30% redemption event without breaching any hard limits. The 80% T+0/T+1 liquidity weighting is purpose-built for this scenario.

[RISK POSTURE UPDATED]`,
  },

  COO: {
    "What's our delivery RAG status?":
`MVP delivery status — Week 6 of 8:

  Smart Contracts   ✅ GREEN   All contracts deployed on testnet and passing Foundry tests
  Backend Services  ✅ GREEN   Auth, compliance, treasury, mint/burn orchestrator, audit service live
  Admin Panel       ✅ GREEN   KYC queue, freeze address, reserve dashboard functional
  Web App           🟡 AMBER  80% complete — governance UI in progress, on track for Week 7
  AI Executive Suite 🟡 AMBER  5 agents wired, tool connectors in progress, Policy Guard pending
  Mobile App        🔴 RED    Not started — scoped for Week 7, React Native dev starts Monday

No incidents this week. SLA: 99.97% uptime. KYC review queue: 7 pending.
Demo date: Week 8 — on track, no slippage.

[OPS LOG UPDATED]`,

    "What's blocking the mobile launch?":
`Mobile app has two blockers — both resolvable before Week 7 start.

Blocker 1 — Dev resource: FS Dev 2 completes admin panel work this Friday. Mobile scaffold starts Monday Week 7. No new hire needed.

Blocker 2 — Wallet SDK compatibility: React Native wrapper requires Node 18+. Current mobile CI image is on Node 16. DevOps is upgrading — ETA end of this week.

Non-blockers being tracked:
  • Apple TestFlight provisioning: In process, 3–5 day turnaround, requested today
  • FCM + APNs push configuration: 1-day task, scheduled Week 7 Day 1

Timeline: Wallet connect + mint/redeem screens deliverable by Week 7 Day 3. Full demo-ready build: Week 8. No slip to demo date anticipated.

[OPS LOG UPDATED]`,

    "Any operational incidents today?":
`Zero operational incidents today. All services nominal.

  API Gateway            OPERATIONAL   p99 latency: 84ms
  Compliance Service     OPERATIONAL   KYC queue processing normally
  Mint/Burn Orchestrator OPERATIONAL   Last transaction: 7 mins ago
  Audit Service          OPERATIONAL   All events logging, daily hash anchored
  ReserveOracle          OPERATIONAL   Last attestation: 4 mins ago
  AI Agent Service       OPERATIONAL   All 5 agents responding
  Block Explorer         OPERATIONAL   Testnet producing blocks every 2s

Last incident: Monday 14:32 GST — oracle feed delay (resolved 18:41, duration 4h09m, zero client impact). Post-incident review complete. Redundant oracle feed on roadmap for Week 7.

[OPS LOG UPDATED]`,

    "KYC queue status?":
`KYC review queue: 7 pending applications across three client tiers.

Tier 1 — Retail (AED <50K limit):
  KYC-2026-0441   Individual, UAE national, docs received 2h ago        AWAITING REVIEW
  KYC-2026-0442   Individual, GCC resident, Emirates ID pending          PENDING DOCUMENT
  KYC-2026-0443   Individual, UK national, address proof pending         PENDING DOCUMENT
  KYC-2026-0444   Individual, UAE national, all docs complete            READY — APPROVE

Tier 3 — Corporate (AED <5M limit):
  KYC-2026-0445   LLC, UAE registered, UBO declaration pending           PENDING DOCUMENT
  KYC-2026-0446   LLC, ADGM registered, full docs received               READY — APPROVE

Tier 4 — Institutional (AED >5M):
  KYC-2026-0447   Regulated UAE bank, CBUAE licence verified             READY — EXPEDITE

Recommendation: Approve KYC-0444, KYC-0446, KYC-0447 today. Three others awaiting client-side submissions.

[OPS LOG UPDATED]`,
  },

  CCO: {
    "Why was this withdrawal held?":
`Travel Rule hold active on outbound transfer REF-TR-2026-0091.

Transaction details:
  Amount:     AED 18,500 (above AED 3,500 Travel Rule threshold)
  Direction:  Outbound — Bolias Bank → Emirates Digital Exchange
  Client:     ACC-7741 (Tier 3, KYC verified, no prior flags)
  Hold time:  Today 09:14 GST
  TTL:        18 hours remaining

Reason: Emirates Digital Exchange is a registered VASP but has not been onboarded into our TRISA network. We cannot transmit IVMS101 beneficiary/originator data automatically. Manual IVMS101 data exchange with their compliance team is required before release.

No AML flags on this transaction. Client due diligence is current. This is a VASP onboarding gap — not a suspicious activity matter.

Recommended action: Contact Emirates Digital Exchange compliance desk today. If confirmed within TTL, release. If no response in 18 hours, return funds to client with written explanation.

[COMPLIANCE LOG UPDATED]`,

    "Which customers need EDD?":
`Enhanced Due Diligence required for 3 customers, all flagged in the past 7 days.

EDD-001 — ACC-8812 (Corporate, Tier 3):
  Trigger: Transaction volume +340% over 30-day baseline. AED 2.1M minted in 10 days vs AED 490K prior month.
  Action: Issue EDD questionnaire. Suspend minting above AED 200K until resolved. Deadline: 14 days.

EDD-002 — ACC-9104 (Individual, Tier 2):
  Trigger: Three cash deposits at separate UAE banks on the same day, totalling AED 48,000. Potential structuring indicator.
  Action: Request 90-day bank statements. Escalate to MLRO review. Deadline: 7 days.

EDD-003 — ACC-7230 (Corporate, Tier 3):
  Trigger: Beneficial ownership change — new UBO is a Politically Exposed Person (non-sanctioned).
  Action: Enhanced PEP screening completed — CLEAR. Monitoring frequency increased to weekly. Source of wealth declaration required. Deadline: 30 days.

[COMPLIANCE LOG UPDATED]`,

    "Travel Rule status today?":
`Travel Rule compliance status: 1 active hold. All other transactions compliant.

Today's activity:
  Total transactions screened:              34
  Below threshold (< AED 3,500):            31   No Travel Rule obligation
  Above threshold — IVMS101 sent:            2   Compliant
  Above threshold — HOLD (VASP gap):         1   REF-TR-2026-0091 ← active

TRISA network status:
  Onboarded VASP partners:    12
  Pending onboarding:          3  (Emirates Digital Exchange, BitOasis, Crypto.com)
  Emirates Digital Exchange onboarding ETA: 5 business days

Sanctions screening: ALL 34 transactions cleared against OFAC, UN, EU, and UAE sanctions lists.

Policy: v2.3.1 — current. Next review due: 60 days.

[COMPLIANCE LOG UPDATED]`,

    "Any sanctions screening alerts?":
`Sanctions screening status: ALL CLEAR. Zero hits across all active accounts and today's transactions.

Coverage:
  Active accounts screened daily:     847
  Today's transactions screened:       34
  Sanctions lists: OFAC SDN, UN Consolidated, EU Asset Freeze, UAE Local Terrorist List, FATF High-Risk Jurisdictions
  Last database refresh:               6 hours ago

Jurisdiction flags: ZERO. No accounts from FATF high-risk or monitored jurisdictions.

Adverse media: 0 new hits from overnight monitoring. 1 historical false positive on ACC-3341 (corporate name match — resolved and documented).

PEP accounts: 1 active (ACC-7230, non-sanctioned, enhanced weekly monitoring — see EDD-003).

Next scheduled screening run: 6 hours. Continuous real-time screening on all transactions above AED 500.

[COMPLIANCE LOG UPDATED]`,
  },
};

// ─── AGENTS ───────────────────────────────────────────────────────────────────
const AGENTS = {
  CEO: { id:"CEO", title:"AI CEO", subtitle:"Strategy & Governance", color:GOLD, bg:"rgba(201,168,76,0.07)", border:"rgba(201,168,76,0.22)", icon:"◈",
    systemPrompt:`You are the AI CEO of Bolias Bank (SRHFI). Live data: Reserve Ratio 107.3%, VaR 68%, Approvals pending 3, Travel Rule hold 1 (AED 18,500 — Emirates Digital Exchange), Oracle 4 min, BOL-AED Supply 247.5M AED, Mint ACTIVE, LCR 2.61x, Tier 1 Capital AED 100M. Speak with authority and institutional gravitas. Concise, data-driven, action-oriented. Sign off with [LOGGED TO AUDIT TRAIL].`,
    quickPrompts:["Give me the morning brief","What is our reserve health today?","Any decisions pending my approval?","Why did we pause minting recently?"] },
  CFO: { id:"CFO", title:"AI CFO", subtitle:"Treasury & Capital", color:"#4CA8C9", bg:"rgba(76,168,201,0.07)", border:"rgba(76,168,201,0.22)", icon:"◉",
    systemPrompt:`You are the AI CFO of Bolias Bank. Data: BOL-AED 247.5M, Reserves 265.2M AED (107.3%), T+0 cash AED 53M, T+1 Sovereign Bills AED 159M, T+7 Sukuk AED 53.2M, LCR 2.61x, Payout Queue 3 pending AED 2.1M, Reconciliation CLEAN, Net yield 4.1%. Financial precision. Sign off with [TREASURY LOG UPDATED].`,
    quickPrompts:["What's our adjusted reserve ratio?","Any reconciliation breaks today?","Payout queue status?","Reserve yield performance?"] },
  CRO: { id:"CRO", title:"AI CRO", subtitle:"Risk & Capital Adequacy", color:"#C94C4C", bg:"rgba(201,76,76,0.07)", border:"rgba(201,76,76,0.22)", icon:"◎",
    systemPrompt:`You are the AI CRO of Bolias Bank. Data: RR 107.3% (floor 105%), VaR 68% (limit 85%), OI AED 142M, Stress ratio 101.6%, LCR 2.61x, no circuit breakers active, oracle 4 min, max leverage Tier 4 25x, Risk posture MODERATE-GREEN. Analytical precision, proactively surface risks. Sign off with [RISK POSTURE UPDATED].`,
    quickPrompts:["Are we within reserve ratio limits?","What's our VaR utilization?","Any stress triggers active?","Simulate a 30% redemption event"] },
  COO: { id:"COO", title:"AI COO", subtitle:"Operations & Delivery", color:"#4CC980", bg:"rgba(76,201,128,0.07)", border:"rgba(76,201,128,0.22)", icon:"◇",
    systemPrompt:`You are the AI COO of Bolias Bank. Data: MVP Week 6/8, Smart Contracts GREEN, Backend GREEN, Admin Panel GREEN, Web App AMBER 80%, AI Suite AMBER, Mobile RED not started. Incidents 0, SLA 99.97%, KYC queue 7. Direct about blockers. Sign off with [OPS LOG UPDATED].`,
    quickPrompts:["What's our delivery RAG status?","What's blocking the mobile launch?","Any operational incidents today?","KYC queue status?"] },
  CCO: { id:"CCO", title:"AI CCO", subtitle:"Compliance & AML", color:"#9B4CC9", bg:"rgba(155,76,201,0.07)", border:"rgba(155,76,201,0.22)", icon:"◆",
    systemPrompt:`You are the AI CCO/MLRO of Bolias Bank. Data: Travel Rule holds 1 (AED 18,500 — Emirates Digital Exchange, VASP unverified, 18hr TTL), EDD required 3, KYC pending 7, Sanctions ALL CLEAR, Policy v2.3.1 current. Regulatory precision. Sign off with [COMPLIANCE LOG UPDATED].`,
    quickPrompts:["Why was this withdrawal held?","Which customers need EDD?","Travel Rule status today?","Any sanctions screening alerts?"] },
};

const METRICS = [
  { label:"Reserve Ratio", value:"107.3%", status:"green", sub:"Floor: 105%", detail:"230 bps above mint floor" },
  { label:"BOL-AED Supply", value:"247.5M", status:"blue", sub:"AED circulating", detail:"Backed 1:1 by AED reserves" },
  { label:"LCR", value:"2.61x", status:"green", sub:"Floor: 1.25x", detail:"Liquidity Coverage Ratio" },
  { label:"VaR Utilisation", value:"68%", status:"amber", sub:"Limit: 85%", detail:"+7% WoW — being monitored" },
  { label:"Mint Status", value:"ACTIVE", status:"green", sub:"Oracle: 4 min ago", detail:"MintController live" },
  { label:"Compliance", value:"1 HOLD", status:"amber", sub:"Travel Rule", detail:"AED 18,500 — VASP unverified" },
];

// ─── CUSTOMER JOURNEYS ────────────────────────────────────────────────────────
const JOURNEYS = {
  A: {
    id:"A", label:"AI CEO Daily Brief", color:GOLD, agentId:"CEO",
    desc:"Executive opens the command centre. All 5 AI agents aggregate overnight data and surface the daily brief, open decisions, and alerts.",
    trigger:"Give me the morning brief",
    steps:[
      { label:"Brief Requested",     note:"Executive opens Command Centre",                  type:"action" },
      { label:"Agents Polled",        note:"CEO, CFO, CRO, COO, CCO pull live data",          type:"system" },
      { label:"Data Aggregated",      note:"Reserve 107.3% · VaR 68% · 3 approvals pending", type:"data" },
      { label:"Brief Generated",      note:"AI CEO synthesises overnight position",            type:"ai" },
      { label:"Decisions Surfaced",   note:"3 governance approvals queued for CEO",           type:"action" },
      { label:"Logged to Audit Trail",note:"Brief hash anchored on-chain — Block 48,291",    type:"chain" },
    ],
  },
  B: {
    id:"B", label:"KYC → Mint BOL-AED", color:"#4CC980", agentId:"CCO",
    desc:"New institutional client completes KYC, deposits AED 50,000, and receives freshly minted BOL-AED directly to their wallet.",
    trigger:"A new client just passed KYC and deposited AED 50,000. What compliance checks run before we mint BOL-AED?",
    steps:[
      { label:"Client Registers",       note:"Name · Email · Jurisdiction",                      type:"action" },
      { label:"KYC Documents Uploaded", note:"Passport + proof of address submitted",            type:"action" },
      { label:"KYC Approved",           note:"AI CCO review — TIER 2 APPROVED",                 type:"ai" },
      { label:"AED 50,000 Deposited",   note:"Bank transfer received · Treasury confirms",       type:"data" },
      { label:"Compliance Check",        note:"ComplianceRegistry: PERMITTED · No sanctions hit", type:"system" },
      { label:"BOL-AED Minted",          note:"50,000 BOL-AED → wallet 0x7f3a...4c2b",           type:"chain" },
      { label:"Confirmed On-Chain",      note:"Txn 0xa4c2...8f01 · Block 48,294",                type:"chain" },
    ],
  },
  C: {
    id:"C", label:"Redeem → Fiat Payout", color:"#4CA8C9", agentId:"CFO",
    desc:"Client burns 25,000 BOL-AED. Treasury service creates a payout record, initiates bank transfer, and reconciles all three ledgers.",
    trigger:"A client wants to redeem 25,000 BOL-AED. Walk me through the payout process and reconciliation.",
    steps:[
      { label:"Redeem Requested",    note:"Client submits 25,000 BOL-AED redemption",      type:"action" },
      { label:"Compliance Cleared",  note:"Travel Rule: below threshold · CLEAR",           type:"system" },
      { label:"BOL-AED Burned",      note:"25,000 tokens burned · Txn 0xb3f1...2a9c",       type:"chain" },
      { label:"Payout Queued",       note:"PAYOUT-2026-0894 · AED 25,000",                  type:"system" },
      { label:"Bank Transfer Sent",  note:"SWIFT instruction issued · ETA T+1",             type:"action" },
      { label:"Reconciled",          note:"Ledger ↔ Chain ↔ Bank — MATCHED",                type:"data" },
    ],
  },
  D: {
    id:"D", label:"Travel Rule Hold", color:"#9B4CC9", agentId:"CCO",
    desc:"AED 18,500 outbound transfer is automatically held. Emirates Digital Exchange is not in the TRISA network. AI CCO surfaces the hold and recommends action.",
    trigger:"Why was this withdrawal held?",
    steps:[
      { label:"Transfer Initiated",   note:"AED 18,500 outbound · above AED 3,500 threshold", type:"action" },
      { label:"VASP Screened",         note:"Emirates Digital Exchange · not in TRISA network", type:"system" },
      { label:"Hold Auto-Placed",      note:"IVMS101 cannot be sent automatically",            type:"system" },
      { label:"AI CCO Briefed",        note:"Hold logged · TTL 18 hrs · recommendation drafted",type:"ai" },
      { label:"VASP Contacted",        note:"Manual IVMS101 data exchange requested",          type:"action" },
      { label:"Hold Released",         note:"Transfer cleared after manual verification",       type:"chain" },
    ],
  },
  E: {
    id:"E", label:"Reserve Stress Event", color:"#C94C4C", agentId:"CRO",
    desc:"Oracle detects reserve ratio dropping to 103.1%. MintController halts automatically. AI CRO fires a stress brief. AI CEO notified. Repo facility drawn to recover.",
    trigger:"Simulate a 30% redemption event",
    steps:[
      { label:"Oracle Detects Drop",    note:"Reserve ratio: 107.3% → 103.1%",               type:"data" },
      { label:"Mint Auto-Halted",       note:"MintController: RR < 105% — HALT TRIGGERED",   type:"system" },
      { label:"Fees Escalated",         note:"Redemption fee: 0.5% → 1.5% (auto)",            type:"system" },
      { label:"AI CRO Brief Fires",     note:"Stress analysis · 7-day liquidity waterfall",   type:"ai" },
      { label:"AI CEO Alerted",         note:"ATTENTION REQUIRED · cockpit alert active",      type:"ai" },
      { label:"Repo Facility Drawn",    note:"AED 25M pre-authorised repo initiated",          type:"action" },
      { label:"Mint Resumed",           note:"Ratio 107.2% · MintController: ACTIVE",          type:"chain" },
    ],
  },
  F: {
    id:"F", label:"Governance Proposal", color:GOLD, agentId:"CEO",
    desc:"Treasury rebalancing proposal TR-2026-14 submitted on-chain. AI CEO classifies risk. 48-hour timelock starts. Security Council reviews. Proposal executes automatically.",
    trigger:"Any decisions pending my approval?",
    steps:[
      { label:"Proposal Submitted",   note:"TR-2026-14: Shift 5% Sukuk → T-Bills",           type:"action" },
      { label:"AI CEO Classifies",     note:"Risk: LOW · Standard treasury rebalancing",       type:"ai" },
      { label:"Timelock Started",      note:"48-hour delay · Security Council window open",    type:"chain" },
      { label:"Council Reviews",       note:"3 of 5 multisig signatures required to veto",    type:"action" },
      { label:"Timelock Expires",      note:"No veto received · Executing automatically",      type:"system" },
      { label:"Anchored On-Chain",     note:"Governance event logged · Block 48,311",          type:"chain" },
    ],
  },
};

const STEP_COLORS = { action:"#4CA8C9", system:"#4CC980", data:GOLD, ai:"#9B4CC9", chain:"#C9A84C" };
const STEP_LABELS = { action:"ACTION", system:"SYSTEM", data:"DATA", ai:"AI", chain:"ON-CHAIN" };

// ─── ROOT APP ─────────────────────────────────────────────────────────────────
export default function App() {
  const [view, setView]           = useState("cockpit");
  const [activeAgent, setActiveAgent] = useState("CEO");
  const [conversations, setConversations] = useState(
    Object.fromEntries(Object.keys(AGENTS).map(k => [k, []]))
  );
  const [input, setInput]         = useState("");
  const [loading, setLoading]     = useState(false);
  const [time, setTime]           = useState(new Date());
  const [activeJourney, setActiveJourney] = useState(null);
  const [journeyProgress, setJourneyProgress] = useState({});
  const [journeyRunning, setJourneyRunning]   = useState({});
  const chatEndRef = useRef(null);

  useEffect(() => { const t = setInterval(() => setTime(new Date()), 1000); return () => clearInterval(t); }, []);
  useEffect(() => { chatEndRef.current?.scrollIntoView({ behavior:"smooth" }); }, [conversations, loading]);

  // ── send a message to a specific agent ──
  async function sendMessage(text, agentKey = activeAgent) {
    if (!text.trim() || loading) return;
    const ag = AGENTS[agentKey];
    const prev = conversations[agentKey];
    const updated = [...prev, { role:"user", content:text }];
    setConversations(p => ({ ...p, [agentKey]: updated }));
    setInput("");
    setLoading(true);
    setActiveAgent(agentKey);
    if (view !== "agent") setView("agent");

    // use sample if available
    const sample = SAMPLES[agentKey]?.[text];
    if (sample) {
      await new Promise(r => setTimeout(r, 700 + Math.random() * 500));
      setConversations(p => ({ ...p, [agentKey]: [...updated, { role:"assistant", content:sample }] }));
      setLoading(false);
      return;
    }
    // fallback to live API
    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method:"POST",
        headers:{ "Content-Type":"application/json" },
        body: JSON.stringify({
          model:"claude-sonnet-4-20250514", max_tokens:1000,
          system: ag.systemPrompt,
          messages: updated.map(m => ({ role:m.role, content:m.content })),
        }),
      });
      const data = await res.json();
      const reply = data.content?.[0]?.text || "Unable to process request.";
      setConversations(p => ({ ...p, [agentKey]: [...updated, { role:"assistant", content:reply }] }));
    } catch {
      setConversations(p => ({ ...p, [agentKey]: [...updated, { role:"assistant", content:"Connection error. Please retry." }] }));
    }
    setLoading(false);
  }

  // ── run a journey (animate steps then fire agent query) ──
  function runJourney(jId) {
    const journey = JOURNEYS[jId];
    setActiveJourney(jId);
    setView("journeys");
    setJourneyProgress(p => ({ ...p, [jId]: -1 }));
    setJourneyRunning(p => ({ ...p, [jId]: true }));

    journey.steps.forEach((_, i) => {
      setTimeout(() => {
        setJourneyProgress(p => ({ ...p, [jId]: i }));
        if (i === journey.steps.length - 1) {
          setJourneyRunning(p => ({ ...p, [jId]: false }));
          // fire agent query after steps complete
          setTimeout(() => sendMessage(journey.trigger, journey.agentId), 400);
        }
      }, i * 750);
    });
  }

  const agent = AGENTS[activeAgent];

  return (
    <div style={{ height:"100vh", display:"flex", flexDirection:"column", background:"#080C12", color:"#E8E4D9", fontFamily:SERIF, overflow:"hidden" }}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500&display=swap');
        * { box-sizing: border-box; }
        @keyframes pulse   { 0%,100%{opacity:0.3;transform:scale(0.8)} 50%{opacity:1;transform:scale(1)} }
        @keyframes fadeUp  { from{opacity:0;transform:translateY(5px)} to{opacity:1;transform:translateY(0)} }
        @keyframes blink   { 0%,100%{opacity:0.3} 50%{opacity:1} }
        @keyframes stepIn  { from{opacity:0;transform:translateX(-6px)} to{opacity:1;transform:translateX(0)} }
        .msg-anim { animation: fadeUp 0.2s ease forwards; }
        .step-anim { animation: stepIn 0.3s ease forwards; }
        ::-webkit-scrollbar { width:3px; }
        ::-webkit-scrollbar-thumb { background:rgba(201,168,76,0.2); border-radius:2px; }
        input { font-family: ${SERIF}; }
        button { font-family: ${SERIF}; }
      `}</style>

      {/* ═══ TOP BAR ═══ */}
      <div style={{ height:52, borderBottom:"1px solid rgba(201,168,76,0.18)", padding:"0 24px", display:"flex", alignItems:"center", justifyContent:"space-between", background:"rgba(201,168,76,0.025)", flexShrink:0 }}>
        <div style={{ display:"flex", alignItems:"center", gap:14 }}>
          <div style={{ width:30, height:30, border:`1px solid ${GOLD}`, display:"flex", alignItems:"center", justifyContent:"center", fontSize:14, color:GOLD }}>◈</div>
          <div>
            <div style={{ fontSize:12, letterSpacing:"0.22em", color:GOLD, textTransform:"uppercase" }}>Bolias Bank</div>
            <div style={{ fontSize:9, color:"rgba(232,228,217,0.3)", letterSpacing:"0.15em", textTransform:"uppercase", fontFamily:MONO }}>AI Executive Suite · Management Demo</div>
          </div>
        </div>
        <div style={{ display:"flex", gap:6 }}>
          {[["cockpit","Command Centre"],["agent","Agent Chat"],["journeys","Customer Journeys"]].map(([v,lbl]) => (
            <button key={v} onClick={() => setView(v)} style={{ padding:"5px 14px", fontSize:9, letterSpacing:"0.14em", textTransform:"uppercase", border:"1px solid", cursor:"pointer", background:"transparent", transition:"all 0.15s", borderColor: view===v ? GOLD : "rgba(232,228,217,0.12)", color: view===v ? GOLD : "rgba(232,228,217,0.3)", fontFamily:MONO }}>{lbl}</button>
          ))}
        </div>
        <div style={{ fontSize:9, color:"rgba(232,228,217,0.25)", fontFamily:MONO }}>{time.toLocaleTimeString("en-AE",{hour12:false})} · Dubai, UAE</div>
      </div>

      {/* ═══ VIEW SWITCHER ═══ */}
      {view === "cockpit"  && <CockpitView  metrics={METRICS} agents={AGENTS} journeys={JOURNEYS} onSelectAgent={id => { setActiveAgent(id); setView("agent"); }} onRunJourney={runJourney} />}
      {view === "agent"    && <AgentView    agent={agent} agents={AGENTS} msgs={conversations[activeAgent]} loading={loading} input={input} setInput={setInput} sendMessage={t => sendMessage(t, activeAgent)} activeAgent={activeAgent} setActiveAgent={setActiveAgent} chatEndRef={chatEndRef} />}
      {view === "journeys" && <JourneysView journeys={JOURNEYS} agents={AGENTS} activeJourney={activeJourney} setActiveJourney={setActiveJourney} journeyProgress={journeyProgress} journeyRunning={journeyRunning} onRunJourney={runJourney} goToAgent={id => { setActiveAgent(id); setView("agent"); }} />}
    </div>
  );
}

// ═══════════════════════════════════════════════════════════════════════════════
// COCKPIT VIEW
// ═══════════════════════════════════════════════════════════════════════════════
function CockpitView({ metrics, agents, journeys, onSelectAgent, onRunJourney }) {
  return (
    <div style={{ flex:1, overflowY:"auto", padding:"28px 32px" }}>
      {/* Header */}
      <div style={{ marginBottom:28, display:"flex", alignItems:"flex-end", justifyContent:"space-between" }}>
        <div style={{ borderLeft:`2px solid ${GOLD}`, paddingLeft:18 }}>
          <div style={{ fontSize:9, letterSpacing:"0.25em", color:GOLD, textTransform:"uppercase", marginBottom:4, fontFamily:MONO }}>Executive Command Centre</div>
          <div style={{ fontSize:26, fontWeight:400, letterSpacing:"0.02em" }}>AI Governance Dashboard</div>
          <div style={{ fontSize:12, color:"rgba(232,228,217,0.35)", marginTop:4 }}>Five AI executives · AED 247.5M BOL-AED · ZK Testnet Active</div>
        </div>
        <div style={{ display:"flex", alignItems:"center", gap:7, padding:"5px 12px", border:"1px solid rgba(76,201,128,0.3)", background:"rgba(76,201,128,0.05)" }}>
          <div style={{ width:5, height:5, borderRadius:"50%", background:"#4CC980", animation:"blink 2s infinite" }} />
          <span style={{ fontSize:8, letterSpacing:"0.18em", textTransform:"uppercase", color:"#4CC980", fontFamily:MONO }}>All Systems Operational</span>
        </div>
      </div>

      {/* Metrics Strip */}
      <div style={{ display:"grid", gridTemplateColumns:"repeat(6,1fr)", border:"1px solid rgba(201,168,76,0.12)", marginBottom:28, background:"rgba(201,168,76,0.02)" }}>
        {metrics.map((m,i) => (
          <div key={i} style={{ padding:"14px 12px", borderRight:i<5?"1px solid rgba(201,168,76,0.08)":"none" }}>
            <div style={{ fontSize:8, letterSpacing:"0.18em", textTransform:"uppercase", color:"rgba(232,228,217,0.28)", marginBottom:6, fontFamily:MONO }}>{m.label}</div>
            <div style={{ fontSize:20, fontFamily:MONO, color:SC[m.status], fontWeight:500 }}>{m.value}</div>
            <div style={{ fontSize:8, color:"rgba(232,228,217,0.22)", marginTop:3, fontFamily:MONO }}>{m.sub}</div>
            <div style={{ fontSize:8, color:"rgba(232,228,217,0.18)", marginTop:2, lineHeight:1.4 }}>{m.detail}</div>
          </div>
        ))}
      </div>

      {/* Agent Cards */}
      <div style={{ fontSize:8, letterSpacing:"0.2em", textTransform:"uppercase", color:"rgba(232,228,217,0.2)", marginBottom:10, fontFamily:MONO }}>AI Executive Suite — click any agent to open chat</div>
      <div style={{ display:"grid", gridTemplateColumns:"repeat(5,1fr)", gap:10, marginBottom:28 }}>
        {Object.values(agents).map(a => (
          <button key={a.id} onClick={() => onSelectAgent(a.id)} style={{ background:a.bg, border:`1px solid ${a.border}`, padding:"20px 16px", cursor:"pointer", textAlign:"left", fontFamily:SERIF, display:"flex", flexDirection:"column", gap:10, transition:"all 0.18s" }}
            onMouseEnter={e => e.currentTarget.style.borderColor = a.color}
            onMouseLeave={e => e.currentTarget.style.borderColor = a.border}>
            <div style={{ fontSize:26, color:a.color }}>{a.icon}</div>
            <div>
              <div style={{ fontSize:13, color:a.color, letterSpacing:"0.04em" }}>{a.title}</div>
              <div style={{ fontSize:8, color:"rgba(232,228,217,0.28)", letterSpacing:"0.12em", textTransform:"uppercase", marginTop:3, fontFamily:MONO }}>{a.subtitle}</div>
            </div>
            <div style={{ fontSize:10, color:"rgba(232,228,217,0.38)", lineHeight:1.55 }}>"{a.quickPrompts[0]}"</div>
            <div style={{ marginTop:"auto", fontSize:8, letterSpacing:"0.16em", textTransform:"uppercase", color:a.color, borderTop:`1px solid ${a.border}`, paddingTop:10, fontFamily:MONO }}>Open Chat →</div>
          </button>
        ))}
      </div>

      {/* Journey Cards */}
      <div style={{ fontSize:8, letterSpacing:"0.2em", textTransform:"uppercase", color:"rgba(232,228,217,0.2)", marginBottom:10, fontFamily:MONO }}>Customer Journeys — click to run interactive demo</div>
      <div style={{ display:"grid", gridTemplateColumns:"repeat(3,1fr)", gap:10 }}>
        {Object.values(journeys).map(j => (
          <button key={j.id} onClick={() => onRunJourney(j.id)} style={{ background:"rgba(255,255,255,0.02)", border:"1px solid rgba(255,255,255,0.07)", padding:"14px 16px", cursor:"pointer", textAlign:"left", fontFamily:SERIF, transition:"border-color 0.18s", display:"flex", gap:12, alignItems:"flex-start" }}
            onMouseEnter={e => e.currentTarget.style.borderColor = "rgba(255,255,255,0.16)"}
            onMouseLeave={e => e.currentTarget.style.borderColor = "rgba(255,255,255,0.07)"}>
            <div style={{ width:26, height:26, border:`1px solid ${j.color}`, display:"flex", alignItems:"center", justifyContent:"center", fontSize:10, color:j.color, fontFamily:MONO, flexShrink:0, marginTop:1 }}>{j.id}</div>
            <div style={{ flex:1 }}>
              <div style={{ fontSize:12, color:"#E8E4D9", marginBottom:3 }}>{j.label}</div>
              <div style={{ fontSize:10, color:"rgba(232,228,217,0.32)", lineHeight:1.5 }}>{j.desc}</div>
            </div>
            <div style={{ fontSize:8, letterSpacing:"0.14em", textTransform:"uppercase", color:j.color, fontFamily:MONO, flexShrink:0, marginTop:2 }}>Run →</div>
          </button>
        ))}
      </div>
    </div>
  );
}

// ═══════════════════════════════════════════════════════════════════════════════
// JOURNEYS VIEW
// ═══════════════════════════════════════════════════════════════════════════════
function JourneysView({ journeys, agents, activeJourney, setActiveJourney, journeyProgress, journeyRunning, onRunJourney, goToAgent }) {
  const j = activeJourney ? journeys[activeJourney] : null;
  const progress = activeJourney ? (journeyProgress[activeJourney] ?? -1) : -1;
  const running  = activeJourney ? !!journeyRunning[activeJourney] : false;

  return (
    <div style={{ flex:1, display:"flex", overflow:"hidden" }}>
      {/* Sidebar */}
      <div style={{ width:210, borderRight:"1px solid rgba(201,168,76,0.12)", flexShrink:0, padding:"16px 0", overflowY:"auto", background:"rgba(201,168,76,0.01)" }}>
        <div style={{ padding:"0 14px 12px", fontSize:8, letterSpacing:"0.18em", textTransform:"uppercase", color:"rgba(232,228,217,0.2)", fontFamily:MONO }}>6 Customer Journeys</div>
        {Object.values(journeys).map(jj => {
          const done = !journeyRunning[jj.id] && journeyProgress[jj.id] != null && journeyProgress[jj.id] >= jj.steps.length - 1;
          return (
            <button key={jj.id} onClick={() => { setActiveJourney(jj.id); if (!journeyRunning[jj.id]) onRunJourney(jj.id); }}
              style={{ width:"100%", padding:"11px 14px", textAlign:"left", cursor:"pointer", background: activeJourney===jj.id ? "rgba(255,255,255,0.04)" : "transparent", borderLeft:`2px solid ${activeJourney===jj.id ? jj.color : "transparent"}`, border:"none", borderLeft:`2px solid ${activeJourney===jj.id ? jj.color : "transparent"}`, fontFamily:SERIF, display:"flex", gap:10, alignItems:"center", transition:"all 0.15s" }}>
              <div style={{ width:22, height:22, border:`1px solid ${jj.color}`, display:"flex", alignItems:"center", justifyContent:"center", fontSize:9, color: done ? "#4CC980" : jj.color, fontFamily:MONO, flexShrink:0, background: done ? "rgba(76,201,128,0.1)" : "transparent" }}>{done ? "✓" : jj.id}</div>
              <div>
                <div style={{ fontSize:11, color: activeJourney===jj.id ? "#E8E4D9" : "rgba(232,228,217,0.45)" }}>{jj.label}</div>
                <div style={{ fontSize:8, color:"rgba(232,228,217,0.22)", fontFamily:MONO, textTransform:"uppercase", letterSpacing:"0.1em", marginTop:2 }}>AI {jj.agentId}</div>
              </div>
            </button>
          );
        })}
      </div>

      {/* Main Panel */}
      <div style={{ flex:1, overflowY:"auto", padding:"28px 32px" }}>
        {!j ? (
          <div style={{ display:"flex", flexDirection:"column", alignItems:"center", justifyContent:"center", height:"100%", gap:16, color:"rgba(232,228,217,0.25)" }}>
            <div style={{ fontSize:28 }}>◈</div>
            <div style={{ fontSize:13 }}>Select a journey from the sidebar to begin</div>
          </div>
        ) : (
          <>
            {/* Journey header */}
            <div style={{ display:"flex", alignItems:"flex-start", justifyContent:"space-between", marginBottom:28 }}>
              <div style={{ borderLeft:`2px solid ${j.color}`, paddingLeft:16 }}>
                <div style={{ fontSize:9, letterSpacing:"0.22em", color:j.color, textTransform:"uppercase", marginBottom:4, fontFamily:MONO }}>Journey {j.id} · AI {j.agentId}</div>
                <div style={{ fontSize:22, fontWeight:400 }}>{j.label}</div>
                <div style={{ fontSize:12, color:"rgba(232,228,217,0.38)", marginTop:5, maxWidth:520, lineHeight:1.6 }}>{j.desc}</div>
              </div>
              <div style={{ display:"flex", gap:8, flexShrink:0 }}>
                <button onClick={() => onRunJourney(j.id)} style={{ padding:"7px 16px", background:"transparent", border:`1px solid ${j.color}`, color:j.color, cursor:"pointer", fontSize:9, letterSpacing:"0.14em", textTransform:"uppercase", fontFamily:MONO }}>{running ? "Running..." : "Run Again"}</button>
                <button onClick={() => goToAgent(j.agentId)} style={{ padding:"7px 16px", background:"transparent", border:"1px solid rgba(232,228,217,0.14)", color:"rgba(232,228,217,0.45)", cursor:"pointer", fontSize:9, letterSpacing:"0.14em", textTransform:"uppercase", fontFamily:MONO }}>View Agent Response →</button>
              </div>
            </div>

            {/* Steps */}
            <div style={{ marginBottom:28 }}>
              <div style={{ fontSize:8, letterSpacing:"0.18em", textTransform:"uppercase", color:"rgba(232,228,217,0.2)", marginBottom:16, fontFamily:MONO }}>Journey Steps</div>
              <div style={{ display:"flex", flexDirection:"column" }}>
                {j.steps.map((step, i) => {
                  const done   = i <= progress;
                  const active = i === progress && running;
                  const col    = STEP_COLORS[step.type] || GOLD;
                  return (
                    <div key={i} className={done ? "step-anim" : ""} style={{ display:"flex", gap:0, opacity: done ? 1 : 0.25, transition:"opacity 0.4s" }}>
                      <div style={{ display:"flex", flexDirection:"column", alignItems:"center", width:38, flexShrink:0 }}>
                        <div style={{ width:22, height:22, borderRadius:"50%", border:`1.5px solid ${done ? col : "rgba(232,228,217,0.15)"}`, background: done && !active ? `${col}18` : "transparent", display:"flex", alignItems:"center", justifyContent:"center", fontSize:9, color: done ? col : "rgba(232,228,217,0.2)", fontFamily:MONO, transition:"all 0.3s" }}>
                          {done && !active ? "✓" : i+1}
                        </div>
                        {i < j.steps.length - 1 && <div style={{ width:1, flex:1, minHeight:20, background: done ? `${col}35` : "rgba(232,228,217,0.06)", transition:"background 0.3s" }} />}
                      </div>
                      <div style={{ padding:"0 0 20px 16px", flex:1 }}>
                        <div style={{ display:"flex", alignItems:"center", gap:10, marginBottom:3 }}>
                          <div style={{ fontSize:12, color: done ? "#E8E4D9" : "rgba(232,228,217,0.35)" }}>{step.label}</div>
                          <div style={{ fontSize:8, letterSpacing:"0.12em", textTransform:"uppercase", fontFamily:MONO, padding:"2px 6px", border:`1px solid ${col}40`, color:col, background:`${col}08` }}>{STEP_LABELS[step.type]}</div>
                          {active && <div style={{ fontSize:8, color:col, fontFamily:MONO, animation:"blink 1s infinite" }}>processing</div>}
                        </div>
                        <div style={{ fontSize:11, color:"rgba(232,228,217,0.38)", fontFamily:MONO }}>{step.note}</div>
                      </div>
                    </div>
                  );
                })}
              </div>
            </div>

            {/* Status footer */}
            <div style={{ border:`1px solid ${j.color}28`, background:`${j.color}06`, padding:"16px 18px" }}>
              <div style={{ display:"flex", alignItems:"center", gap:10, marginBottom:10 }}>
                <div style={{ width:6, height:6, borderRadius:"50%", background: running ? j.color : "#4CC980", animation: running ? "blink 1s infinite" : "none" }} />
                <div style={{ fontSize:8, letterSpacing:"0.16em", textTransform:"uppercase", color: running ? j.color : "#4CC980", fontFamily:MONO }}>
                  {running ? "Journey running — steps animating" : progress >= j.steps.length - 1 ? "Journey complete — agent response ready" : "Ready to run"}
                </div>
              </div>
              <div style={{ fontSize:11, color:"rgba(232,228,217,0.45)", lineHeight:1.7 }}>
                Agent trigger: <span style={{ color:"rgba(232,228,217,0.7)", fontStyle:"italic" }}>"{j.trigger}"</span>
              </div>
              <div style={{ display:"flex", gap:20, marginTop:10 }}>
                {["POLICY GUARD: ACTIVE","AUDIT TRAIL: ON","ZK CHAIN: TESTNET","ORACLE: LIVE"].map(t => (
                  <div key={t} style={{ fontSize:8, color:"rgba(232,228,217,0.2)", fontFamily:MONO }}>{t}</div>
                ))}
              </div>
            </div>
          </>
        )}
      </div>
    </div>
  );
}

// ═══════════════════════════════════════════════════════════════════════════════
// AGENT VIEW
// ═══════════════════════════════════════════════════════════════════════════════
function AgentView({ agent, agents, msgs, loading, input, setInput, sendMessage, activeAgent, setActiveAgent, chatEndRef }) {
  return (
    <div style={{ flex:1, display:"flex", overflow:"hidden" }}>
      {/* Sidebar */}
      <div style={{ width:190, borderRight:"1px solid rgba(201,168,76,0.12)", flexShrink:0, padding:"16px 0", overflowY:"auto", background:"rgba(201,168,76,0.01)" }}>
        <div style={{ padding:"0 14px 12px", fontSize:8, letterSpacing:"0.18em", textTransform:"uppercase", color:"rgba(232,228,217,0.2)", fontFamily:MONO }}>Executive Suite</div>
        {Object.values(agents).map(a => (
          <button key={a.id} onClick={() => setActiveAgent(a.id)} style={{ width:"100%", padding:"11px 14px", textAlign:"left", cursor:"pointer", background: activeAgent===a.id ? a.bg : "transparent", border:"none", borderLeft:`2px solid ${activeAgent===a.id ? a.color : "transparent"}`, fontFamily:SERIF, transition:"all 0.15s" }}>
            <div style={{ fontSize:12, color: activeAgent===a.id ? a.color : "rgba(232,228,217,0.42)" }}>{a.icon} {a.title}</div>
            <div style={{ fontSize:8, color:"rgba(232,228,217,0.2)", letterSpacing:"0.1em", textTransform:"uppercase", marginTop:2, fontFamily:MONO }}>{a.subtitle}</div>
          </button>
        ))}
        <div style={{ margin:"14px 14px 0", paddingTop:12, borderTop:"1px solid rgba(255,255,255,0.05)" }}>
          {["Policy Guard: Active","Audit Trail: On","Chain: Testnet","Oracle: Live"].map(t => (
            <div key={t} style={{ fontSize:8, color:"rgba(232,228,217,0.16)", fontFamily:MONO, lineHeight:2 }}>{t}</div>
          ))}
        </div>
      </div>

      {/* Chat */}
      <div style={{ flex:1, display:"flex", flexDirection:"column", overflow:"hidden" }}>
        {/* Agent header */}
        <div style={{ padding:"14px 24px", borderBottom:`1px solid ${agent.border}`, background:agent.bg, flexShrink:0, display:"flex", alignItems:"center", gap:14 }}>
          <div style={{ fontSize:28, color:agent.color }}>{agent.icon}</div>
          <div>
            <div style={{ fontSize:16, color:agent.color, letterSpacing:"0.04em" }}>{agent.title}</div>
            <div style={{ fontSize:8, color:"rgba(232,228,217,0.28)", letterSpacing:"0.12em", textTransform:"uppercase", fontFamily:MONO }}>{agent.subtitle} · Policy Guard · Audit Trail · Claude API</div>
          </div>
          <div style={{ marginLeft:"auto", display:"flex", alignItems:"center", gap:6, padding:"4px 10px", border:`1px solid ${agent.color}`, background:agent.bg }}>
            <div style={{ width:5, height:5, borderRadius:"50%", background:agent.color, animation:"blink 2s infinite" }} />
            <span style={{ fontSize:8, letterSpacing:"0.16em", textTransform:"uppercase", color:agent.color, fontFamily:MONO }}>Live</span>
          </div>
        </div>

        {/* Messages */}
        <div style={{ flex:1, overflowY:"auto", padding:"22px 24px", display:"flex", flexDirection:"column", gap:18 }}>
          {msgs.length === 0 && (
            <div style={{ display:"flex", flexDirection:"column", gap:18 }}>
              <div style={{ padding:"16px 18px", border:`1px solid ${agent.border}`, background:agent.bg }}>
                <div style={{ fontSize:9, color:agent.color, letterSpacing:"0.14em", textTransform:"uppercase", marginBottom:6, fontFamily:MONO }}>{agent.title} — Online</div>
                <div style={{ fontSize:12, color:"rgba(232,228,217,0.55)", lineHeight:1.75 }}>
                  I am your {agent.subtitle.toLowerCase()} AI executive. All interactions are logged to the immutable audit trail. Select a suggested query below — sample responses are instant — or type a custom question.
                </div>
              </div>
              <div>
                <div style={{ fontSize:8, letterSpacing:"0.18em", textTransform:"uppercase", color:"rgba(232,228,217,0.2)", marginBottom:10, fontFamily:MONO }}>Quick queries — instant sample responses</div>
                <div style={{ display:"flex", flexDirection:"column", gap:6 }}>
                  {agent.quickPrompts.map((p,i) => (
                    <button key={i} onClick={() => sendMessage(p)} style={{ padding:"10px 14px", background:"transparent", border:`1px solid rgba(232,228,217,0.08)`, cursor:"pointer", textAlign:"left", fontSize:12, color:"rgba(232,228,217,0.48)", fontFamily:SERIF, transition:"all 0.15s", display:"flex", alignItems:"center", justifyContent:"space-between", gap:12 }}
                      onMouseEnter={e => { e.currentTarget.style.borderColor = agent.color; e.currentTarget.style.color = "#E8E4D9"; }}
                      onMouseLeave={e => { e.currentTarget.style.borderColor = "rgba(232,228,217,0.08)"; e.currentTarget.style.color = "rgba(232,228,217,0.48)"; }}>
                      <span>{p}</span>
                      <span style={{ fontSize:8, color:"rgba(232,228,217,0.22)", fontFamily:MONO, flexShrink:0 }}>sample →</span>
                    </button>
                  ))}
                </div>
              </div>
            </div>
          )}

          {msgs.map((m, i) => (
            <div key={i} className="msg-anim" style={{ display:"flex", flexDirection:"column", alignItems: m.role==="user" ? "flex-end" : "flex-start" }}>
              <div style={{ fontSize:8, letterSpacing:"0.14em", textTransform:"uppercase", color: m.role==="user" ? "rgba(232,228,217,0.25)" : agent.color, marginBottom:5, fontFamily:MONO }}>
                {m.role==="user" ? "You" : agent.title}
              </div>
              <div style={{ maxWidth:"80%", padding:"12px 16px", background: m.role==="user" ? "rgba(232,228,217,0.04)" : agent.bg, border:`1px solid ${m.role==="user" ? "rgba(232,228,217,0.08)" : agent.border}`, fontSize:12, lineHeight:1.82, color:"#E8E4D9", whiteSpace:"pre-wrap", fontFamily: m.role==="assistant" ? MONO : SERIF }}>
                {m.content}
              </div>
            </div>
          ))}

          {loading && (
            <div style={{ display:"flex", flexDirection:"column", alignItems:"flex-start" }}>
              <div style={{ fontSize:8, letterSpacing:"0.14em", textTransform:"uppercase", color:agent.color, marginBottom:5, fontFamily:MONO }}>{agent.title}</div>
              <div style={{ padding:"12px 16px", background:agent.bg, border:`1px solid ${agent.border}`, display:"flex", gap:5, alignItems:"center" }}>
                {[0,1,2].map(d => <div key={d} style={{ width:5, height:5, borderRadius:"50%", background:agent.color, animation:"pulse 1.2s ease-in-out infinite", animationDelay:`${d*0.2}s` }} />)}
              </div>
            </div>
          )}
          <div ref={chatEndRef} />
        </div>

        {/* Input bar */}
        <div style={{ padding:"12px 24px", borderTop:"1px solid rgba(201,168,76,0.1)", background:"rgba(0,0,0,0.25)", flexShrink:0 }}>
          <div style={{ display:"flex", gap:10 }}>
            <input value={input} onChange={e => setInput(e.target.value)} onKeyDown={e => e.key==="Enter" && !e.shiftKey && sendMessage(input)} placeholder={`Query ${agent.title}...`}
              style={{ flex:1, padding:"9px 14px", background:"rgba(232,228,217,0.03)", border:"1px solid rgba(232,228,217,0.1)", color:"#E8E4D9", fontSize:12, outline:"none" }}
              onFocus={e => e.target.style.borderColor = agent.color}
              onBlur={e => e.target.style.borderColor = "rgba(232,228,217,0.1)"} />
            <button onClick={() => sendMessage(input)} disabled={loading || !input.trim()} style={{ padding:"9px 18px", background:"transparent", border:`1px solid ${agent.color}`, color:agent.color, cursor: loading || !input.trim() ? "default" : "pointer", fontSize:8, letterSpacing:"0.14em", textTransform:"uppercase", fontFamily:MONO, opacity: loading || !input.trim() ? 0.3 : 1, transition:"opacity 0.15s" }}>Send</button>
          </div>
          <div style={{ fontSize:8, color:"rgba(232,228,217,0.14)", marginTop:6, fontFamily:MONO }}>Quick queries use instant sample responses · Custom questions call Claude API live · All logged to audit trail</div>
        </div>
      </div>
    </div>
  );
}
