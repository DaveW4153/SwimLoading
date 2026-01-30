# SwimLoading Roadmap

## Vision
The go-to app for Cape Town ocean swimmers — and eventually, the platform that makes open water swimming insurable.

---

## 🔴 Phase 1: MVP (Beta Testers)

### Auth & Onboarding
- [x] Signup/login via Supabase
- [x] Legal waivers (POPIA compliant)
- [x] Personal details collection
- [ ] Swimming profile (pace, cold tolerance)
- [ ] Emergency contact (required)

### Core Features
- [x] Temperature logging with conditions/hazards
- [ ] GPS location detection
- [x] Dashboard with stats
- [x] Swim events + RSVP
- [ ] Basic leaderboard

### Goal: 20 beta testers actively logging

---

## 🟡 Phase 2: Safety & Community

### Safety System (Insurance Foundation)
- [ ] "Going swimming" check-in
- [ ] "I'm out safe" check-out  
- [ ] Auto-alert if no check-out (configurable: 1hr, 2hr, 3hr)
- [ ] Emergency contact notification
- [ ] Incident reporting (near-miss, injury, rescue)
- [ ] Hazard alerts (shark sighting, bluebottles, rips)

### Community
- [ ] Public swimmer profiles
- [ ] Activity feed
- [ ] Photo uploads
- [ ] Comments on logs/events
- [ ] Follow other swimmers

### Gamification
- [ ] Points system
- [ ] Streak tracking
- [ ] Badges & achievements
- [ ] Weekly/monthly leaderboards

### Goal: 200 active users, safety data flowing

---

## 🟢 Phase 3: Data & Intelligence

### Analytics
- [ ] Historical temp trends per spot
- [ ] Best swimming times predictions
- [ ] Crowd patterns (busy vs quiet times)
- [ ] Personal stats dashboard

### Integrations
- [ ] Tide/swell data (Surfline API?)
- [ ] Weather overlay
- [ ] Water quality data (City of CT?)
- [ ] Strava/Garmin import

### Goal: Rich dataset proving swimmer behavior patterns

---

## 🔵 Phase 4: Insurance Play

### What Insurers Need
1. **Verified Identity** — Know who's swimming
2. **Risk Assessment** — Experience level, behavior patterns
3. **Loss Prevention** — Safety features reduce incidents
4. **Claims Data** — What happened, where, conditions

### Features for Insurance
- [ ] Verified swimmer certification
- [ ] Safety score (based on check-in compliance, group swims, etc.)
- [ ] Incident reports with conditions data
- [ ] Swimming history export (PDF for applications)
- [ ] Integration hooks for insurer systems

### Insurance Product Ideas

#### Per-Swim Coverage
- User buys R20-50 coverage before swim
- Covers: emergency rescue, medical, liability
- Payout: Up to R500k
- SwimLoading takes 15-20% commission

#### Monthly Membership
- R150-300/month
- Unlimited swims covered
- Includes premium app features
- Family plans available

#### Event Insurance
- Organizer buys coverage for group swim
- R10-20 per participant
- Covers all RSVPed swimmers

#### Data Licensing
- Anonymized swimming patterns
- Incident/near-miss data
- Risk modeling for actuaries
- Seasonal trends

### Target Partners
| Company | Why |
|---------|-----|
| Discovery Vitality | Fitness data obsessed, rewards active lifestyle |
| Outsurance | Digital-first, innovative products |
| Hollard | Niche sports insurance experience |
| King Price | Disruptive, might try something new |
| Specialized marine insurers | Understand water risks |

### Pitch Angle
> "We've built a community of 500 verified ocean swimmers in Cape Town. They check in before swims, check out after, log conditions, and report incidents. We have 6 months of behavioral data. Want to pilot a product with us?"

---

## 💰 Revenue Streams

### Phase 1-2 (Free)
- Build userbase, no revenue
- Maybe: Tip jar / "buy us a coffee"

### Phase 3 (Premium)
- Premium features: R50/month
  - Advanced stats
  - Data export
  - Priority support
  - Ad-free

### Phase 4 (Insurance)
- Commission on insurance sales (15-20%)
- Data licensing fees
- White-label for swim clubs

### Phase 5 (Expansion)
- Other regions (Durban, PE, Mozambique)
- Other sports (trail running, MTB, paddling)
- Corporate wellness programs
- Coaching marketplace

---

## Technical Debt / Cleanup

- [ ] Single HTML → proper component structure
- [ ] Consider Flutter for native app
- [ ] Proper error handling
- [ ] Offline support (log temps without signal)
- [ ] Push notifications
- [ ] Admin dashboard

---

## Success Metrics

| Metric | Phase 1 | Phase 2 | Phase 3 |
|--------|---------|---------|---------|
| Registered users | 50 | 500 | 2000 |
| Weekly active | 20 | 200 | 800 |
| Temp logs/week | 50 | 500 | 2000 |
| Check-in rate | - | 60% | 80% |
| Events/month | 5 | 30 | 100 |

---

*Last updated: 2026-01-29*
