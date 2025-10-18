# 🏈 Football Match Predictor

**Football Match Predictor** is a full-stack web app that predicts which team is more likely to win based on player stats and team composition.  
Built for friendly games, it lets you add players, form teams, and view real-time win probabilities using data-driven machine learning models.

---

## 🚀 Features
- **Player Management:** Add and edit players with key attributes (speed, strength, accuracy, etc.)
- **Team Builder:** Drag-and-drop interface to create and edit teams
- **Match Predictor:** Instantly calculate win probabilities between any two lineups
- **Results Tracking:** Record scores and automatically update ratings
- **Hybrid Models:** Elo + Logistic Regression for balanced prediction accuracy
- **Analytics Dashboard:** Track team stats, player impact, and historical performance trends

---

## 🧱 Tech Stack
**Frontend**
- Next.js (React + TypeScript)
- Tailwind CSS + shadcn/ui
- TanStack Query
- Recharts (data visualization)

**Backend**
- FastAPI (Python)
- PostgreSQL (database)
- SQLAlchemy + Alembic
- scikit-learn, pandas, numpy (model training)
- Optional: Redis + Celery for background training jobs

**Deployment**
- Vercel (frontend)
- Railway / Render (backend)
- Supabase / Neon (PostgreSQL hosting)
- GitHub Actions (CI/CD)

---

## 🧠 Model Overview
1. **Elo Rating System:** Base rating that updates after every match.  
2. **Logistic Regression:** Predicts win probability using team stats + Elo difference.  
3. *(Coming soon)* Gradient Boosting for more complex, non-linear predictions.

**Example Features**
| Feature | Description |
|----------|-------------|
| avg_speed | Average player speed per team |
| avg_strength | Average strength |
| avg_accuracy | QB/WR accuracy |
| elo_diff | Difference in team Elo ratings |
| win_label | 1 if Team A wins, 0 otherwise |

---

## 🗂️ Database Schema
- **players(id, name, position, speed, strength, accuracy, stamina)**  
- **teams(id, name, captain_id)**  
- **team_members(team_id, player_id)**  
- **matches(id, team_a_id, team_b_id, final_score_a, final_score_b, winner)**  
- **lineups(match_id, player_id, position)**  
- **models(id, type, trained_at, metrics, artifact_path)**  

---

## 🧰 Setup Instructions

### Prerequisites
- Node 20+
- Python 3.11+
- PostgreSQL (local or hosted)
- Docker *(optional for local dev)*

### 1. Clone the Repo
```bash
git clone https://github.com/<your-username>/football-match-predictor.git
cd football-match-predictor
