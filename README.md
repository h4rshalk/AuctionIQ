# ⚡ AuctionIQ — IPL Player Valuation & Auction Intelligence

> End-to-end sports analytics platform — Python • SQL • Power BI • Machine Learning

![Dashboard](screenshots/08_page3_auction.png)

---

## 🎯 The Problem We're Solving

IPL franchises spend ₹100+ crore in auctions making decisions based on basic 
statistics. Smaller franchises can't afford full analytics teams. AuctionIQ is 
a data-driven player valuation platform that tells franchises exactly who is 
worth the money — and who isn't.

---

## 📊 Dataset

| Metric | Value |
|--------|-------|
| Source | Cricsheet.org — ball-by-ball IPL data |
| Seasons | 19 (2007/08 → 2026) |
| Matches | 1,209 |
| Balls | 287,513 |
| Batters ranked | 229 |
| Bowlers ranked | 191 |
| Total players | 306 |

---

## 🏏 Key Findings

| Finding | Insight |
|---------|---------|
| Most Undervalued | CV Varun — ₹1.7Cr with value ratio 47.28 |
| Most Overvalued | RG Sharma — ₹16Cr with value ratio 4.07 |
| #1 Batter (BPI) | H Klaasen — BPI 86.12 |
| #1 Bowler (BoPI) | JJ Bumrah — BoPI 83.65 |
| #1 Allrounder | SP Narine — only TRUE allrounder in top 15 |
| Most Match Wins | AB de Villiers — 25 POTM awards |
| IPL Evolution | Run rate grew from 7.74 (2007) to 9.25 (2026) — +20% |
| Six Rate | Doubled from 4.78% to 8.08% over 19 seasons |
| Death Over King | AB de Villiers — 222.9 SR in death overs |
| Powerplay Beast | AD Russell — 241.2 SR in powerplay |

---

## 🔬 Methodology

### Batting Performance Index (BPI)
Weighted composite of 6 metrics:

| Metric | Weight |
|--------|--------|
| Recent Strike Rate (2023-25) | 25% |
| Death Over Strike Rate | 20% |
| Career Strike Rate | 20% |
| Batting Average | 15% |
| Boundary % | 10% |
| Consistency Score | 10% |

### Bowling Performance Index (BoPI)
Weighted composite of 6 metrics:

| Metric | Weight |
|--------|--------|
| Recent Economy (2023-25) | 20% |
| Recent Wickets | 20% |
| Career Wicket Rate | 20% |
| Career Economy | 15% |
| Dot Ball % | 15% |
| Death Economy | 10% |

### Player Value Score (PVS)
- **Batter**: PVS = BPI
- **Bowler**: PVS = BoPI
- **Allrounder**: PVS = (BPI × 0.5) + (BoPI × 0.5) + 5 bonus

### Auction Valuation Model
- **Value Ratio** = PVS ÷ Auction Price (₹Cr)
- **Undervalued**: High PVS + Low Price
- **Premium**: High PVS + High Price
- **Overvalued**: Low PVS + High Price
- **Budget**: Low PVS + Low Price

---

## 🛠️ Tech Stack

| Layer | Tools |
|-------|-------|
| Data Collection | Cricsheet.org ball-by-ball CSV |
| Data Processing | Python, Pandas, NumPy |
| Analysis | Python, Statistical modelling |
| Visualisation | Matplotlib, Seaborn |
| Dashboard | Power BI, DAX |
| Version Control | Git, GitHub |

---

## 📁 Project Structure


auctioniq/
│
├── data/
│   └── README.md              ← how to get the raw data
│
├── notebooks/
│   ├── 00_data_exploration.ipynb   ← load 287K balls
│   ├── 01_batting_analysis.ipynb   ← BPI for 229 batters
│   ├── 02_bowling_analysis.ipynb   ← BoPI for 191 bowlers
│   ├── 03_player_index.ipynb       ← PVS + auction valuation
│   └── 04_dashboard_prep.ipynb     ← 8 Power BI exports
│
├── exports/                   ← Power BI data sources
│   ├── player_index.csv
│   ├── batting_top100.csv
│   ├── bowling_top100.csv
│   ├── auction_valuation.csv
│   ├── season_trends.csv
│   ├── team_stats.csv
│   ├── potm_awards.csv
│   └── phase_batting.csv
│
├── screenshots/               ← dashboard images
├── requirements.txt
└── README.md


---

## 📈 Dashboard Pages

### Page 1 — IPL Evolution
![Page 1](screenshots/06_page1_ipl_evolution.png)

### Page 2 — Player Rankings
![Page 2](screenshots/07_page2_player_rankings.png)

### Page 3 — Auction Intelligence
![Page 3](screenshots/08_page3_auction.png)

---

## 🚀 How to Run

```bash
# Clone the repo
git clone https://tgithub.com/h4rshalk/auctioniq.gi
cd auctioniq

# Create virtual environment
python -m venv venv
venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Download IPL data
# Go to https://cricsheet.org/downloads/ipl_csv2.zip
# Extract all CSV files into data/raw/

# Run notebooks in order
# 00 → 01 → 02 → 03 → 04
```

---

## 💡 Business Applications

- **Franchise analysts** — identify undervalued players before auction
- **Fantasy cricket** — data-driven team selection
- **Sports media** — evidence-based player comparison
- **Coaching staff** — phase-wise weakness analysis

---

## 👤 Author

**Harshal Nanasaheb Kawane**
📧 harshalkawane3@gmail.com
🔗 [LinkedIn](https://linkedin.com/in/harshal-kawane)
📍 Pune, Maharashtra