# Js

\`\`\`\`\`\`let now\_playing = document.querySelector(".now-playing");  
let track\_art = document.querySelector(".track-art");  
let track\_name = document.querySelector(".track-name");  
let track\_artist = document.querySelector(".track-artist");  
let playpause\_btn = document.querySelector(".playpause-track");  
let next\_btn = document.querySelector(".next-track");  
let prev\_btn = document.querySelector(".prev-track");  
let seek\_slider = document.querySelector(".seek\_slider");  
let volume\_slider = document.querySelector(".volume\_slider");  
let curr\_time = document.querySelector(".current-time");  
let total\_duration = document.querySelector(".total-duration");  
let track\_index = 0;  
let isPlaying = false;  
let updateTimer;  
let curr\_track = document.createElement('audio');  
let track\_list = [  
{  
name: "Night Owl",  
artist: "Broke For Free",  
image: "Image URL",  
path: "Night\_Owl.mp3"  
},  
{  
name: "Enthusiast",  
artist: "Tours",  
image: "Image URL",  
path: "Enthusiast.mp3"  
},  
{  
name: "Shipping Lanes",  
artist: "Chad Crouch",  
image: "Image URL",  
path: "Shipping\_Lanes.mp3",  
},  
];  
function loadTrack(track\_index) {  
clearInterval(updateTimer);  
resetValues();  
curr\_track.src = track\_list[track\_index].path;  
curr\_track.load();  
track\_art.style.backgroundImage =  
"url (" \+ track\_list[track\_index].image + ")";  
track\_name.textContent = track\_list[track\_index].name;  
track\_artist.textContent = track\_list[track\_index].artist;  
now\_playing.textContent =  
"PLAYING" \+ (track\_index + 1) + " OF " \+ track\_list.length;  
updateTimer = setInterval(seekUpdate, 1000);  
curr\_track.addEventListener("ended", nextTrack);  
random\_bg\_color();  
}  
function random\_bg\_color() {  
let red = Math.floor(Math.random() \* 256) + 64;  
let green = Math.floor(Math.random() \* 256) + 64;  
let blue = Math.floor(Math.random() \* 256) + 64;  
let bgColor = "rgb(" \+ red + ", " \+ green + ", " \+ blue + ")";  
document.body.style.background = bgColor;  
}  
function resetValues() {  
curr\_time.textContent = "00:00";  
total\_duration.textContent = "00:00";  
seek\_slider.value = 0;  
}  
function playpauseTrack() {  
if (!isPlaying) playTrack();  
else pauseTrack();  
}  
function playTrack()  
curr\_track.play();  
isPlaying = true;  
playpause\_btn.innerHTML = '<i class="fa fa-pause-circle fa-5x"></i>';  
}  
function pauseTrack() {  
curr\_track.pause();  
isPlaying = false;  
playpause\_btn.innerHTML = '<i class="fa fa-play-circle fa-5x"></i>';  
}  
function nextTrack() {  
if (track\_index \< track\_list.length - 1)  
track\_index += 1;  
else track\_index = 0;  
loadTrack(track\_index);  
playTrack();  
}  
function prevTrack() {  
if (track\_index \> 0)  
track\_index -= 1;  
else track\_index = track\_list.length - 1;  
loadTrack(track\_index);  
playTrack();  
}  
function seekTo() {  
seekto = curr\_track.duration \* (seek\_slider.value / 100);  
curr\_track.currentTime = seekto;  
}  
function setVolume()  
curr\_track.volume = volume\_slider.value / 100;  
}  
function seekUpdate() {  
let seekPosition = 0;  
if (!isNaN(curr\_track.duration)) {  
seekPosition = curr\_track.currentTime \* (100 / curr\_track.duration);  
seek\_slider.value = seekPosition;  
let currentMinutes = Math.floor(curr\_track.currentTime / 60);  
let currentSeconds = Math.floor(curr\_track.currentTime - currentMinutes \* 60);  
let durationMinutes = Math.floor(curr\_track.duration / 60);  
let durationSeconds = Math.floor(curr\_track.duration - durationMinutes \* 60);  
if (currentSeconds \< 10) { currentSeconds = "0" \+ currentSeconds; }  
if (durationSeconds \< 10) { durationSeconds = "0" \+ durationSeconds; }if (currentMinutes \< 10) { currentMinutes = "0" \+ currentMinutes; }  
if (durationMinutes \< 10) { durationMinutes = "0" \+ durationMinutes; }  
curr\_time.textContent = currentMinutes + ":" \+ currentSeconds;  
total\_duration.textContent = durationMinutes + ":" \+ durationSeconds;  
}  
}
