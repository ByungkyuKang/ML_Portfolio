``` README.md
🔍 Day 1: Titanic Survival EDA
📅 Date: 11/03/2025
🎯 Goal: 
    - Understanding the data structure,
    - checking for missing values,
    - exploring basic distributions.
✅ Result: The dataset contains a total of 891 rows and 15 coloumns, and the key columns with missing values are deck(688), age(177), embarked(2), and embarked_town(2)

🔍 Day 2: Missing Value Handling & Feature Engineering
📅 Date: 11/04/2025
🎯 Goal: 
    - Age Missing Values (~20%): Imputed with the median (with an option for group-based imputation).
    - Deck Missing Values (High Volume): Due to lack of clear information, candidates for handling include filling with 'Unknown' or dropping the feature entirely.
    - Embarked Missing Values (Minority): Imputed with the mode (the most frequent value).
✅ Result: 
    - Age Grouped Median Imputation: Filled NaNs using the median Age calculated within each Pclass and Sex group. => 0 missing values remaining.
    - Embarked	Mode Imputation: Filled the 2 missing values with the Mode (most frequent value). => 0 missing values remaining.
    - deckUnchanged: Kept for now due to high missing rate. Future strategy (drop or 'Unknown') to be determined. => 688 missing values remain.

    📊 Missing Value Comparison 
    (Before vs. After)
    Feature     Before  After
    Age         177     0
    Embarked    2       0
    Cabin       688     688 (Unchanged)

🔍 Day 3: Exploratory Visualization & Correlation Analysis
📅 Date: 11/05/2025
🎯 Goal: 
    - Visualize key features to understand distribution and survival relationships.
    - Identify potential predictive features based on exploratory charts and correlation patterns.

🛠️ Key Exploratory Focus Areas:
    - Categorical Variables: Compare survival rates across groups (Sex, Pclass).
    - Numerical Variables: Analyze age and fare distributions and how they relate to survival.
    - Correlation Analysis: Review correlation heatmap to find meaningful numerical relationships relevant for model building.

🛠️ Expected Insights:
    - Female passengers show significantly higher survival rates compared to males.
    - First–class passengers have the highest survival rate, illustrating socioeconomic influence.
    - Younger passengers (especially children) tend to have better survival chances.
    
✅ Result: 
    - Female passengers show a significantly higher survival rate than males (around 74% vs 19%), guessing it's becuase of a strong "women and children first" effect.
    - First-class passengers have the highest survival rate, indicating social class likely influenced rescue priority.
    - Age is strongly associated with survival, with the youngest group (children) having the highest survival rate, while the 20-40 age range saw high fatality rates, though a resurgence in survival was observed among some middle-aged passengers (early 50s).
