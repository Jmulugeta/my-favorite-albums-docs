# Analyzing Music Rankings with MyFavoriteAlbums R Scripts

*A Guide for Developers and Experienced R Users*

## Audience

This guide is for developers and experienced R users who want to call MyFavoriteAlbums functions directly in their own scripts to analyze album ranking data. You should be comfortable with R syntax, loading CSV files, and running scripts from the RStudio Console. You do not need experience with Shiny to follow this guide.

## What This Guide Covers

- Load and inspect the album rankings dataset
- Source the analysis scripts
- Generate yearly album rankings with `year_albums()`
- Identify top bands with `fav_bands()`
- Filter and sort album data manually

---

## Prerequisites

Before you begin:

- [Clone or download the MyFavoriteAlbums repository from GitHub](https://github.com/UW-Example-Student/MyFavoriteAlbums)
- Open project in RStudio (**File > Open Project** → select the MyFavoriteAlbums folder)
- Confirm that shiny, dplyr, tidyverse, and ggplot2 are installed:
```r
install.packages(c("shiny", "dplyr", "tidyverse", "ggplot2"))
```

---

## Task 1: Load the Album Rankings Dataset

All scripts rely on a shared data frame loaded from `album-rankings.csv` file in the `data/` folder. 

1. In the RStudio Console, run this:
```r
album_data <- read.csv("data/album-rankings.csv")
```

2. Preview the dataset to confirm it loaded correctly:
```r
head(album_data)
```

---

## Task 2: Source the Analysis Scripts

The analysis functions are defined across three R scripts: **albums_by_year.R**, **compare_bands.R**, and **fav_bands.R**. 

1. Run the following commands in the Console:
```r
source("albums_by_year.R")
source("compare_bands.R")
source("fav_bands.R")
```

* If you see an error message, make sure the file names match those in the project root and that your working directory is correct.*

---

## Task 3: Generate Rankings for a Specific Year

The `albums_by_year.R` script defines a function that filters and ranks albums for a given year. Use this function when you want a quick, sorted view of one year's data.

1. Call the function with the four-digit year you want to inspect:
```r
year_albums(2024)
```

*The Console prints a table of albums ranked for 2024, sorted from highest to lowest. Replace `2024` with any year present in the dataset.*

---

## Task 4: Identify Favorite Bands

The `fav_bands()` function ranks artists by how frequently their albums appear in the dataset. It accepts two arguments: a minimum number of albums an artist must have (integer), and a logical flag indicating whether to exclude EPs and live albums (`TRUE` or `FALSE`).

1. Run the function with your chosen arguments. For example, to see bands with at least five albums, excluding live records:
```r
fav_bands(album_data, min_albums = 5, exclude_eps = TRUE)
```

*The output lists artists whose studio albums appear at least five times, sorted by frequency of high rankings.*

---

## Task 5: Filter and Sort Album Data Manually

If you want to explore the data outside of the built-in functions, you can use standard dplyr verbs directly on the `album_data` data frame.

### Filter by artist

1. Replace `"Artist Name"` with the exact artist name as it appears in the dataset:
```r
filter(album_data, Artist == "Artist Name")
```

*The Console returns all rows where the Artist column matches the name you entered. Capitalization and spacing have to match exactly.*

### Sort by ranking

1. To sort all albums from best-ranked to worst-ranked:
```r
arrange(album_data, Ranking)
```

*You can pipe these two operations together to filter and sort in one step:*
```r
album_data |>
  filter(Artist == "Artist Name") |>
  arrange(Ranking)
```
