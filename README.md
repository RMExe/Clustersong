# Clustersong
## Abstract
The goal of this project is to explore a more novel way of categorizing music than genres.  While genres are powerful information and have adapted to a very fine level of granularity with sub-genres, they are not exclusively about how a song or album might sound.  Often, genres encapsulate important pieces of history and culture into them as certain markers.

Clustersong aims to explore the use of unsupervised machine learning to cluster songs together, and thus create new labels with a little more control on what exactly is input.  The hope with these labels is to create something that tries to bin similar sounding songs together, with less attachment to a band's history or even other songs on an album.  I have decided to call these new labels aural palettes, and while I do not think that I have conclusively found all of them, or even the proper granularity of them, the early results already show some trends.  The meat of this analysis can be found in [this notebook](./code/04-analysis-and-conclusions.ipynb)

## Dataset

The dataset used for creating the clusters totals to about 98,337 songs, with 23 features describing each song.  Everything in the dataset was queried through the [Spotify Web API](https://developer.spotify.com/documentation/web-api/).  Most of the song choices for the querying are based off my own collection, which does present some initial selection bias.  For the querying, I took the list of artists in my library and fetched them from the web-api endpoints to construct the dataset.  A more complete breakdown can be found in [the data collection notebook](./code/01_data_collection.ipynb).

## Methodology

