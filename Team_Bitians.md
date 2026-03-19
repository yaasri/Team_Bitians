# 🛡️ ShiftShield
### *AI-Powered Weekly Income Protection for Food Delivery Workers*

> **Guidewire DEVTrails 2026 Hackathon Submission**
> Parametric micro-insurance that protects Swiggy/Zomato delivery partners from income loss caused by rain, heatwaves, platform outages, demand crashes, and more — with zero-touch, automatic payouts.

---

## 📋 Table of Contents

- [Problem Statement](#-problem-statement)
- [Our Solution](#-our-solution)
- [Target Persona](#-target-persona)
- [Realistic User Scenario](#-realistic-user-scenario)
- [Product Workflow](#-product-workflow)
- [Parametric Triggers](#-parametric-triggers)
- [Weekly Premium Model](#-weekly-premium-model)
- [AI Components](#-ai-components)
- [System Architecture](#️-system-architecture)
- [Key Features](#-key-features)
- [Tech Stack](#️-tech-stack)
- [Development Roadmap](#-development-roadmap)
- [Expected Impact](#-expected-impact)

---

## 🚨 Problem Statement

India's **50+ million gig delivery workers** on platforms like Swiggy and Zomato face a harsh income reality:

- Earnings are **volatile and shift-dependent**, primarily during lunch (12–3 PM) and dinner (7–11 PM) peaks.
- A single weather event, platform outage, or restaurant closure can wipe out **30–60% of weekly income** overnight.
- No existing insurance product accounts for **shift-level disruptions** — current covers are either too broad, too slow, or require manual claims.
- Workers have **no safety net** when external disruptions — not personal negligence — cause income loss.

> *"A delivery rider in Coimbatore can lose ₹600–₹800 in a single rainy evening. That's not a minor inconvenience — that's groceries for the week."*

---

## 💡 Our Solution

**ShiftShield** is a **shift-aware, behavior-aware parametric micro-insurance platform** that:

- Protects weekly income loss from **external, verifiable disruptions** — heavy rain, heatwaves, fog, floods, curfews, restaurant shutdowns, demand crashes, and platform outages.
- Combines **multiple disruption signals** into a single Disruption Score instead of relying on a single weather trigger.
- Delivers **automatic, zero-touch payouts** into an in-app Income Smoothing Wallet — no claim forms, no manual decisions.
- Renews **weekly**, matching the short earning cycle of gig workers.

---

## 👤 Target Persona

| Attribute | Detail |
|-----------|--------|
| **Who** | Swiggy / Zomato food delivery partners |
| **Where** | Tier-1 and Tier-2 Indian cities (e.g., Coimbatore, Pune, Jaipur, Lucknow) |
| **Work Pattern** | 6–7 days/week; split lunch (12–3 PM) and dinner (7–11 PM) shifts |
| **Weekly Income** | ₹3,500 – ₹6,000 (highly variable) |
| **Risk Exposure** | Extreme heat, heavy monsoon rain, winter fog, unsafe late-night conditions, platform volatility |
| **Pain Point** | No access to affordable, relevant insurance; disruptions cause unrecoverable income gaps |

---

## 🎯 Realistic User Scenario

**Meet Ravi** — a 24-year-old Swiggy delivery partner in Coimbatore.

- Typical weekly earnings: **₹4,000–₹5,000**, most earned during the dinner peak (7–11 PM).
- One evening, heavy rain and waterlogging hit his zone. Several restaurants shut early. Swiggy stops accepting new orders for 4–5 hours.
- His orders drop from **18–20 down to 5–6** that evening — a loss of ₹600–₹800 with no recourse.

**With ShiftShield:**

1. Ravi has purchased a Weekly plan with **25 protected hours** aligned to his dinner peak slots.
2. When rainfall crosses the threshold and Swiggy marks his zone as "red / high-risk," ShiftShield's engine activates automatically.
3. The system cross-checks Ravi's GPS trail, his platform login logs, and zone-level order data.
4. Within minutes, Ravi receives a push notification:

   > *"Heavy rain + order crash in your dinner slot – Disruption Score 0.84 – estimated payout ₹720 pending checks."*

5. The payout is approved and credited to his **Income Smoothing Wallet** — no forms, no calls, no waiting.

---

## 🔄 Product Workflow

### Step 1 — Onboarding
- Rider downloads the ShiftShield app and signs up via phone + OTP.
- Consents to share basic profile (city, zones) and link Swiggy/Zomato rider ID via API.
- ShiftShield fetches **8–12 weeks of historical earnings**, shift timings, and zone data to build a baseline profile.

### Step 2 — Risk Profiling & Weekly Offer
Before each new week, the **Shift & Zone Risk Brain** analyses:
- Historical earnings per hour per slot (lunch vs dinner, weekday vs weekend).
- Preferred delivery zones (city center, suburbs, highway corridors).
- Historical disruption patterns: rain days, fog days, strikes, restaurant shutdowns.
- 7-day weather forecast for those specific zones.

The app presents Ravi with a personalised weekly offer:
- **Expected weekly earnings (E)**
- **Suggested coverage limit (C)**
- **Weekly premium (P)** based on risk score *R*
- **Number of protected hours** included (Smart Shift Shield)
- Plain-language trigger explanation: *"Heavy rain + restaurant shutdown in your zone during protected hours will pay up to ₹X/hour."*

### Step 3 — Policy Creation (Weekly Micro-Policy)
- Rider accepts and pays weekly premium *P* via UPI.
- System issues a **7-day food-delivery micro-policy** with:
  - Policy dates and shift windows (e.g., 12–3 PM, 7–11 PM)
  - Covered zones and parametric triggers
  - Weekly coverage cap *C*
- **Income Smoothing Wallet:** 90–95% of *P* funds the risk pool; 5–10% goes to a small savings wallet the rider can withdraw monthly if unused.

### Step 4 — Real-Time Disruption Detection
The **Event/Trigger Service** continuously monitors:
- 🌧️ **Weather:** Rainfall intensity, temperature, fog visibility by pin-code.
- 📱 **Platform:** Mock Swiggy/Zomato APIs for zone-level outages and "no orders / low orders" flags.
- 📉 **Demand:** Drastic drop in orders per available rider vs 4-week historical average.
- 📢 **Social/Admin:** Union feeds, curfew orders, or restaurant cluster closures.

When metrics cross thresholds during protected hours, a **DisruptionEvent** is generated:
> *"Heavy rain + 60% order drop, Zone X, 8–10 PM"*

### Step 5 — Disruption Scoring & Auto-Claim
The **Disruption Brain** computes a **Disruption Score (D)** combining:
- Weather severity (rain intensity / fog density)
- Operational issues (platform outage duration, "orders paused" flags)
- Demand collapse (orders per rider down >40–60% vs baseline)

The **Claim Engine** validates:
- Is the rider's weekly policy active?
- Is the event within their protected hours?
- Is their GPS trail inside the affected zone?

Estimated lost income is calculated from historical hourly earnings for that slot, scaled by *D*.

### Step 6 — Fraud Checks & Decision
The **Trust Brain** runs automated checks:
- GPS location vs zone (prevents fake location claims).
- Platform logs: Was the rider logged in and available? Were there genuinely no orders?
- Claim frequency vs peers in the same zone.
- Device clustering (multiple IDs on same device).

Low-risk claims are **auto-approved**. Suspicious claims are flagged for review but remain **zero-touch for the rider** — no forms required.

### Step 7 — Payout & Dashboards
- Approved payouts credit the rider's **Income Smoothing Wallet**.
- Rider withdraws via UPI to their bank account.

**Worker Dashboard:**
> *"This week: ₹900 protected (3 events). Protected hours used: 10/25. Wallet balance: ₹350."*

**Admin Dashboard (Insurer / Platform):**
- Loss ratios by city, zone, and shift (lunch vs dinner).
- "Income Stability Index" per zone.
- Next-week disruption risk forecast.

---

## ⚡ Parametric Triggers

| Trigger | Data Sources | Condition | Payout |
|---------|-------------|-----------|--------|
| **Heavy Rain + Restaurant Shutdown** | Weather API + Platform restaurant availability | Rainfall >30 mm in 3-hour window AND >50% of usual restaurants closed | 70–80% of average hourly earnings for affected protected hours |
| **Heatwave / Extreme Heat** | IMD temperature forecasts | Max temp ≥40–42°C for ≥3 hours; platform throttles orders | Fixed per-day compensation for scheduled slots |
| **Dense Fog / Visibility** | Fog/visibility index + platform safety policy | Visibility below threshold AND platform reduces late-night deliveries | Hourly benefit for protected late-night slots |
| **Platform Outage / Technical Glitch** | Mock uptime API + error logs | Platform downtime ≥45 minutes while rider is logged in | Up to 80% of expected hourly earnings for that window |
| **Demand Crash** | Orders per rider vs 4-week baseline | Orders per active rider drop >40–60% below baseline despite normal weather | Partial hourly compensation for protected hours |
| **Curfew / Strike** | Admin sources, police orders, union feeds | Zone marked "curfew/strike" for >X hours; platform restricts operations | Flat per-day amount per affected day |

---

## 📐 Weekly Premium Model

### Variables

| Symbol | Definition |
|--------|-----------|
| **E** | Average weekly earnings over last N weeks |
| **R** | Composite risk score (0–1) |
| **C** | Weekly coverage limit = γE, where γ = 0.5–0.7 |
| **P** | Weekly premium |

### Risk Score Formula

```
R = 0.4 × R_rain + 0.3 × R_heat/fog + 0.3 × R_outage/demand
```

### Premium Formula

```
P = αE + βRC     subject to P ≤ 5% of E
```

### Example Calculation

| Parameter | Value |
|-----------|-------|
| Expected Weekly Earnings (E) | ₹4,500 |
| Risk Score (R) | 0.6 |
| Coverage Limit (C = 0.6 × E) | ₹2,700 |
| **Weekly Premium (P)** | **~₹130/week** |

> At ~₹130/week (~2.9% of earnings), a Swiggy rider gets up to ₹2,700 in weekly coverage — triggered automatically, paid instantly.

---

## 🤖 AI Components

### 1. Shift & Zone Risk Brain
- Analyses historical earnings, shift patterns, and zone-level data to profile individual risk before each week.
- Outputs personalised risk scores and coverage recommendations.

### 2. Disruption Brain (Adaptive Parametric Matrix)
- Combines weather data, platform signals, and demand metrics into a single **Disruption Score (D)**.
- Goes beyond simple "rain index" triggers to model real-world income impact.

### 3. Trust Brain (Fraud Detection)
- ML-based anomaly detection on GPS trails, platform login consistency, and peer comparison.
- Enables automatic approvals for low-risk claims while flagging suspicious patterns.

### 4. Income Smoothing Engine
- Tracks rider earnings over time and uses actuarial + ML models to smooth payouts across volatile weeks.
- Incorporates unused premium savings to build a long-term financial buffer for riders.

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                      RIDER-FACING LAYER                      │
│         ShiftShield App  ←→  Income Smoothing Wallet         │
└───────────────────────────────┬─────────────────────────────┘
                                │
┌───────────────────────────────▼─────────────────────────────┐
│                      CORE INTELLIGENCE                        │
│                                                              │
│  ┌─────────────────┐   ┌──────────────────┐   ┌───────────┐ │
│  │  Risk Brain     │   │  Disruption Brain │   │  Trust    │ │
│  │  (Profiling &   │   │  (Parametric      │   │  Brain    │ │
│  │   Pricing)      │   │   Scoring)        │   │  (Fraud)  │ │
│  └────────┬────────┘   └────────┬─────────┘   └─────┬─────┘ │
│           └───────────────────┬─┘                   │       │
│                               ▼                     │       │
│                    ┌──────────────────┐              │       │
│                    │  Claim Engine    │◄─────────────┘       │
│                    │  (Auto-Approve / │                      │
│                    │   Flag / Payout) │                      │
│                    └──────────────────┘                      │
└───────────────────────────────┬─────────────────────────────┘
                                │
┌───────────────────────────────▼─────────────────────────────┐
│                     DATA INTEGRATION LAYER                    │
│                                                              │
│  Weather API   │  Swiggy/Zomato   │  IMD Forecasts           │
│  (Rain/Fog/    │  Mock APIs       │  (Heat/Fog)              │
│   Heat)        │  (Orders/Zones)  │                          │
│                                                              │
│  Admin/Union Feeds  │  GPS/Location Service  │  UPI Gateway  │
└─────────────────────────────────────────────────────────────┘
```

---

## ✨ Key Features

### 🕐 Smart Shift Shield
- Coverage is linked to **actual platform online hours** — not a blanket 24/7 policy.
- Riders get a fixed number of **Protected Hours** per week where payouts are higher.
- Eliminates moral hazard: riders are only covered during verified active delivery windows.

### 📊 Adaptive Parametric Matrix
- A single **Disruption Score** combines weather severity, platform outages, and demand crashes.
- Far more accurate than simple single-trigger weather covers.
- Prevents both under-payment (one signal misses) and over-payment (spurious triggers).

### 💰 Income Smoothing Wallet
- 5–10% of each weekly premium builds a small personal savings buffer.
- Parametric payouts credited here are available for immediate UPI withdrawal.
- Smooths volatile gig earnings into a more predictable weekly income experience.

### 🤝 Zero-Touch Claims
- No forms. No calls. No waiting.
- The entire detection-to-payout pipeline runs automatically.
- Riders are notified at each stage with plain-language updates in their regional language.

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Mobile App** | React Native (iOS + Android) |
| **Backend API** | Node.js / FastAPI (Python) |
| **AI / ML** | Python (scikit-learn, XGBoost, custom scoring models) |
| **Weather Data** | OpenWeatherMap API / IMD API |
| **Platform Integration** | Mock Swiggy/Zomato Rider APIs |
| **Location Services** | Google Maps Platform / GPS tracking |
| **Payments** | Razorpay UPI Sandbox |
| **Database** | PostgreSQL (policy/claim data) + Redis (real-time event cache) |
| **Insurance Core** | Guidewire PolicyCenter (parametric policy issuance) |
| **Fraud Detection** | Isolation Forest + rule-based anomaly scoring |
| **Notifications** | Firebase Cloud Messaging (FCM) |
| **Infrastructure** | AWS / GCP (containerised via Docker) |

---

## 🗺️ Development Roadmap

### Phase 1 — MVP (Hackathon Scope)
- [ ] Rider onboarding and Swiggy/Zomato mock API integration
- [ ] Historical earnings ingestion and risk profiling engine
- [ ] Weekly premium calculation and UPI sandbox payment
- [ ] Core parametric triggers: Heavy Rain + Restaurant Shutdown, Platform Outage
- [ ] Basic Disruption Score computation
- [ ] Auto-claim engine with GPS cross-validation
- [ ] Income Smoothing Wallet with UPI payout
- [ ] Rider-facing dashboard (React Native prototype)
- [ ] Admin/insurer loss-ratio dashboard

### Phase 2 — Expansion (3–6 Months Post-Hackathon)
- [ ] Live integration with real Swiggy/Zomato Rider APIs
- [ ] Full trigger set: Heatwave, Fog, Demand Crash, Curfew/Strike
- [ ] Trust Brain ML model trained on real claim patterns
- [ ] Multi-city rollout across 5 Tier-1 cities
- [ ] Guidewire PolicyCenter deep integration for policy lifecycle
- [ ] Rider app in regional languages (Tamil, Hindi, Telugu, Kannada)
- [ ] Monthly savings wallet withdrawal functionality

### Phase 3 — Scale (6–18 Months)
- [ ] Tier-2 city expansion (20+ cities)
- [ ] Dynamic premium adjustment using real-time ML risk re-scoring
- [ ] Partnership with IRDAI-licensed micro-insurance carrier
- [ ] White-label licensing to Swiggy, Zomato, and Dunzo platforms
- [ ] Expansion to adjacent gig segments: auto-rickshaw drivers, hyperlocal couriers
- [ ] Aggregated "Income Stability Index" as B2B analytics product for platforms

---

## 📈 Expected Impact

| Metric | Target (Year 1) |
|--------|----------------|
| **Riders Covered** | 50,000+ across 5 cities |
| **Average Weekly Premium** | ₹100–₹150/rider |
| **Average Payout per Event** | ₹400–₹900 |
| **Claims Processed Automatically** | >90% zero-touch |
| **Income Volatility Reduction** | 25–35% for active users |
| **Gross Written Premium (GWP)** | ₹2.5–₹4 Cr annually (Year 1) |

> ShiftShield doesn't just protect income — it **restores dignity and financial agency** to millions of gig workers who power India's food delivery economy, yet remain invisible to the traditional insurance industry.

---

## 👥 Team

| Name | Role |
|------|------|
| *[Team Member 1]* | Product & Insurance Design |
| *[Team Member 2]* | AI / ML Engineering |
| *[Team Member 3]* | Backend & API Integration |
| *[Team Member 4]* | Frontend & UX |

---

## 📄 License

This project was created for **Guidewire DEVTrails 2026**. All rights reserved by the team.

---

*Built with ❤️ for India's gig economy workers — because every shift deserves a shield.*
