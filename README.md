# SwimLoading 🏊‍♂️

Cape Town Ocean Swimming Community App

## Features

### Working ✅
- **User Auth** - Signup/login via Supabase
- **Onboarding** - Legal waivers (POPIA compliant), personal details
- **Temperature Logging** - Log water temps with conditions & hazards
- **GPS Location** - Auto-detect nearest swim spot
- **Swim Events** - Create events, RSVP, join group swims
- **Dashboard** - Stats, streaks, points, upcoming swims
- **History** - Temperature trends with charts

### Coming Soon 🚧
- Emergency contacts
- Swimming profile (pace/speed)
- Leaderboard
- Push notifications
- Safety alerts

## Tech Stack
- **Frontend**: Vanilla HTML/JS (single file for now)
- **Backend**: Supabase (Auth, Database, Realtime)
- **Charts**: Chart.js
- **Icons**: Lucide

## Quick Start

1. Open `index.html` in a browser
2. Sign up with email
3. Accept waivers & complete profile
4. Start logging temperatures!

## File Structure
```
/
├── index.html          # Main app (canonical version)
├── 14files/            # Legal docs & SQL scripts
│   ├── terms-of-service.txt
│   ├── privacy-policy.txt
│   ├── liability-waiver.txt
│   ├── ONBOARDING_SQL.md
│   └── ONBOARDING_TEST_GUIDE.md
├── archive/            # Old versions (git history backup)
├── TODO.md             # Feature checklist
└── README.md           # This file
```

## Database

Supabase tables:
- `profiles` - User profiles with onboarding data
- `spots` - Swim locations (Atlantic/False Bay)
- `temp_logs` - Temperature readings
- `swim_events` - Group swim events
- `swim_event_members` - RSVPs
- `user_stats` - Points, streaks
- `badges` / `user_badges` - Gamification

## Deployment

Coming soon: Vercel/Netlify deployment for beta testing.

---

Built with 🌊 in Cape Town
