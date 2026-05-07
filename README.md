# Movie-platform-database-
The goal is to extract valuable insights and answer various business questions based on the dataset.

Setup Summary

- 100 records inserted (57 Movies, 43 TV Shows)
- 9 indexes created on frequently queried columns: type, country, release_year, director, rating, listed_in, date_added, casts, description

  Business Problems
Q1 — Movies vs TV Shows
Type   Count
Movie   57
TV Show 43

Q2 — Most Common Rating
Type    Most Common Rating Count
Movie   TV-14           14
TV      ShowTV-MA       37

Q3 — Movies Released in 2020
19 movies found including: Army of the Dead, Bird Box, Extraction, Gulabo Sitabo, Shakuntala Devi, White Tiger, and more.

Q4 — Top 5 Countries
Country           Content Count
🇮🇳 India               37
🇺🇸 United States       31
🇬🇧 United Kingdom      11
🇫🇷 France              4
🇪🇸 Spain               3

Q5 — Longest Movie
The Irishman — 209 minutes

Q6 — Content Added in Last 5 Years
39 items added from 2021–2023

Q7 — Content by Rajiv Chilaka
2 animated movies found: Rajiv Chilaka Film 1 (2019) and Rajiv Chilaka Film 2 (2020)

Q8 — TV Shows with >5 Seasons
Show                                                       Seasons
The Blacklist                                                  9
Grace and Frankie                                              7
The Crown, Peaky Blinders, Better Call Saul, Black Mirror      6 each


Q9 — Content per Genre
Top genres: Drama (83), Action (24), Thriller (20), Mystery (20), Comedy (22), Crime (26)

Q10 — Top 5 Years for India Content
Year           Count        Avg per Year
2020            17            2.13
2019            6              0.75
2021            6              0.75
2018            3              0.38
2022            2               0.25


Q11 — Documentary Movies
1 documentary found: Tiger King (Crime, Documentary)

Q12 — Content without Director
5 records: La Casa de Papel, Dil Dhadakne Do, Chilling Adventures, Tujhse Naraaz Nahi, Rekha ki Kahani

Q13 — Salman Khan Movies (Last 10 Years)
4 movies: Salman Action Flick (2021), Salman Star Saga (2021), Salman Khan Blockbuster (2020), Tujhse Naraaz Nahi (2019)

Q14 — Top 10 Actors in Indian Movies
Salman Khan & Saif Ali Khan lead with 4 appearances each, followed by Priyanka Chopra, Radhika Apte, Taapsee Pannu, Vikrant Massey with 3 each.

Q15 — Content Categorization (Bad/Good)
Category                   Count
Good                         91
Bad (contains kill/violence)  9

Query Optimization Applied

9 indexes created on all heavily queried columns — enabling index scans instead of full seq scans
EXPLAIN ANALYZE used on Q1, Q3, Q7, and Q15 — all showed execution times under 0.5 ms
Window functions (RANK() OVER) used in Q2 for efficient per-partition ranking
UNNEST + STRING_TO_ARRAY used in Q4, Q9, Q14 for efficient multi-value column parsing

