A “ticking” clock, that’s changing it’s hex color according to local time. The app was made with help of: HTML, CSS and JavaScript.


HTML
I have used the HTML to define the id-s that I’m working with:
  <div style="background-color:red" id="clock" >12:13:14</div>
  <div id="color-clock"></div>

CSS
Helped to customize the fonts and colors of the document and “ticking watch”
html, body {
  height: 100%;
  font-family: 'Coiny', cursive;
}
#clock {
  text-align: center;
  position: relative;
  top:0%;
  font-size:50px;
  color:black;
}

JavaScript
Here I wrote a function that’s getting the time using a new Date() method . The variables extracted are for hours, minutes and seconds.
The problem we faced was that, usually on watch, we have 6 characters but from 0 to 9 was generating just one, so we had to add a “0” for this range.
This function is changing is time with the setTimeout method to 1000 ms ( 1s).

function colorClock(){
var date = new Date();
var hours = date.getHours();
if (hours < 10) {
  hours ='0'+hours;
}
var minutes=
date.getMinutes();
if (minutes < 10) {
  minutes ='0'+minutes;
}
var seconds=
date.getSeconds();
if (seconds < 10) {
  seconds ='0'+seconds;
}
var clockFace=(hours+':'+ minutes+':'+seconds);
var hexColor = '#' + hours + minutes + seconds;
document.getElementById('clock').innerHTML = clockFace;
document.body.style.background = hexColor;
  
setTimeout(function() {
  colorClock();
}, 1000);
}

You can see the live preview accesing: https://negrut112.github.io/JS-TheColorWatch/





