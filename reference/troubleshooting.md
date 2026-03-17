# MyFavoriteAlbums Troubleshooting Guide
This guide helps you diagnose and fix common problems when running the MyFavoriteAlbums Shiny app.  
For setup instructions, see [Getting Started with My Favorite Albums](../tasks/run-the-app.md).
---
## App Will Not Launch
**Problem:** Clicking **Run App** does nothing or produces an error in the Console.

**Possible causes:**
- Required packages are not installed.
- The project folder is missing files.
- RStudio is not pointed at the correct working directory.
**Solution:**
1. Install all required packages:
```r
   install.packages(c("shiny", "dplyr", "tidyverse", "ggplot2"))
```

2. Confirm your working directory is the MyFavoriteAlbums project folder:
```r
   getwd()
```
   The output should end with `.../MyFavoriteAlbums`. If it does not, go to **Session - Set Working Directory - Project Directory**.

3. Confirm that all required files are present in the project folder. Open the **Files** pane in RStudio and check for:
   - `app.R`
   - `app_ui.R`
   - `app_server.R`
   - `albums_by_year.R`
   - `compare_bands.R`
   - `number_one_albums.R`
   - `fav_bands.R`
   - `data/album-rankings.csv`

4. If errors still exist, restart RStudio: **Session > Restart R**, then click **Run App** again.
---

## Error: `object 'album_data' not found`

**Problem:** The Console displays:
```
Error: object 'album_data' not found
```

**Cause:** The dataset was not loaded before a function tried to use it.

**Solution:** Load the dataset first, then run your function:
```r
album_data <- read.csv("data/album-rankings.csv")
```

---

## Error: `cannot open file 'data/album-rankings.csv'`

**Problem:** The Console displays:
```
Error: cannot open file 'data/album-rankings.csv': No such file or directory
```

**Cause:** The CSV file is missing, named incorrectly, or not inside the `data/` folder.

**Solution:** Confirm that your project folder matches this structure exactly:
```
MyFavoriteAlbums/
└── data/
    └── album-rankings.csv
```
If the file is in the wrong place, move it into the `data/` folder, then click **Run App** again.

---

## No Albums Appear for Selected Year

**Problem:** The app shows an empty table after selecting a year and clicking **Submit**.

**Possible causes:**
- The selected year does not exist in the dataset
- The `Year` column contains text instead of numbers
- The dataset is not loading

**Solution:** Run the following in the Console to see which years are available:
```r
unique(album_data$Year)
```
If the year you selected is not in the output, choose a year from the list that is returned. If the command itself errors, reload the dataset first:
```r
album_data <- read.csv("data/album-rankings.csv")
```
---

## App Window Opens but Shows No Content

**Problem:** The Shiny window opens but the tabs are empty.

**Possible causes:**
- Errors in R scripts that prevent the server from rendering output
- A required file is missing from the project folder

**Solution:**

1. Check the **Console** for red error text and address each error shown.
2. Confirm all required files are present (see the file list in [App Will Not Launch](#app-will-not-launch) above).
3. Restart RStudio and click **Run App** again.

---

## Changes to CSV Do Not Appear in App

**Problem:** After editing `album-rankings.csv`, the app still shows the old data.

**Cause:** Shiny loads data only when the app starts, not while it is already running.

**Solution:**
1. Stop the app by clicking the **Stop** button in the Console toolbar.
2. Save your CSV file.
3. Click **Run App** again.
