# Unlocking Future Stars: Predicting High-Potential Football Players with Machine Learning

## PROJECT OVERVIEW

Smart scouting is pretty important, especially if it's outshining a big budget .Sifting through thousands of young players worldwide, all while working with a tight budget, can be quite a challenge. You need to know: Which of these kids will grow into a world-class player? Miss a future star, and you lose a chance to build a legacy. Sign the wrong player, and you waste millions. It’s a high-stakes gamble, and the pressure is on.

That’s where my project comes in. I’ve harnessed the power of data science to act like your ultimate scouting assistant. Using a massive dataset from the FIFA 21 game, packed with details on over 18,000 players—think skills, market value, and more—I’ve built a tool to predict which young players, aged 23 or under, have what it takes to reach the elite level, like a Lionel Messi or Kylian Mbappé. The model doesn’t just guess; it learns patterns from the data to spot players with that special potential, even if they’re flying under the radar. 

Source: fifa21_raw_data.csv from the FIFA 21 video game in Kaggle, containing player attributes for ~18,000 players.

##  OBJECTIVES

The key objectives to be achieved by this study are as follows:

1. **Find Young Players Who Can Become Stars**: Build a tool to predict which players aged 23 or younger will likely reach an elite level (Overall Rating ≥ 80), helping the club spot future top performers early.

2. **Save Money and Time in Scouting**: Create a model that shortlists the most promising players, so the scouting team can focus on the best targets without wasting resources on less likely prospects.

3. **Give the Club a Competitive Edge**: Use data to identify undervalued players before bigger clubs notice them, allowing the club to sign talent at a lower cost and build a stronger team.

### Key columns used:

↓OVA, Value, Wage, Attacking, Skill, Movement, Power, Mentality, Defending, W/F, SM, A/W, D/W, IR, Height, Weight, foot drive predictions. POT creates the target.

These columns were cleaned (e.g., converting Value to numeric) and used as features to predict High_Potential.

### Methodology:
Data Preparation: Cleaned the FIFA 21 dataset, filtered for players aged ≤ 23, and created the High_Potential target.

Exploratory Data Analysis (EDA): Analyzed distributions (e.g., Age, Value) and correlations (e.g., ↓OVA with Value).

Modeling: Built three models:

**.** Baseline Logistic Regression (simple, interpretable).

**.** Tuned Logistic Regression (optimized with class weights, expanded hyperparameters: C, solver, penalty).

**.** Tuned Decision Tree (tuned max_depth, min_samples_split).

Evaluation: Focused on Recall (~85% for Tuned Logistic Regression) to catch high-potential players, with ROC-AUC (~0.91) for class separation.

Player Ranking: Generated with predicted probabilities to prioritize high-potential players.

### Key Outcomes:

The Tuned Logistic Regression identifies ~85% of high-potential players, with top prospects like Kylian Mbappé ranked highly (probability ~0.95).

Value, Dribbling, and ↓OVA are the strongest predictors, guiding scouting criteria.

### Recommendations for the 2025–2026 Season

**1.** Target Top Prospects: Scout the top 20 players from player_ranking.csv with probabilities ≥ 0.8. Arrange trials or review footage in January 2025.

**2.** Focus on Skills: Prioritize players with Dribbling ≥ 75 and strong Skill scores for attacking and midfield roles.

**3.** Sign Young Talent: Negotiate for players aged 18–20 with Value ≤ €5M (e.g., €3M, probability ≥ 0.75) for long-term value.

**4.** Streamline Scouting: Use video tools (e.g., Wyscout) to evaluate the top 50 players, then scout the top 10–15 in person.

**5.** Scout Lower Leagues: Visit leagues like the Eredivisie in early 2025 to find players with low IR and high Skill Moves (SM ≥ 4).

**6.** Pilot the Model: Sign 2–3 top-ranked players in July 2025, track their performance, and update the model with new data in January 2026.






