# Create a Music Player Using JavaScript - GeeksforGeeks

As streaming is increasingly being adopted by users, online media players have become essential for consuming media on the internet. Music players allow one to enjoy music in any browser and supports a lot of the features of an offline music player.  
We will be creating a music player with a clean user interface that can be used to play music in the browser. We will also implement features like seeking and volume control. HTML has several methods in the HTMLMediaElement interface that can be used to play audio files and control its playback without using any other library.  
We will start by creating the HTML layout first that defines the structure of the player, make it look good by styling using CSS and then write the player logic for all the functions in JavaScript.  
**The HTML Layout**  
The HTML layout defines the element structure that would be shown on the page. The player can be divided into the following portions:

  * **Details Portion:** This section shows the details of the current track being played. It includes the track number, track album, track name and track artist.
  * **Buttons Portion:** This section shows the buttons that are used to control the playback of the track. It includes the play/pause button, the previous and next track buttons. They would have an onclick() method that calls a specific function defined in the JavaScript file.
  * **Sliders Portion:** This section contains the seek slider and volume slider that can be used to control the playback and volume.

We will be using FontAwesome icons to get the icons for all the buttons used on the page. The custom CSS and JavaScript we will write later is also linked in the file.  

## **The HTML Code is as follows:**

html

`<!DOCTYPE html>`

``<``html`` ``lang``=``"en"``>``

``<``head``>``

````<``title``>Simple Music Player</``title``>``

