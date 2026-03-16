# Sports Betting Predictor - Specification

## 1. Project Overview

**Project Name:** Sports Betting Predictor  
**Type:** Web Application  
**Core Functionality:** AI-powered sports betting predictions with tracking, analytics, and profitability metrics  
**Target Users:** Sports bettors who want data-driven predictions and performance tracking

---

## 2. Features

### 2.1 Daily Predictions for Upcoming Games
- Display upcoming games with predicted outcomes
- Show confidence levels for each prediction
- Include key stats/analysis behind each pick
- Filter by sport (NFL, NBA, MLB, NHL, NCAA)
- Auto-refresh with new predictions daily

### 2.2 Best Bets List
- Curated "Top Picks" section highlighting highest-confidence predictions
- Value rating (e.g., 1-5 stars) based on odds vs. probability
- Quick-view card layout for easy scanning
- One-click access to place bet (external sportsbook links)

### 2.3 Track Profitability Over Time
- Running total of profits/losses (ROI percentage)
- Historical performance chart (daily/weekly/monthly)
- Breakdown by sport, bet type, favorite vs. underdog
- Bankroll tracking with starting balance

### 2.4 Win/Loss Record
- Overall record (W-L-Push)
- Win rate percentage
- Streak tracking (current & longest win/loss streaks)
- Unit record (e.g., +12.5 units this season)

---

## 3. UI/UX Specification

### Layout Structure
- **Header:** Logo, navigation tabs, settings icon
- **Main Content:** Tab-based interface (Today's Picks | Best Bets | Record | Tracker)
- **Sidebar (Desktop):** Quick stats summary, recent form

### Responsive Breakpoints
- Mobile: < 768px (single column, bottom nav)
- Tablet: 768px - 1024px (two columns)
- Desktop: > 1024px (full layout with sidebar)

### Visual Design
- **Color Palette:**
  - Background: `#0d1117` (dark)
  - Card Background: `#161b22`
  - Primary Accent: `#58a6ff` (blue)
  - Success: `#3fb950` (green for wins)
  - Danger: `#f85149` (red for losses)
  - Text Primary: `#f0f6fc`
  - Text Secondary: `#8b949e`
  
- **Typography:**
  - Headings: Inter Bold, 24px/20px/16px
  - Body: Inter Regular, 14px
  - Stats/Numbers: JetBrains Mono, 16px

- **Components:**
  - Prediction cards with team logos, spread, confidence bar
  - Animated profit counter
  - Progress rings for win rate
  - Toast notifications for new picks

---

## 4. Data Model

### Prediction
```
- id: string
- sport: string
- game: { homeTeam, awayTeam, startTime }
- pick: string (team name)
- spread: number
- odds: number
- confidence: number (0-100)
- result: "win" | "loss" | "push" | "pending"
- units: number
```

### User Stats
```
- totalWins: number
- totalLosses: number
- totalPushes: number
- bankroll: number
- startingBankroll: number
- profit: number
- roi: number
```

---

## 5. Acceptance Criteria

- [ ] Today's predictions page loads with at least 3 upcoming games
- [ ] Best Bets section shows top 3 highest confidence picks
- [ ] Profitability tracker displays accurate ROI calculation
- [ ] Win/Loss record shows correct totals with percentage
- [ ] Mobile responsive layout works on 375px width
- [ ] Dark theme consistently applied throughout
- [ ] All numbers update in real-time when new picks are added
