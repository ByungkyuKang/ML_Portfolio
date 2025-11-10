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

Day 4: Numeric/Categorical statistics and simple comparisons (group statistics, percentage tables)
📅 Date: 11/07/2025
🎯 Goal: Summarize precise figures (counts and percentages) for each group (such as Gender, Pclass, Title, etc.)

🛠️ Key Exploratory Focus Areas:
    - Compare survival rate differences between males and females
    - Analyze survival rates and passenger counts by the combination of passenger class (Pclass) 

✅ Result: 
    - Overall survival rate: 38.38%
    - Female survival rate: 74.2% vs Male: 18.9% — There is a significant difference in survival rates between genders.
    - Pclass=1 survival: 63.0% vs Pclass=2 suvival: 47.3 vs Pclass=3: 24.2% — There is a significant difference in survival rates based on passenger class.

Day 5: Organizing
📅 Date: 11/08/2025
🎯 Goal: Remove unnecessary lines and refactore the unclear parts.
✅ Result: Done.

Day 6: Feature Selection and Data Splitting
📅 Date: 11/10/2025
🎯 Goal: Select key features for the model and accurately split the dataset into training and validation sets.
🛠️ Key Steps:
    - Identify important features influencing survival (e.g., Pclass, Sex, Age, Fare, Embarked, Title).
    - Drop irrelevant columns such as PassengerId, Name, and Ticket.
    - Convert categorical variables (like Sex, Embarked, Title) into numeric form using encoding.
    - Split the dataset into training and validation sets using train_test_split from scikit-learn (e.g., test_size=0.2, random_state=12).
✅ Result:
    - Finalized feature set for modeling: ['Pclass', 'Sex', 'Age', 'Fare', 'Embarked', 'Title']
    - Data successfully divided into training (80%) and validation (20%) sets, ready for model training in the next step.