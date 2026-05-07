# BetPulse
users         → id, name, email, password_hash, balance, kyc_verified
bets          → id, user_id, selections, stake, odds, potential_win, status, created_at
transactions  → id, user_id, type (deposit/withdraw/bet/win), amount, reference, created_at
matches       → id, sport, league, home_team, away_team, kickoff_time, status, score
odds          → id, match_id, market (1x2/over-under), selections, values, updated_at
POST /auth/register       → Create account
POST /auth/login          → Login, return JWT token
GET  /matches/live        → Fetch live matches + odds
POST /bets/place          → Place a bet (deduct balance)
GET  /bets/history        → User's past bets
POST /payments/deposit    → Initiate Paystack payment
POST /payments/webhook    → Paystack confirms payment → credit balance
POST /payments/withdraw   → User withdrawal request
