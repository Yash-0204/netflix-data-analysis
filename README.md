
# Netflix Content Analysis (EDA)

This is an exploratory data analysis project I built using Python — mainly Pandas, Matplotlib, and Seaborn. The goal was to take a messy, realistic content dataset and actually dig into it: clean it up, ask real questions, and see what patterns show up.

I wanted this project to go beyond just making a few charts. So I focused on picking questions that would actually matter if I were working at a streaming company — things like content mix, growth over time, genre trends, and audience targeting.

## What I was trying to figure out
- Is the platform mostly Movies or mostly TV Shows?
- How has the content library grown year by year?
- Which genres and countries show up the most?
- What's the typical audience rating — is this more of an adult-focused catalog or family-friendly?
- How long are movies usually, and how many seasons do most TV shows get?
- Do Movies and TV Shows lean toward different genres?
- Is there any seasonal pattern in when content gets added?
- Do certain countries specialize in certain genres?

## Tools
Python, Pandas, Matplotlib, Seaborn, Google Colab

## About the data
The file is `netflix_titles.csv`, about 1,250 rows after cleaning, with the usual columns you'd expect — type, title, director, cast, country, date added, release year, rating, duration, genre, description.

I generated this dataset myself rather than pulling the real Netflix Kaggle one directly, mainly so I could freely share it without any licensing questions, but I built it to have the same kind of messiness real data has — missing directors, missing cast info, some duplicate rows, inconsistent country formatting. Basically I wanted the cleaning process to be genuinely necessary, not just for show.

## Cleaning it up
This took a good chunk of the actual work, honestly:
- Removed 15 exact duplicate rows
- Missing `director`, `cast`, and `country` values got filled with "Unknown" instead of dropped — almost half the rows were missing a director, so dropping them wasn't really an option
- Country names had extra whitespace and inconsistent casing in some rows, cleaned that up
- The `duration` column mixed "104 min" and "5 Seasons" in the same field, which doesn't work for any kind of numeric analysis — split it into two separate numeric columns
- `date_added` was just plain text, converted it to an actual date so I could pull out year and month

## What I found

Movies make up about 70% of the catalog (872 titles) versus TV Shows at 30% (378). Not too surprising, but worth confirming with actual numbers instead of assuming.

The growth trend was the most interesting part for me. Content additions basically exploded between 2016 and 2020 — that's clearly Netflix's big expansion phase — and then it flattens out after 2020, hovering around 140-175 titles a year. Makes sense if you think about it: at some point you're not adding a library from scratch anymore, you're maintaining one.

Action & Adventure, Sci-Fi & Fantasy, and Independent Movies are the top genres overall. But when I split it by content type, Movies and TV Shows actually favor different genres — Movies lean Action & Adventure, while TV Shows lean toward Comedies. I didn't expect that split going in.

On the geography side, the US produces way more content than anywhere else, with India a distant second, then UK and Canada. I made a heatmap to check this more carefully across genres, and the US comes out on top in literally every genre category — but India specifically stood out in Documentaries and Independent Movies, more than its overall ranking would suggest.

Ratings skew toward mature audiences — TV-MA, R, and TV-14 dominate, well ahead of anything family-oriented. So this reads as an adult-focused catalog overall.

For TV shows, most only make it to 1 season (around 120 out of 378), and it drops off fast after that — classic long-tail pattern, only a handful of shows reach 5+ seasons.

Average movie length came out to about 119 minutes, and honestly the distribution was pretty flat across the 60-180 minute range rather than clustering around a typical "90-100 min" movie length like I expected going in — worth noting since it's a bit different from what you'd usually see in real datasets.

## Screenshots
Chart images are in `/screenshots`, or you can just open the notebook directly on GitHub to see everything inline.
## Screenshots

### Content Growth Trend
![Growth Trend](Netflix%20Analysis%20Screenshots/Screenshot%202026-08-10%20143910.png)

### Movie Duration Distribution
![Movie Duration](Netflix%20Analysis%20Screenshots/Screenshot%202026-08-10%20143937.png)

### Top Countries Making Content
![Top Countries](Netflix%20Analysis%20Screenshots/Screenshot%202026-08-10%20143951.png)

### Top Genres by Content Type
![Genre by Type](Netflix%20Analysis%20Screenshots/Screenshot%202026-08-10%20144027.png)

### Seasonal Pattern by Month
![Seasonal Pattern](Netflix%20Analysis%20Screenshots/Screenshot%202026-08-10%20144037.png)

### Country-Genre Heatmap
![Heatmap](Netflix%20Analysis%20Screenshots/Screenshot%202026-08-10%20144045.png)


## Running it yourself
Easiest way is to open `Netflix_Analysis.ipynb` right here on GitHub — it'll render the code and charts without needing to run anything. If you want to actually run it, download the notebook and the CSV, keep them in the same folder, and open it in Google Colab or Jupyter.

## Author
Yash Srivastava — [LinkedIn](https://www.linkedin.com/in/yash-srivastava-93a95a36a)

