# LIRI
Find songs from Spotify, shows from Bands In Town, and movies from OMDB.

## Installation and Getting Started
1. `git clone https://github.com/adj-dev/liri-node-app.git`
2. `cd liri-node-app`
3. `npm install`
4. `touch .env` 
5. Place __credentials__ for Spotify and OMDB inside `.env` using the following syntax:
    ```
    SPOTIFY_ID=provided_credential
    SPOTIFY_SECRET=provided_credential
    OMDB_KEY=provided_credential
   ```
6. `node liri` _or_ `node liri.js`

### Where can I find said credentials?

_Spotify: https://developer.spotify.com/dashboard/login_

_OMDB: http://www.omdbapi.com/_

## A quick note on entering arguments
When adding any search term quotes are not recommended as they could throw off the APIs - though Liri will attempt to handle it. If there are no results Liri will let you know that none were found. 

## Commands
There are 6 different commands that the user can use.

### Find upcoming events for an artist/band
_Formerly known as_ `concert-this`

![event-gif](resources/liri-events.gif)

Takes a string that represents an artist/band name. LIRI uses the Bandsintown API to return a list of all upcoming events for said artist/band. If it is possible to buy tickets for the event LIRI will provide a link that will take you to where you can purchase them. 

### Search for a song on Spotify
_Formerly known as_ `spotify-this-song`

![song-gif](resources/liri-songs.gif)

Takes a string that represents the title of a song. LIRI uses Spotify to return a list of 5 songs related to the given song title. 
If no song is specified the user will be involuntarily "rick-rolled". 

### Get information about a movie
_Formerly known as_ `movie-this`

![movie-gif](resources/liri-movie.gif)

Takes a string that represents the title of a movie. LIRI uses OMDB to find information about the movie.

### Something incredibly mundane
_Formerly known as_ `do-what-it-says`

A rather useless feature. LIRI reads a file named random.txt and makes an API call based on the text it finds.

__Notice:__ there is no _GIF_ for this feature because you gotta install and run the application to find out exactly how incredibly mundane it truly is.

### HELP!

Provides a description of what LIRI is and directions for basic use. 

### QUIT

Exits from the application loop and ends the process.

## Special Features

When searching for a song the user has the option to specify a desired number of results by adding an additional argument: `r=[1-20]`. For example, the user could add `r=15` after writing out the song title and LIRI would return 15 results;  `billie jean r=2` would return 2 songs related to "billie jean". The user can ask for up to 20 results, and the default is 5. If the user attempts to use a number that is out of range, the default is used. Additionally, this argument can be added before or after the song title (it can even go in-between words of a song title as long as there are spaces separating all the words).
