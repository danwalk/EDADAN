# EDA - THE HOUSE ALWAYS WINS...most of the time

Data Science Student EDA Project

This project is to review popular betting patterns and discover the basic errors made by most people when it comes to sports betting.

The EDA is based on collecting scores and betting results from 3 different sports from the past 6 years, cleaning the data, uploading to mysql, visualising the data using workspaces, dashboards and stories in tableau and finally in streamlit/flask making the cleaned data available via API.

### Data Sources:

### NBA
https://masseyratings.com/nba/games

https://www.oddsportal.com/basketball/usa/nba/

### NFL
https://www.aussportsbetting.com/data/historical-nfl-results-and-odds-data/

### Football
http://www.football-data.co.uk/

Using webscraping and also from importing the CSV files available, the data was then cleaned and sent to a database in mysql calling the corresponding function from main.ipynb.

### The cleaning process includes:

1. Removing unwanted columns.
2. Adding multiple columns to include calculations such as Result, Favourite, ResultBetWin : 
      conditions = [(df['Result'] == "Win"),
      (df['Result'] != "Win")]
      values = [(df['TeamOdds']-1), -1]
      df['ResultBetWin'] = np.select(conditions, values)
3. Duplicating the DF to include all home and away teams in both columns without manipulating the scores and results obtained by each team, to then be able to filter each team individually later on in the process.
4. Reorder columns
5. Add columns with the country, league and season data that needs to be included when calling the function to be able to filter the data correctly later on in the process.

## Tableau

The database tables are then accessed via direct connection from Tableau to then visualize the data using 22 workspaces/graphics/charts, 8 dashboards and also made public from a storyboard:

https://public.tableau.com/app/profile/daniel.walker8090/viz/ComparisonLeaguesWINStraight/Story1

