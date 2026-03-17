# Conceptual Overview
What is my Favorite Albums?
My Favorite Albums is a data analysis, favorite album finding tool written in R where it was
made, allowing users to explore and analyze yearly rankings of music albums. The software
processes album ranking data stored in CSV files and produces summaries, comparisons, and
visualizations that help users better understand patterns in their music preferences over time.
By combining the capabilities of R with Shiny’s interface, my favorite albums can allow users to
both analyze data and explore results.

Audience 1: Music Fans

Overview
- This overview is intended for music fans or general users who want to analyze their
personal album rankings using My Favorite Albums. These users may have little or no
programming experience and may primarily interact with the software through the
Shiny web interface rather than directly with the underlying R code.
- For this audience, the goal of the overview is to explain the basic ideas behind the
software, what it analyzes, how the data is structured, and what kinds of insights the
tool can produce.

What the Software Does
My Favorite Albums analyzes yearly lists of favorite albums and identifies patterns within those
rankings. Users can upload or work with datasets containing album rankings across multiple
years. The software processes data and generates summaries reveal trends, such as:
• Albums that consistently rank highly across multiple years
• Artists that appear frequently in yearly rankings
• Changes in music preferences over time
• Comparisons between different album lists or years
The software is particularly useful for people who maintain yearly top album lists and want to
examine those lists more closely.

What the Software Does Not Do
While My Favorite Albums can analyze ranking data and generate insights from it, there are
several things it does not do. The software does not collect (auto) music data from streaming
services or music platforms. Users must already have their own album ranking data prepared in
a CSV file. The software also does not provide music recommendations or predict things about
future music trends, as its about findings. Even then, the software is not intended to be a full
music database or streaming platform. Instead, it focuses specifically on analyzing ranking
datasets provided by the user.
Key Concept- Album Ranking Data
The main reason behind My Favorite Albums is album ranking data. This data represents a list
of albums ranked in preference per year.
Each dataset typically includes information such as:
• The year of the ranking.
• The position of the album in the ranking.
• The album title.
• The artist name.
By analyzing multiple years of ranking data together, the software can identify long-term
patterns in listening preferences.

Audience 2: R Users and Developers

Who overview is for
- The second audience for this conceptual overview includes users who are familiar with R
or data science technologies, and may want to explore or extend the software’s
functionality. This includes students, researchers, and developers who are interested in
working with the code directly or modifying the software for their own analysis projects.
For this audience, the overview focuses on the tools, and technologies used to build the
application
