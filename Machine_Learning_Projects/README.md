🔍 Day 1: Titanic Survival EDA
📅 Date: 11/03/2025
🎯 Goal: 
    - Understanding the data structure,
    - checking for missing values,
    - exploring basic distributions.
✅ Result: The dataset contains a total of 891 rows and 15 coloumns, and the key columns with missing values are deck(688), age(177), embarked(2), and embarked_town(2)

🛠️ Day 2: Missing Value Handling & Feature Engineering
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