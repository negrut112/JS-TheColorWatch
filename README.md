<p>A “ticking” clock, that’s changing it’s hex color according to local time. The app was made with help of: HTML, CSS and JavaScript.</p>
<br>
<p>You can see the live preview accesing: <a href="https://negrut112.github.io/JS-TheColorWatch/">https://negrut112.github.io/JS-TheColorWatch/</a></p>

<img src="https://i.imgur.com/FhC2TOs.jpg"></img>

<b>HTML</b>

I have used the HTML to define the id-s that I’m working with:<br>
&lt;div style=“background-color:red” id=“clock” &gt;12:13:14&lt;/div&gt;<br>
&lt;div id=“color-clock”&gt;&lt;/div&gt;</p>

<p><b>CSS</b><br>
  
Helped to customize the fonts and colors of the document and “ticking watch”<br>
html, body {<br>
height: 100%;<br>
font-family: ‘Coiny’, cursive;<br>
}<br>
#clock {<br>
text-align: center;<br>
position: relative;<br>
top:0%;<br>
font-size:50px;<br>
color:black;<br>
}<br>
<b>JavaScript</b><br>
Here I wrote a function that’s getting the time using a new Date() method . The variables extracted are for hours, minutes and seconds.<br>
The problem we faced was that, usually on watch, we have 6 characters but from 0 to 9 was generating just one, so we had to add a “0” for this range.<br>
This function is changing is time with the setTimeout method to 1000 ms ( 1s).</p>
<p>function colorClock(){<br>
var date = new Date();<br>
var hours = date.getHours();<br>
if (hours &lt; 10) {<br>
hours =‘0’+hours;<br>
}<br>
var minutes=<br>
date.getMinutes();<br>
if (minutes &lt; 10) {<br>
minutes =‘0’+minutes;<br>
}<br>
var seconds=<br>
date.getSeconds();<br>
if (seconds &lt; 10) {<br>
seconds =‘0’+seconds;<br>
}<br>
var clockFace=(hours+’:’+ minutes+’:’+seconds);<br>
var hexColor = ‘#’ + hours + minutes + seconds;<br>
document.getElementById(‘clock’).innerHTML = clockFace;<br>
document.body.style.background = hexColor;</p>
<p>setTimeout(function() {<br>
colorClock();<br>
}, 1000);<br>
}<br>
