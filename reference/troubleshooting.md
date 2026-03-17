# MyFavoriteAlbums FAQ

## How do I launch the app?

1. Open the MyFavoriteAlbums project in RStudio (**File - Open Project**).
2. In the **Files** pane, click **app.R** to open it.
3. Click **Run App** at the top.

Then, now, A browser window opens showing the MyFavoriteAlbums interface.  
For a full walkthrough, see [Getting Started with My Favorite Albums](../tasks/run-the-app.md).

---
## Where does the data come from?
The app reads from `data/album-rankings.csv` in the project folder. The dataset contains  following columns:

**Example rows:**
| Column  | Type    | Description                                         |
|---------|---------|-----------------------------------------------------|
| Year    | integer | The year the ranking was published                  |
| Ranking | integer | The album's position in that year's list (1 = best) |
| Album   | string  | The album title                                     |
| Artist  | string  | The artist or band name                             |
| Rating  | integer | A personal rating score for the album               |
| Vinyl   | string  | Contains "v" if the owner has this album on vinyl   |
| EP      | string  | Contains "EP" if the release is an extended play    |
| Live    | string  | Contains "Live" if the release is a live recording  |
|--------------------------------------------------------------------------|
**Example rows:**

| Year | Ranking | Album                       | Artist              | Rating | Vinyl | EP | Live |
|------|---------|-----------------------------|---------------------|--------|-------|----|------|
| 1993 | 1       | August and Everything After | Counting Crows      | 10     | v     |    |      |
| 1994 | 3       | Unplugged in New York       | Nirvana             | 10     | v     |    | Live |
| 1997 | 3       | Dog on Wheels               | Belle and Sebastian | 10     | v     | EP |      |
---------------------------------------------------------------------------------------------------
---
## Why isn't the app loading?
Check the following, in order:

1. **Are all required packages installed?** Run this in the Console:
```r
   install.packages(c("shiny", "dplyr", "tidyverse", "ggplot2"))
```
2. **Is the CSV file in the right place?** Confirm that `album-rankings.csv` is inside the `data/` folder:
```
   MyFavoriteAlbums/
   └── data/
       └── album-rankings.csv
```
3. **Are there errors in the Console?** Look for red error text and address each one before trying again.

---
## Why don't I see albums for the year I selected?

Possible causes:

- The year you selected does not exist in the dataset. Run `unique(album_data$Year)` in the Console to see which years are available.
- The dataset did not load correctly. Confirm `album_data` is in your environment.
- The `Year` column contains text instead of numbers, which prevents matching. Open `album-rankings.csv` and confirm the Year column contains only four-digit integers with no quotes.

---

## What does the Number One Albums tab show?

The **Number One Albums** tab displays every album that achieved a ranking of 1 in the dataset, across all available years. Select a year from the dropdown and click **Submit** to filter the results.

---

## Can I add my own album rankings?

Yes. To add rankings to the dataset:

1. Open `data/album-rankings.csv` in a spreadsheet/text file.
2. Add new rows using the existing column order: `Year`, `Ranking`, `Album`, `Artist`, `Rating`, `Vinyl`, `EP`, `Live`.
3. Save the file.
4. Stop the Shiny app and click **Run App** again to reload the data.

> **Note:** The app loads data only when it starts, so you must restart it to see any changes to the CSV.
