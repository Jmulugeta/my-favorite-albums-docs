# Getting Started with My Favorite Albums

*A Tutorial for New R Users and Music Fans*

## Audience

This tutorial is for music fans and people who are new to programming. You do not need any prior experience with R or RStudio to follow along. By the end, you will be able to open the My Favorite Albums app, explore album ranking data by year, and compare your favorite bands, all without writing a single line of code yourself.

## What This Tutorial Covers

- Install R and RStudio on your computer
- Download and open the My Favorite Albums project
- Install the required packages
- Launch the Shiny web app
- Explore album rankings, compare bands, and view number-one albums

---

## Prerequisites
Before you begin complete the steps:

1. [Download and install R](https://cran.r-project.org/)
2. [Download and install RStudio](https://posit.co/download/rstudio-desktop/)
3. [Download the My Favorite Albums project files from GitHub](https://github.com/UW-Example-Student/MyFavoriteAlbums) by clicking the green **Code** button and selecting **Download ZIP**. Unzip the folder to a location you can locate with ease.

> **Note:** If you are not sure whether R is already installed, open RStudio and look at the Console panel. If you see a version number, R is already installed.

---

## Task 1: Open the My Favorite Albums Project in RStudio

An RStudio project keeps all your files organized in one place. Opening the project correctly ensures the app can find its data files.

1. Launch RStudio on your computer.
2. In the menu bar, click **File**, then click **Open Project**.
3. Navigate to the **MyFavoriteAlbums** folder you unzipped earlier, and click **Open**.

*You should now see the project files listed in the Files pane in the lower-right corner of RStudio, like: for example, `app.R`, `albums_by_year.R`, and a `data` folder.*

---

## Task 2: Install and Load the Required Packages

Packages are collections of extra tools that R does not include by default. My Favorite Albums uses four packages: **shiny**, **dplyr**, **tidyverse**, and **ggplot2**. You only need to install packages once. after that, you load them each time you open RStudio.

### Install the packages

1. In RStudio, click in the **Console** panel (lower-left).
2. Copy and paste the following code, then press **Enter**:
```r
install.packages("shiny")
install.packages("dplyr")
install.packages("tidyverse")
install.packages("ggplot2")
```


### Load the packages

1. In the Console, paste the following code and press **Enter**:
```r
library(shiny)
library(dplyr)
library(tidyverse)
library(ggplot2)
```

*The Console shows packages loading. If you see any red error messages, re-check that each install.packages() command ran without errors in  previous step.*

---

## Task 3: Launch the My Favorite Albums App

Now that the packages are loaded, you can start the web app.

1. In the **Files** pane (lower-right), click **app.R** to open it in the editor.
2. Click the **Run App** button at the top of the editor panel.

*A browser window  opens and displays the My Favorite Albums interface. You see a navigation bar at the top with tabs including **Albums by Year**, **Compare Bands**, and **Number One Albums**.*

## Task 4: View Album Rankings by Year

The Albums by Year tab lets you see which albums ranked highest in any given year.

1. Click the **Albums by Year** tab in the navigation bar.
2. Click **Submit** to apply your selection.


## Task 5: Compare Favorite Bands

The Compare Bands tab displays ranking data for two artists side by side so you can see which one appeared more consistently in the top rankings.

1. Click the **Compare Bands** tab.
2. Use the first dropdown menu to select your first band.
3. Use the second dropdown menu to select a second band.

## Task 6: View Number-One Albums

The Number One Albums tab shows every album that reached the top ranking position across all years in the dataset.

1. Click the **Number One Albums** tab.
2. Use the year dropdown to select a specific year, then click **Submit**.
3. Scroll through results to see each number-one album for that year.
