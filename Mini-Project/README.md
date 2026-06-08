Project Documentation  
Movie Data Analytics Project Documentation
1.	Project Overview 
The goal of this project is to analyse the movie_metadata.csv dataset to uncover the key factors that drive a movie's success. We aim to identify trends in IMDb scores, gross revenue, and budget allocations to help production houses make data-driven decisions on which genres or directors are most likely to yield a high return on investment (ROI).

2. Tools Used 
-	Microsoft Excel 
-	Power BI 

 3. Dataset 
•	Source: movie_metadata.csv 
•	Key Columns: Movie_Title, Director_Name, Genres, Budget, Gross, IMDb_Score, Language, and Country

 4. Steps Followed 
•	Excel Power Query: Steps & Logic
In this stage, I focused on "Data Cleaning" to ensure the analysis wouldn't be skewed by errors. 
	Removing Duplicates: Removed duplicate movie entries based on the movie_title to ensure unique records. 
	Handling Missing Values: * Filtered out rows where Gross or Budget were null (since ROI cannot be calculated without these).
o	Replaced null values in Director_Name with "Unknown".
	Data Type Conversion: Ensured Budget and Gross were set to Currency and IMDb_Score to Decimal Number.
	Genre Splitting: Since the Genres column contained multiple values (e.g., Action|Adventure|Sci-Fi), I used Split Column by Delimiter ("|") to better categorize the data.
•	Power BI: Data Modeling & DAX
After importing the cleaned data into Power BI, I created specific logic to answer our problem statement. 
Calculated Columns:
	Profit: Profit = movie_metadata[gross] - movie_metadata[budget]
	ROI %: ROI % = (movie_metadata[Profit] / movie_metadata[budget]) * 100
	Score Category: A "Switch" logic to group movies into High, Medium, and Low based on IMDb scores.
o	Measures (Calculated on the fly):
	Average IMDb Score: Avg Score = AVERAGE(movie_metadata[imdb_score])
	Total Gross Revenue: Total Gross = SUM(movie_metadata[gross])
•	Visualization & Logic
I built the dashboard to provide a "Macro to Micro" view of the movie industry: 
	KPI Cards: Displaying Total Revenue, Average IMDb Score, and Total Movies analyzed. 
	Top 10 Directors by Gross: A Bar Chart to show which directors bring in the most money. 
	Budget vs. Revenue Correlation: A Scatter Plot to see if a higher budget actually results in a higher IMDb score.
	Genre Slicer: A tool allowing the user to filter the entire dashboard by genre (e.g., "Show me only Horror movies"). 

5. Key Insights 
•	Popularity vs. Profit: High audience engagement (votes/popularity) correlates strongly with profit, whereas a high budget alone does not guarantee financial success.
•	Genre Dominance: Action, Adventure, and Comedy are the most frequent genres, but smaller genres like Animation often show a higher average ROI %.
•	Language Bias: Over 90% of the top-grossing films are in the English language and produced in the USA, suggesting a strong geographic concentration of financial success.
•	Director Impact: A "Top 10 Directors" bar chart reveals that a small group of directors consistently maintains high IMDb scores regardless of budget size.

6. Screenshots 
Pre-processed File :
 Added in Mini_Project Documentation file.

Visualization File :
 Added in Mini_Project Documentation file.

7. Files Included 
-	Mini_Project Preprocessing.pbix – The cleaned data and Power Query logic.
-	Mini_Project Visualization.pbix – The interactive Power BI dashboard.
-	README.md – Project overview and instructions.

 8. How to Use 
-	Open Mini_Project Preprocessing.pbix to view the cleaned data. 
-	Open Mini_Project Visualization.pbix in Power BI Desktop to explore the visuals. 
