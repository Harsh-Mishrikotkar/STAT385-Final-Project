## Power Consumption Forecasting Project
1. Project goal
	- Predict the power consumption of Tetouan City using weather, flow, and time-based variables, then compare several statistical and machine learning models to see which works best.
	- We will build separate models for Zone 1, Zone 2, and Zone 3, because each zone has its own consumption target.

2. Main questions
	- How accurately can we predict power consumption for each zone using the available features?
	- Which variables matter most for prediction?
	- Do nonlinear models outperform linear regression?
	- Does adding time features like hour, day of week, or month improve performance?

3. Data to use
	- Dataset: Tetuan City power consumption.csv
	- Predictors: Datetime, Temperature, Humidity, Wind Speed, general diffuse flows, diffuse flows
	- Targets: Zone 1 Power Consumption, Zone 2 Power Consumption, Zone 3 Power Consumption

4. Recommended workflow
	* Step 1: Load and inspect data
		- Read the CSV file.
		- Check column names, data types, missing values, duplicates, and basic summary statistics.
		- Convert Datetime to a proper date-time format.
	* Step 2: Exploratory data analysis
		- Plot each zone’s power consumption over time.
		- Plot histograms and boxplots for the main variables.
		- Make scatterplots or correlation plots between predictors and targets.
		- Look for trends, seasonality, and outliers.
	* Step 3: Feature engineering
		- Extract useful time features from Datetime:
			- hour
			- day of week
			- month
		- Standardize numeric predictors when needed.
	* Step 4: Split the data
		- Use a train/test split based on time, not random splitting.
		- For example, use the earlier 70–80% of rows for training and the last 20–30% for testing.
		- This is important because random splitting can leak future information into training and make results look fake.
	* Step 5: Fit baseline models
		- Multiple linear regression for each zone.
		- Possibly include polynomial terms or interactions if needed.
		- Use this as your reference model.
	* Step 6: Fit improved models
		- Try several methods:
		- Ridge regression
		- Lasso regression
		- Elastic net
		- Random forest
		- Gradient boosting / XGBoost
		- These are reasonable because the dataset likely has nonlinear relationships and correlated predictors.
	* Step 7: Tune models
		- Use cross-validation on the training set.
		- Tune:
			- lambda for ridge/lasso/elastic net
			- number of trees and tree depth for random forest
			- learning rate, tree depth, and number of rounds for boosting
	* Step 8: Evaluate models
		- Use the same test set for all models.
			- RMSE
			- MAE
			- R^2
		- Compare results for each zone separately.
	* Step 9: Interpret results
		- Report which model performed best for each zone.
		- Interpret coefficient signs for linear models.
		- Use variable importance or SHAP for tree-based models.
		- Explain which weather/time factors seem most influential.
	* Step 10: Write the report
		- Report should include:
			- problem statement
			- exploratory analysis
			- model equations
			- tuning procedure
			- test performance comparison
			- interpretation
			- limitations and future improvements
5. Suggested model order
	- Baseline linear regression
	- Regularized regression
	- Random forest
	- Gradient boosting / XGBoost
	- That sequence shows progression from simple to more flexible methods, which professors usually like because it proves you tried multiple approaches.

6. Report structure
	- Introduction and project goal
	- Data description
	- Exploratory data analysis
	- Methods
	- Model tuning and selection
	- Results
	- Interpretation
	- Conclusion and future work
