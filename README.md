# Clustersong
## Abstract
The goal of this project is to explore a more novel way of categorizing music than genres.  While genres are powerful information and have adapted to a very fine level of granularity with sub-genres, they are not exclusively about how a song or album might sound.  Often, genres encapsulate important pieces of history and culture into them as certain markers.

Clustersong aims to explore the use of unsupervised machine learning to cluster songs together, and thus create new labels with a little more control on what exactly is input.  The hope with these labels is to create something that tries to bin similar sounding songs together, with less attachment to a band's history or even other songs on an album.  I have decided to call these new labels aural palettes, and while I do not think that I have conclusively found all of them, or even the proper granularity of them, the early results already show some trends.  The meat of this analysis can be found in [the analysis notebook](./code/04-analysis-and-conclusions.ipynb), and is the reccomended destination.

## Dataset

The dataset used for creating the clusters totals to about 98,337 songs, with 23 features describing each song.  Everything in the dataset was queried through the [Spotify Web API](https://developer.spotify.com/documentation/web-api/).  Most of the song choices for the querying are based off my own collection, which does present some initial selection bias.  For the querying, I took the list of artists in my library and fetched them from the web-api endpoints to construct the dataset.  A more complete breakdown can be found in [the data collection notebook](./code/01_data_collection.ipynb).

## Methodology

### Cleaning
With data obtained, I set out to prep it for modeling.  The data was mostly pretty well formed, most of the missings that needed to be accounted for were simply a few tracks that were not in Spotify's library and thus had nothing to return.

### Exploratory Data Analysis
Before clustering and feature selecting, I explored the features available in the dataset to give myself a baseline expectation.  I wanted to know things like distribution of Key Centers, tempo, duration.  For a more thorough exploration, please check the [eda notebook](./code/02_eda.ipynb).

### Clustering
Now that I had a baseline understanding, I set out to actually cluster the data.  Specifically, I went with agglomerative clustering, because I feel it naturally already fits the data.  Clustering might be trying to get away from genre as the only classification, but it still often informs scructure and dividing lines, especially with how sub-genres differentiate themselves.  A breakdown of the clustering can be found in the [clustering notebook](./code/03-clustering.ipynb).

## Conclusions

This clustering is still pretty rudimentary, but shows a lot of promise already.  I decide that these clusters could be thought of as a kind of aural palette: the limited sonic qualities that are used to build a song, much like a painter might limit their palette for a more cohesive product.  Re-examining many of the categorical features already offers a wealth identifying features for each new aural palette.  For next steps, there should be a lot to gain both from diversifying the dataset more, and refining the clustering process.

When the clustering is more refined, some next steps I would like to do include training a model to fit to these new categories, and explore how these new aural palettes do end up intersecting with genres.  Questions to answer include: What genres span the most palettes? What genres are dominant in in what palettes?  Do bands that stick around for a long time end up moving around?  What about bands that are well known for rapidly changing styles?  How cohesive do albums tend to be under these new labels?

The full breakdown can be found in [the analysis notebook](./code/04-analysis-and-conclusions.ipynb).