\` \`

````<``link`` ``rel``=``"stylesheet"``

````href``=``

``"<https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css>"``>``

\` \`

\` \`

````<``link`` ``rel``=``"stylesheet"`` ``type``=``"text/css"`` ``href``=``"style.css"``>``

``</``head``>``

``<``body``>``

````<``div`` ``class``=``"player"``>``

\` \`

\` \`

````<``div`` ``class``=``"details"``>``

````<``div`` ``class``=``"now-playing"``>PLAYING x OF y</``div``>``

````<``div`` ``class``=``"track-art"``></``div``>``

````<``div`` ``class``=``"track-name"``>Track Name</``div``>``

````<``div`` ``class``=``"track-artist"``>Track Artist</``div``>``

````</``div``>``

\` \`

\` \`

````<``div`` ``class``=``"buttons"``>``

````<``div`` ``class``=``"prev-track"`` ``onclick``=``"prevTrack()"``>``

````<``i`` ``class``=``"fa fa-step-backward fa-2x"``></``i``>``

````</``div``>``

````<``div`` ``class``=``"playpause-track"`` ``onclick``=``"playpauseTrack()"``>``

````<``i`` ``class``=``"fa fa-play-circle fa-5x"``></``i``>``

````</``div``>``

````<``div`` ``class``=``"next-track"`` ``onclick``=``"nextTrack()"``>``

````<``i`` ``class``=``"fa fa-step-forward fa-2x"``></``i``>``

````</``div``>``

````</``div``>``

\` \`

\` \`

````<``div`` ``class``=``"slider_container"``>``

````<``div`` ``class``=``"current-time"``>00:00</``div``>``

````<``input`` ``type``=``"range"`` ``min``=``"1"`` ``max``=``"100"``

````value``=``"0"`` ``class``=``"seek_slider"`` ``onchange``=``"seekTo()"``>``

````<``div`` ``class``=``"total-duration"``>00:00</``div``>``

````</``div``>``

\` \`

\` \`

````<``div`` ``class``=``"slider_container"``>``

````<``i`` ``class``=``"fa fa-volume-down"``></``i``>``

````<``input`` ``type``=``"range"`` ``min``=``"1"`` ``max``=``"100"``

````value``=``"99"`` ``class``=``"volume_slider"`` ``onchange``=``"setVolume()"``>``

````<``i`` ``class``=``"fa fa-volume-up"``></``i``>``

````</``div``>``

````</``div``>``

\` \`

\` \`

````<``script`` ``src``=``"main.js"``></``script``>``

``</``body``>``

``</``html``>``

## **The CSS Styling**

Using CSS we can style the different portions to make it more visually appealing:  

  
  

  * The flex layout is used to arrange the various elements of the player and align them to the middle of the page.
  * The track art image is given a fixed dimension and made rounded using the border-radius property.
  * The two sliders have been modified from their default look by using the appearance property. The height and background are changed to suit the color scheme. They are also given slight transparency that smoothly transitions to the full opacity using the transition property.
  * All the playback controls have their cursor property set so that it changes to a pointer whenever the mouse hovers over it.

css

`body {`

````background-color``: lightgreen;``

\` \`

\` \`

````transition: background-color .``5``s;``

`}`

\` \`

\` \`

`.player {`

````height``: ``95``vh;``

````display``: flex;``

````align-items: ``center``;``

````flex-``direction``: column;``

````justify-``content``: ``center``;``

`}`

\` \`

`.details {`

````display``: flex;``

````align-items: ``center``;``

````flex-``direction``: column;``

````justify-``content``: ``center``;``

````margin-top``: ``25px``;``

`}`

\` \`

`.track-art {`

````margin``: ``25px``;``

````height``: ``250px``;``

````width``: ``250px``;``

````background-image``: URL(``

````"<https://source.unsplash.com/Qrspubmx6kE/640x360>"``);``

````background-``size``: cover;``

````background-position``: ``center``;``

````border-radius: ``15%``;``

`}`

\` \`

`.now-playing {`

````font-size``: ``1``rem;``

`}`

\` \`

`.track-name {`

````font-size``: ``3``rem;``

`}`

\` \`

`.track-artist {`

````font-size``: ``1.5``rem;``

`}`

\` \`

\` \`

`.buttons {`

````display``: flex;``

````flex-``direction``: row;``

````align-items: ``center``;``

`}`

\` \`

`.playpause-track,`

`.prev-track,`

`.next-track {`

````padding``: ``25px``;``

````opacity: ``0.8``;``

\` \`

\` \`

````transition: opacity .``2``s;``

`}`

\` \`

`.playpause-track:hover,`

`.prev-track:hover,`

`.next-track:hover {`

````opacity: ``1.0``;``

`}`

\` \`

`.slider_container {`

````width``: ``75%``;``

````max-width``: ``400px``;``

````display``: flex;``

````justify-``content``: ``center``;``

````align-items: ``center``;``

`}`

\` \`

`.seek_slider, .volume_slider {`

````-webkit-appearance: ``none``;``

````-moz-appearance: ``none``;``

````appearance: ``none``;``

````height``: ``5px``;``

````background``: ``black``;``

````opacity: ``0.7``;``

````-webkit-transition: .``2``s;``

````transition: opacity .``2``s;``

`}`

\` \`

`.seek_slider::-webkit-slider-thumb,`

`.volume_slider::-webkit-slider-thumb {`

````-webkit-appearance: ``none``;``

````-moz-appearance: ``none``;``

````appearance: ``none``;``

````width``: ``15px``;``

````height``: ``15px``;``

````background``: ``white``;``

````cursor``: ``pointer``;``

````border-radius: ``50%``;``

`}`

\` \`

`.seek_slider:hover,`

`.volume_slider:hover {`

````opacity: ``1.0``;``

`}`

\` \`

`.seek_slider {`

````width``: ``60%``;``

`}`

\` \`

`.volume_slider {`

````width``: ``30%``;``

`}`

\` \`

`.current-time,`

`.total-duration {`

````padding``: ``10px``;``

`}`

\` \`

`i.fa-volume-down,`

`i.fa-volume-up {`

````padding``: ``10px``;``

`}`

\` \`

\` \`

``i.fa-play-``circle``,``

``i.fa-pause-``circle``,``

`i.fa-step-forward,`

`i.fa-step-backward {`

````cursor``: ``pointer``;``

`}`

The result of the HTML layout and CSS styling would give the following appearance:

![html\_css\_output][image-1]

## **JavaScript Logic of the player:**

The logic of the player is defined in the JavaScript file. There are several functions that work together to handle all the functions of the player.  
**Step 1:** Defining all the variables and accessing the HTML elements  
The required elements in the HTML layout that are to be dynamically changed are first selected using the querySelector() method. They are then assigned variable names so that they could be accessed and modified. Other variables that would be accessed throughout the program are also defined.

### Javascript

``let now_playing = document.querySelector(``".now-playing"``);``

``let track_art = document.querySelector(``".track-art"``);``

``let track_name = document.querySelector(``".track-name"``);``

``let track_artist = document.querySelector(``".track-artist"``);``

\` \`

``let playpause_btn = document.querySelector(``".playpause-track"``);``

``let next_btn = document.querySelector(``".next-track"``);``

``let prev_btn = document.querySelector(``".prev-track"``);``

\` \`

``let seek_slider = document.querySelector(``".seek_slider"``);``

``let volume_slider = document.querySelector(``".volume_slider"``);``

``let curr_time = document.querySelector(``".current-time"``);``

``let total_duration = document.querySelector(``".total-duration"``);``

\` \`

`let track_index = 0;`

``let isPlaying = ``false``;``

`let updateTimer;`

\` \`

``let curr_track = document.createElement(``'audio'``);``

\` \`

`let track_list = [`

````{``

````name: ``"Night Owl"``,``

````artist: ``"Broke For Free"``,``

````image: ``"Image URL"``,``

````path: ``"Night_Owl.mp3"``

````},``

````{``

````name: ``"Enthusiast"``,``

````artist: ``"Tours"``,``

````image: ``"Image URL"``,``

````path: ``"Enthusiast.mp3"``

````},``

````{``

````name: ``"Shipping Lanes"``,``

````artist: ``"Chad Crouch"``,``

````image: ``"Image URL"``,``

````path: ``"Shipping_Lanes.mp3"``,``

````},``

`];`

**Step 2:** Loading a new track from the tracklist  
All the tracks that have to be played are defined in the tracklist as objects. These objects contain properties like the name, artist, image and path to the track. Each of the tracks can then be accessed using its track index.  
To load a track, a function loadTrack() is defined which handles the following things:  

  * **Reset all the values of the previous track**  
	A resetValues() function is created which handles the resetting of the duration value and the slider to their initial values before a new track starts. This prevents the jumping of the seek slider while the new track loads.

  * **Loading the track**  
	The audio element is assigned a new source using its src property. It may be given any path from the filesystem or a URL. The load() method is then used on the audio element to get the track ready.

  * **Updating the track art to be shown**  
	The track art is fetched from the array and assigned with the help of the backgroundImage property.

  * **Updating the track details to be shown**  
	The track details are fetched from the array and assigned with the help of the textContent property.

  * **Adding event listeners to the track**  
	The media element has two event listeners added to it, the first one to update the current seek position and the second one to load the next track when the current track finishes.

  * **Setting a random colored background**  
	A coloured background is generated by randomising the red, green and blue values used and setting it as a color. The effect is animated by using the transition property on the background-color.

### Javascript

`function` `loadTrack(track_index) {`

\` \`

````clearInterval(updateTimer);``

````resetValues();``

\` \`

\` \`

````curr_track.src = track_list[track_index].path;``

````curr_track.load();``

\` \`

\` \`

````track_art.style.backgroundImage =``

````"url("`` ``\+ track_list[track_index].image + ``")"``;``

````track_name.textContent = track_list[track_index].name;``

````track_artist.textContent = track_list[track_index].artist;``

````now_playing.textContent =``

````"PLAYING "`` ``\+ (track_index + 1) + ``" OF "`` `\+ track_list.length;`

\` \`

\` \`

\` \`

````updateTimer = setInterval(seekUpdate, 1000);``

\` \`

\` \`

\` \`

````curr_track.addEventListener(``"ended"``, nextTrack);``

\` \`

\` \`

````random_bg_color();``

`}`

\` \`

`function` `random_bg_color() {`

\` \`

\` \`

````let red = Math.floor(Math.random() * 256) + 64;``

````let green = Math.floor(Math.random() * 256) + 64;``

````let blue = Math.floor(Math.random() * 256) + 64;``

\` \`

\` \`

````let bgColor = ``"rgb("`` ``\+ red + ``", "`` ``\+ green + ``", "`` ``\+ blue + ``")"``;``

\` \`

\` \`

````document.body.style.background = bgColor;``

`}`

\` \`

`function` `resetValues() {`

````curr_time.textContent = ``"00:00"``;``

````total_duration.textContent = ``"00:00"``;``

````seek_slider.value = 0;``

`}`

**Step 3:** Configuring the player buttons  
A function playTrack() handles the playing of the currently loaded track. The play() method of the HTMLMediaElement API is used for this function. The icon of the button also changes to the pause icon. This is done by using one of the icons from the FontAwesome library and inserting it using innerHTML.  
A function pauseTrack() handles the playing of the currently loaded track. The pause() method of the HTMLMediaElement API is used for this function. The icon of the button also changes back to the play icon. This is done by using one of the icons from the FontAwesome library and inserting it using innerHTML.  
These two functions are invoked depending on whether the track is currently playing or not. The playpause() function handles the actual play/pause control of the track.  
A function prevTrack() handles the loading of the previous track and moving the index backward. The index is reset to the last track when the index reaches the first track. The loadTrack() method defined above is used for loading the new track.  
Similarly, a function nextTrack() handles the loading of the next track and moving the index forward. The index is reset to the first track when the index reaches the last track. The loadTrack() method defined above is used for loading the new track.

### Javascript

`function` `playpauseTrack() {`

\` \`

\` \`

````if`` `(!isPlaying) playTrack();`

````else`` `pauseTrack();`

`}`

\` \`

`function` `playTrack() {`

\` \`

````curr_track.play();``

````isPlaying = ``true``;``

\` \`

\` \`

````playpause_btn.innerHTML = ``'<i class="fa fa-pause-circle fa-5x"></i>'``;``

`}`

\` \`

`function` `pauseTrack() {`

\` \`

````curr_track.pause();``

````isPlaying = ``false``;``

\` \`

\` \`

````playpause_btn.innerHTML = ``'<i class="fa fa-play-circle fa-5x"></i>'``;``

`}`

\` \`

`function` `nextTrack() {`

\` \`

\` \`

````if`` `(track_index < track_list.length - 1)`

````track_index += 1;``

````else`` `track_index = 0;`

\` \`

\` \`

````loadTrack(track_index);``

````playTrack();``

`}`

\` \`

`function` `prevTrack() {`

\` \`

\` \`

````if`` `(track_index > 0)`

````track_index -= 1;``

````else`` `track_index = track_list.length - 1;`

\` \`

\` \`

````loadTrack(track_index);``

````playTrack();``

`}`

**Step 4:** Configuring the sliders portion  
We will be setting up two sliders that control the seek slider and the volume slider.

  * **The seek slider**  
	The seek slider shows the current playback position on a slider by updating it with the current time of the track. A new function is created seekUpdate() which handles the updating of the seek slider relative to the current time of the track. The seek slider position is calculated and set using the value property.  
	Now, this function has to be called every time the track progresses further. This can be done by scheduling it to be updated every second. This can be done using the setInterval() method with an interval of 1000 milliseconds. This timer is cleared every time a new track is loaded.  
	This function also handles the changing of the time elapsed and the total duration of the track, which is updated every time this function fires. The minutes and the seconds are separately calculated and properly formatted to be displayed.

	 

  * **The volume slider**  
	The volume slider is used to display an set the current volume of the track. A new function is created setVolume() which handles the setting of the volume slider whenever the user changes it.

	 

### Javascript

`function` `seekTo() {`

\` \`

\` \`

\` \`

````seekto = curr_track.duration * (seek_slider.value / 100);``

\` \`

\` \`

````curr_track.currentTime = seekto;``

`}`

\` \`

`function` `setVolume() {`

\` \`

\` \`

````curr_track.volume = volume_slider.value / 100;``

`}`

\` \`

`function` `seekUpdate() {`

````let seekPosition = 0;``

\` \`

\` \`

````if`` `(!isNaN(curr_track.duration)) {`

````seekPosition = curr_track.currentTime * (100 / curr_track.duration);``

````seek_slider.value = seekPosition;``

\` \`

\` \`

````let currentMinutes = Math.floor(curr_track.currentTime / 60);``

````let currentSeconds = Math.floor(curr_track.currentTime - currentMinutes * 60);``

````let durationMinutes = Math.floor(curr_track.duration / 60);``

````let durationSeconds = Math.floor(curr_track.duration - durationMinutes * 60);``

\` \`

\` \`

````if`` ``(currentSeconds < 10) { currentSeconds = ``"0"`` `\+ currentSeconds; }`

````if`` ``(durationSeconds < 10) { durationSeconds = ``"0"`` `\+ durationSeconds; }`

````if`` ``(currentMinutes < 10) { currentMinutes = ``"0"`` `\+ currentMinutes; }`

````if`` ``(durationMinutes < 10) { durationMinutes = ``"0"`` `\+ durationMinutes; }`

\` \`

\` \`

````curr_time.textContent = currentMinutes + ``":"`` `\+ currentSeconds;`

````total_duration.textContent = durationMinutes + ``":"`` `\+ durationSeconds;`

````}``

`}`

**Step 5:** Starting the player  
The first track is loaded by calling the loadTrack() function. This will load the first track from the tracklist and update all the details of the track. The user can then start playing the track using the play button. The previous and next track button would load the previous and next track respectively and start playing them.  
The next track is automatically loaded when a track finishes playing. The user can seek to a position in the track using the seek slider. The volume can also be adjusted using the volume slider.

**Final Demonstration**  
The player is now ready to be used in any browser. New tracks can be added to the tracklist to play the music of your choice.

**Try Online:** [https://ide.geeksforgeeks.org/tryit.php/T3gdWUn4aX][1]  
**Source Code:** [https://github.com/sayantanm19/js-music-player][2]

HTML is the foundation of webpages, is used for webpage development by structuring websites and web apps.You can learn HTML from the ground up by following this [HTML Tutorial][3] and [HTML Examples][4].

CSS is the foundation of webpages, is used for webpage development by styling websites and web apps.You can learn CSS from the ground up by following this [CSS Tutorial][5] and [CSS Examples][6].

  
  
  



----

[1]:	https://ide.geeksforgeeks.org/tryit.php/T3gdWUn4aX
[2]:	https://github.com/sayantanm19/js-music-player
[3]:	https://www.geeksforgeeks.org/html-tutorials/
[4]:	https://www.geeksforgeeks.org/html-examples/
[5]:	https://www.geeksforgeeks.org/css-tutorials/
[6]:	https://www.geeksforgeeks.org/css-examples/

[image-1]:	https://media.geeksforgeeks.org/wp-content/uploads/20200417134245/chrome_cfLtTgiJ3y.png

#article
