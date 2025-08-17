# Project Summary

This project explores serve performance in men's professional tennis tournaments using panel data (ATP matches 2010-2024). It is inspired by two costrasting upset matches in the 2025 season: 

Sinner vs. Alcaraz - French Open Final: Despite statistically worse serving, Alcaraz came back after being down two sets and a few match points. 
Opekla vs. Medvedev - Libéma Open: An unseeded Rielly Opelka served his way to upset the No. 1 seed with 24 aces, 0 double faults, and 72% of first serves in.

These matches raised the question:
Is it the match or is it the moment?
Can we quantify when a player wins because of a clear serve performance advantage vs. when something less measurable-pressure, momentum, or nerves-swings the outcome?

# Research Question

Can a player's serve performance statistically explain the outcome of a match, or are there matches that defy expectations?

# Data Source
This project uses publicly available match-level data from the [ATP Tour](https://www.atptour.com/) and compiled through [Jeff Sackmann's Tennis Data Repository](https://github.com/JeffSackmann/tennis_atp).

All data covers men’s singles matches from 2010 through 2024, including Grand Slams, ATP 1000, 500, 250, and Davis Cup matches. Certain tournamnets like the Davis Cup and the Olympics did not have accessable data and were removed in cleaning. 


# Methods

1. Data Cleaning and Preparation
   - ATP-level men's singles data from 2010-2024
   - merged serve, match, and player statistics
   - standardized serve-related performance metrics
2. Feature Engineering
  - Built composite serve performance index using Principal Component Analysis (PCA)
  - Created the metrics:
    - first/second serve win %
    - break points saved %
    - aces and double faults
    - controlled for surface, tournament, and round
3. Regression Modeling
  - Ran Fixed Effects regressions to explain variance in serve performance
  - adjusted for match-level and player-level fixed effects
  - Achieved adjusted R^2 up to 0.32
4. Interpretation and Vusulation
  - Used PCA loadings and coefficent signs to interpret serve strategy trade-offs
  - analyzed consistency vs. aggression dimensions of serving
    
# Tools used
- Python:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn (PCA, scaling)
  - statsmodels (fixed effects regression)

 # Key Findings
- Serve performance metrics do explain a meaningful portion of match outcomes, but defintely not all
- Serve strategies have different effects based on what surface a match is being played on and what round a player is in
- Some matches are statistically explainable; others are likely decided by mental/emotional factors
- The composite serve performance index reveals that dominant servers are defined more by power and point-outcome than consistency.
- The index loads most heavily on first serve win %, aces, and even double faults - indcating that high-performing servers tend to serve aggressively and risk faulting more.
- Surpisingly, first and second serve percentages contribute negatively, suggesting that trying to land more serves in isn't associated with a strong serve performance as much as  winning the points that matter. 

# Future Endevors 
- Extend model to predict match outcomes using logistic regression
- Train feedforward neural network to predict match outcomes
- Incorporate non-serve data (rallies, return stats, unforced errors)
- Create visulations for indivudal matches that over-or under- perform the model.

# License 
This proejct is open-source under the MIT License


