The data set contains three main files that are pre-processed versions of a larger data set from Spotify.com. 

Spotify_Metadata.csv:

This file contains information about 1420 song tracks on Spotify, including track name, artist, the URI (unique reference to identify the track on Spotify), and the mood(s) associated with the song. The mood(s) feature has been assigned to each track manually as a way to label the type of activities to which the track is best suited. The index column provides the unique key for each track and corresponds to the track index values in the other files in this archive.

--------------------------------------

Spotify_Numeric.csv:

This file represents each song track (same index as in "Spotify_Metadata.csv") using 13 numeric musical and acoustic features. For our purposes, we consider these features and "content" features that describe the song track. So, songs with similar features would represent similar songs acoustically. Note that the feature values in this data set have been normalized to be within the scale of [0,1] and thus they are not the same as the "raw" values of these features in the original Spotify data. You can review to the following reference document that describes the meaning of each of these features (along with other available features):

https://developer.spotify.com/documentation/web-api/reference/#/operations/get-audio-features

--------------------------------------

Spotify_Users.txt:

This file contains a list of 20 hypothetical user playlists (one on each line). each playlist contains a minimum of 10 song tracks with each song identified by its index value (corresponding to "Spotify_Metadata.csv" and "Spotify_Numeric.csv"). These user playlists are used to generate user profiles for input into a recommender system or as test users for the purpose of evaluating recommendation effectiveness. 

--------------------------------------