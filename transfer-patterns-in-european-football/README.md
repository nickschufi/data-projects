# Transfer Patterns in European Football

Group project (team of 3) completed during the **Data Collection, Integration and Preprocessing (CIP)** course.

## Objective

This project explores transfer spending trends and player movement patterns across Europe's top football leagues (2009-2021). It explores how nationality, position, and league characteristics influence transfer activity and performance outcomes, guided by three research questions:

1. **Transfer patterns across leagues**: position and nationality dominance, and how club spending varies across transfer windows.
2. **Transfer market dynamics**: how player age, transfer type, and league characteristics influence transfer activity, spending patterns, and their relationship with team performance across seasons and age groups.
3. **Spending vs. success**: how La Liga and the Premier League differ in transfer spending, and how that spending impacts final league standings.

## Data Source

- **Football Transfer dataset** from [Kaggle](https://www.kaggle.com/datasets/mexwell/football-transfer-dataset), player transfers, fees, clubs, seasons, positions, and nationalities across Europe's top leagues (2009–2021, ~70'000 entries)
- **League standings data**, scraped via BeautifulSoup from football statistics sites, for the Premier League and La Liga (2013–2015 seasons)

## Approach

1. **Data cleaning & preprocessing**: checked for missing data, verified data types, removed unusable rows, dropped irrelevant columns, and handled duplicates and outliers.
2. **Web scraping**: scraped league standings data with BeautifulSoup to enrich the transfer dataset with performance outcomes.
3. **Exploratory & statistical analysis**: analyzed transfer patterns by position, nationality, age group, and league, applied Spearman correlation and Poisson regression models to test the relationship between spending and league performance.
4. **Visualization**: built static and interactive visualizations (`matplotlib`, `seaborn`, `plotly`, `plotnine`) to communicate findings across research questions.

## Tools & Technologies

`Python` · `pandas` · `numpy` · `BeautifulSoup` · `requests` · `matplotlib` · `seaborn` · `plotly` · `plotnine` · `statsmodels` · `scipy` and more packages.

## Key Findings

- **Central positions** (CB, CF, CM, GK) saw the highest transfer activity across leagues, though the pattern varied by league.
- **Youth transfers** peaked around 2013–2014 and declined afterward. **Serie A** consistently led in youth exports, while the **Premier League** and German clubs favored acquiring established talent over developing youth.
- **Serie A** showed the largest and most consistent export surplus of prime-age players, **La Liga** stayed close to balanced, and the **Premier League** varied by season. Spending and international movement dropped after 2019, reflecting the pandemic's impact.
- In **La Liga**, transfer spending correlated strongly with final league rank (Spearman's ρ between -0.73 and -0.81), a Poisson regression model confirmed the relationship, explaining roughly 52% of rank variation.
- In the **Premier League**, the spending–rank relationship was inconsistent across seasons (significant in 2013–2014, not significant in 2015) and a Poisson model found no statistically significant effect, suggesting spending predicts success less reliably in a more competitive league.

## How to View the Notebook

Open `transfer_patterns_in_european_football.ipynb` in Jupyter Notebook, JupyterLab, VS Code, Google Colab or else to view the full analysis with code, visualizations, and commentary.

