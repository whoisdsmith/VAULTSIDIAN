---
created: 2022-08-27T22:52:09 (UTC -04:00)
tags: []
source: https://towardsdatascience.com/visualizing-spotify-data-with-python-tableau-687f2f528cdd
author: Anne Bode
---

# Visualizing Spotify Data with Python and Tableau | by Anne Bode | Towards Data Science

---
## Create a dynamic dashboard using your streaming data & Spotify’s API

I didn’t need to do this project to find out that I’m still addicted to ‘[**Ribs**](https://open.spotify.com/track/0TEekvXTomKt3hdXDZxxeW)**’** by Lorde, but it was fun to work on nonetheless. See below to learn how you can easily replicate it using your own Spotify data!

[**Tableau Public Dashboard**](https://public.tableau.com/app/profile/anne.bode/viz/SpotifyPREMIUMDashboard/PremiumDashboard)  
[**Jupyter Notebook**](https://jovian.ai/abode118/spotify-data-prep)

![](https://miro.medium.com/max/1400/1*IdybzQcWJqLaECUpOm8j0g.png)

[https://public.tableau.com/app/profile/anne.bode/viz/SpotifyPREMIUMDashboard/PremiumDashboard](https://public.tableau.com/app/profile/anne.bode/viz/SpotifyPREMIUMDashboard/PremiumDashboard)

## Step 1: Request Data

Request a copy of your data from Spotify [**here**](https://www.spotify.com/account/privacy/). Be patient and wait a few days. _There is probably a way to request this data directly using Spotify’s API but that’s a project for another day!_

## Step 2: Prep Streaming/Library Data

Using the files Spotify has given us, we will now create one dataframe that includes all our streaming data PLUS whether each song is on our Library PLUS each song’s Spotify ‘URI’ (unique identifier — it’ll come in handy later)

Create **df_stream**:

Next, I cleaned up my ‘YourLibrary’ file from Spotify so that it just contained the “tracks” dictionary, surrounded by brackets [ ] and saved as a new file ‘YourLibrary1'. _Someone better at cleaning up json files could likely automate this step and use the original file._

Create **df_library**:

Create our final dataframe, **df_tableau:**

## Step 3: Create New Spotify Project

Log into your developer account [**here**](https://developer.spotify.com/dashboard). In your dashboard, create a new project. Once created, you can retrieve your ‘Client ID’ and ‘Client Secret.’ We’ll use these in Step 4.

## Step 4: Create Genre Dataframe using Spotify’s API

First we’ll use our Client ID and Client Secret to generate an access token so we can pull data from Spotify’s API. Note: this token has to be regenerated after one hour. I figured out how to do this using the help of [**this post**](https://stmorse.github.io/journal/spotify-api.html).

Now we’ll pull the artist and genres associated with each track_uri in our library and add to a dictionary _(check out Spotify’s_ [**_console_**](https://developer.spotify.com/console/) _to find out how to pull the data points you’re interested in)._

We’ll convert this dictionary to a dataframe (**df_genre**) and expand it so that each genre for each track/artist is in its own line (I used this solution). This will create **df_genre_expanded**.

We’ll then save **df_tableau** and **df_genre_expanded** as csv files that we can load into Tableau.

## Step 5: Loading Data into Tableau

Connect to your Excel file (MySpotifyDataTable.csv) as a data source. This should pull up your GenresExpandedTable.csv file on the left hand side as well. Drag the latter file over into the right hand side and add a relationship between the two tables. Make sure you create the relationship based on track_uri _(note: you may have to click the down arrow next to GenresExpandedTable.csv and click “Field names are in first row”)_.

![](https://miro.medium.com/max/1400/1*okkf8BiEpOGVfSTjjA4z6A.png)

## Step 6: Editing Fields in Tableau

We’ll add two calculated fields to our data table. We could have done this using Python but I wanted to experiment with Tableau.

1.  Convert **Ms Played** into **Minutes Listened**:  
    _[Ms Played]/60000_
2.  Convert **End Time** (UTC) to **End Time (Adj)** (your time zone, with Daylight Savings taken into account):  
    _IF [End Time] < DATE(2020–03–08) THEN DATEADD(‘hour’,-5,[End Time])  
    ELSEIF [End Time] < DATE(2020–11–01) THEN DATEADD(‘hour’,-4,[End Time])  
    ELSE DATEADD(‘hour’,-5,[End Time])  
    END_

## Step 7: Create Visualizations

[**Download the dashboard**](https://public.tableau.com/app/profile/anne.bode/viz/SpotifyPREMIUMDashboard/PremiumDashboard) to see how I created the visualizations below. Note they are all linked in the dashboard and can therefore filter each other down, which is pretty sick!

![](https://miro.medium.com/max/1400/1*Gj3Af_U9MKU2WI6QHbaD2A.png)

Dashboard filtered for just songs/artists with the genre ‘alt z’ — am I a cool Gen Z kid yet?

1.  **Top Artists**: most popular artists by minutes listened, with individual songs making up colorful segments
2.  **Artist Breadth**: number of songs by each artist I’ve listened to for >1 minute and >1 stream
3.  **Top Songs**: most popular songs by minutes listened
4.  **Genres**: all genres I’ve listened to, with size and color indicating count of streams
5.  **Listenership by Month**: self-explanatory _(edit 9/29: I converted the field “In Library” to a dimension from a measure, so that I could include it in a stacked bar chart to see how many total minutes I listened to each month, and of that how many were in my library)_
6.  **Listenership by Hour**: self-explanatory

## In Conclusion

There are a ton of interesting insights you can glean from analyzing your Spotify streaming and library data — especially when combined with additional data fields obtained via the Spotify API (i.e. genre). I learned that I REALLY liked Julien Baker this year and my love for Lorde knows no time limit. I listened to way too much of Adrianne Lenker’s ‘[**Gone**](https://open.spotify.com/track/1abuE8PRWIA2GAH1DqzfNl)**’** in August (#sadgirlvibes) but in December my top song was of course Mariah Carey’s ‘[**All I Want For Christmas Is You**](https://open.spotify.com/track/0bYg9bo50gSsH3LtXe2SQn)’. Now that I know how to connect to Spotify’s API, in future projects I want to check out the musical qualities of the songs/artists I listen to (beyond just genre). One field I am especially interested in is “danceability”, because whenever I am tasked with DJing a family road-trip my mother’s sole criteria is “something I could dance to.” Whatever that means.

Good luck analyzing your own listening history and keep jammin’ out to all your favorite songs from 2013!
