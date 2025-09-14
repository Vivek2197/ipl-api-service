# 🏏 IPL API Service

A **Flask-based REST API** that provides rich statistics and insights from the **Indian Premier League (IPL)**.  
It uses match-level and ball-by-ball datasets to expose endpoints for team stats, head-to-head records, and detailed batting/bowling performances.

---

## 🚀 Features
- 📋 List all IPL teams
- ⚔️ Head-to-head record between two teams
- 🏆 Team records (matches, wins, losses, titles, etc.)
- 🏏 Batting stats for players (runs, SR, 50s, 100s, HS, etc.)
- 🎯 Bowling stats for players (wickets, economy, best figures, etc.)
- 🔍 Opponent-wise breakdown for both batting & bowling records

---

## 🛠️ Tech Stack
- **Python 3**
- **Flask** → API framework  
- **Pandas & NumPy** → Data processing  
- **CSV datasets** → IPL matches and ball-by-ball data  

---

## 📦 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/ipl-api-service.git
   cd ipl-api-service
   
2. (Optional) Create a virtual environment:
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

3.Install dependencies:

pip install -r requirements.txt

▶️ Running the API

Start the server with:

python app.py


API will be available at 👉 http://127.0.0.1:5000

📡 API Endpoints
1. Root
GET /


Response

Hello World

2. Get All Teams
GET /api/teams


Response

{
  "teams": ["MI", "CSK", "RCB", "KKR", ...]
}

3. Team vs Team
GET /api/teamvteam?team1=MI&team2=CSK


Response

{
  "total_matches": 36,
  "MI": 21,
  "CSK": 15,
  "draws": 0
}

4. Team Record
GET /api/team-record?team=RCB


Gives overall stats and performance against every opponent.

5. Batting Record
GET /api/batting-record?batsman=Virat Kohli


Response (sample)

{
  "Virat Kohli": {
    "all": {
      "innings": 215,
      "runs": 7263,
      "fours": 643,
      "sixes": 234,
      "avg": 37.25,
      "strikeRate": 130.2,
      "fifties": 50,
      "hundreds": 7,
      "highestScore": "122*",
      "notOut": 32,
      "mom": 13
    },
    "against": {
      "MI": {...},
      "CSK": {...}
    }
  }
}

6. Bowling Record
GET /api/bowling-record?bowler=Jasprit Bumrah


Response (sample)

{
  "Jasprit Bumrah": {
    "all": {
      "innings": 120,
      "wicket": 145,
      "economy": 7.39,
      "average": 23.1,
      "strikeRate": 19.4,
      "fours": 300,
      "sixes": 120,
      "best_figure": "4/14",
      "3+W": 6,
      "mom": 5
    },
    "against": {
      "RCB": {...},
      "CSK": {...}
    }
  }
}

📂 Project Structure
ipl-api-service/
│
├── app.py           # Main Flask app (routes & API)
├── ipl.py           # IPL helper functions (teams & head-to-head)
├── jugaad.py        # Player stats module (batting & bowling)
├── ipl-matches.csv  # Match-level dataset
├── requirements.txt # Dependencies
└── README.md        # Documentation

📝 Requirements

Minimal requirements.txt:

flask
pandas
numpy

