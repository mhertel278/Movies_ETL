# Movies_ETL

## Resources
Python 3.7.9, jupyeter notebook 6.1.4, postgreSQL 11.10, pgAdmin 4.29

## Overview

The purpose of this project is to extract, transform, and load data about various movies from separate sources into a movies SQL database to make available for a hackathon.  I used a jupyter notebook to explore data scraped from the sidebars of movies' wikipedia pages into a JSON file.  Columns with equivalent data were combined, tv shows were dropped, null values dropped or replaced, data forms-such as dates in various formats and dollar amounts represented with words million or billion-were transformed and made more consistent, and data types were corrected.  From that cleaned data, a wiki_movies_df was created.

I then performed similar cleaning tasks on a csv file of movie metadata from from MovieLens and merged the kaggle and wikipedia movies dataframes.  I cleaned the merged dataframes by consolidating data from similar columns and dropping duplicate columns.  I then created a dataframed of ratings fore each movie pulled from a csv file also compiled by MovieLens.  This dataframe was merged into the existing dataframe of wiki and kaggle data.

Finally, I exported the merged movies_df and the ratings.csv to a SQL database for use in the hackathon.

I then refactored the code used to transform and clean all the data into a more concise function that could be used to extract, transform, and load data from these same sources for potential use for future hackathons.