# MyMovieDB - Data Analysis Project

**By:** Krish Rathore  
**Dataset:** TMDB Movie Database  
**Tools:** Python, Pandas, Matplotlib, Seaborn

---

## About the Dataset

The dataset contains information on 9,837 movies sourced from The Movie Database (TMDB). Each row represents one movie and includes the following columns:

- `Release_Date` — date the movie was released
- `Title` — movie name
- `Overview` — short description
- `Popularity` — TMDB popularity score
- `Vote_Count` — number of user votes
- `Vote_Average` — average user rating (out of 10)
- `Original_Language` — language the movie was made in
- `Genre` — one or more genres (comma separated)
- `Poster_Url` — link to movie poster image

---

## What Was Done

### Data Cleaning
- Dropped ~11 rows with missing values (less than 0.1% of the data)
- Fixed `Vote_Count` and `Vote_Average` from string to numeric
- Converted `Release_Date` from string to datetime format

### New Columns Created
| Column | Description |
|--------|-------------|
| `Year` | Year extracted from Release_Date |
| `Month` | Month number extracted from Release_Date |
| `Month_Name` | Month name (Jan, Feb...) |
| `Rating_Category` | Low / Average / Good / Excellent based on Vote_Average |
| `Popularity_Level` | Low / Medium / High / Viral based on Popularity score |
| `Is_English` | English or Non-English flag |
| `Decade` | Decade the movie was released in (e.g., 2010s) |

---

## Key Findings

**Ratings**
- Most movies are rated between 5.5 and 7.5. Average rating is around 6.2.
- Only a small percentage of movies are rated above 7.5 (Excellent category).
- Older classic films tend to have higher ratings because the less-known ones are not as widely catalogued on TMDB.

**Genres**
- Drama is the most common genre, followed by Comedy and Thriller.
- History, Documentary, and Music genres have the highest average ratings despite having fewer movies.
- Niche genres attract more engaged audiences who rate thoughtfully.

**Popularity**
- Spider-Man: No Way Home has the highest popularity score (5083), almost 1,200 points ahead of The Batman in second place.
- The vast majority of movies (over 90%) have a Low popularity score — most movies never go viral.
- Popularity and rating have almost zero correlation (r ≈ 0.07). A movie being popular does not mean it is good.

**Language**
- 77% of movies in the dataset are English-language.
- Surprisingly, Non-English movies have a slightly higher average rating than English movies.
- Japanese (ja), Spanish (es), and French (fr) are the next most represented languages.

**Release Trends**
- Movie production grew steadily from the 2000s and peaked in the 2010s.
- January and October see the highest number of releases — studios target the awards season window.
- There is a visible dip in production around 2020 due to COVID-19.

**Vote Count vs Popularity**
- Vote_Count and Popularity have a moderate positive correlation (~0.56). Popular movies tend to attract more votes.
- But Vote_Average is independent of both — you cannot predict rating from popularity or vote count alone.

**Hidden Gems**
- 15 movies were identified with rating >= 7.5, low popularity (bottom 30%), and at least 200 votes.
- Films like Ikiru (1952), Paths of Glory (1957), and Bicycle Thieves (1948) rank among the top hidden gems.
- These are classics that are critically acclaimed but not mainstream-popular.

---

## Project Structure

```
MyMovieDB_Project.ipynb   — Main analysis notebook (15 questions)
mymoviedb.csv             — Dataset
README.md                 — This file
```

---

## Questions Covered in the Notebook

1. Distribution of movie ratings
2. Movies by Rating Category (new column)
3. Top 10 most popular movies
4. Movies released per year
5. Monthly release trends
6. Genre distribution
7. Average rating by genre
8. Language breakdown
9. English vs Non-English ratings comparison
10. Popularity vs Rating scatter
11. Popularity Level distribution (new column)
12. Average rating trend over the years
13. Correlation heatmap
14. Movies per decade (new column)
15. Hidden gem movies (high rating, low popularity)
