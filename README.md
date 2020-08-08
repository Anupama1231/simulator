

Manual Slideshow 

Just create many elements with the same class name:

Example
<img class="mySlides" src="img_snowtops.jpg">
<img class="mySlides" src="img_lights.jpg">
<img class="mySlides" src="img_mountains.jpg">
<img class="mySlides" src="img_forest.jpg">
And two buttons to scroll the images:

Example
<button class="w3-button w3-display-left" onclick="plusDivs(-1)">&#10094;</button>
<button class="w3-button w3-display-right" onclick="plusDivs(+1)">&#10095;</button>
And add a JavaScript to select images:

Example
var slideIndex = 1;
showDivs(slideIndex);

function plusDivs(n) {
  showDivs(slideIndex += n);
}

function showDivs(n) {
  var i;
  var x = document.getElementsByClassName("mySlides");
  if (n > x.length) {slideIndex = 1}
  if (n < 1) {slideIndex = x.length} ;
  for (i = 0; i < x.length; i++) {
    x[i].style.display = "none";
  }
  x[slideIndex-1].style.display = "block";
}
JavaScript Explained
First, set the slideIndex to 1. (First picture)

Then call showDivs() to display the first image.

When the user clicks one of the buttons call plusDivs().

The plusDivs() function subtracts one or  adds one to the slideIndex.

The showDiv() function hides (display="none") all elements with the class name "mySlides", and displays (display="block") the element with the given slideIndex.

If the slideIndex is higher than the number of elements (x.length), the slideIndex is set to zero.

If the slideIndex is less than 1 it is set to number of elements (x.length).


Automatic Slideshow

To display an automatic slideshow is even simpler.

You only need a little different JavaScript:

Example
var slideIndex = 0;
carousel();

function carousel() {
  var i;
  var x = document.getElementsByClassName("mySlides");
  for (i = 0; i < x.length; i++) {
    x[i].style.display = "none";
  }
  slideIndex++;
  if (slideIndex > x.length) {slideIndex = 1}
  x[slideIndex-1].style.display = "block";
  setTimeout(carousel, 2000); // Change image every 2 seconds
}
HTML Slides
The slides do not have to be images.

They can be any HTML content:

Slide 1
Lorem ipsum
Example
<div class="mySlides">
  <div class="w3-container w3-red">
  <h1><b>Did You Know?</b></h1>
  <h1><i>We plan to sell trips to the moon in the 2020s</i></h1>
</div>
Slideshow Caption
Snow, Norway
Add a caption text for each image slide with the w3-display-* classes (topleft, topmiddle, topright, bottomleft, bottommiddle, bottomright, left, right or middle):

Example
<div class="w3-display-container mySlides">
  <img src="img_snowtops.jpg" style="width:100%">
  <div class="w3-display-bottomleft w3-container w3-padding-16 w3-black">
    French Alps
  </div>
</div>
Slideshow Indicators
An example of using buttons to indicate how many slides there are in the slideshow, and which slide the user is currently viewing.


 
  
Example
<div class="w3-center">
  <button class="w3-button" onclick="plusDivs(-1)">&#10094; Prev</button>
  <button class="w3-button" onclick="plusDivs(1)">Next &#10095;</button>

  <button class="w3-button demo" onclick="currentDiv(1)">1</button>
  <button class="w3-button demo" onclick="currentDiv(2)">2</button>
  <button class="w3-button demo" onclick="currentDiv(3)">3</button>
</div>
Another example:

Example
<div class="w3-content w3-display-container">
  <img class="mySlides" src="img_nature.jpg">
  <img class="mySlides" src="img_snowtops.jpg">
  <img class="mySlides" src="img_mountains.jpg">
  <div class="w3-center w3-display-bottommiddle" style="width:100%">
    <div class="w3-left" onclick="plusDivs(-1)">&#10094;</div>
    <div class="w3-right" onclick="plusDivs(1)">&#10095;</div>
    <span class="w3-badge demo w3-border" onclick="currentDiv(1)"></span>
    <span class="w3-badge demo w3-border" onclick="currentDiv(2)"></span>
    <span class="w3-badge demo w3-border" onclick="currentDiv(3)"></span>
  </div>
</div>
Images as Indicators
An example of using images as indicators:



Example
<div class="w3-content" style="max-width:1200px">
  <img class="mySlides" src="img_nature_wide.jpg" style="width:100%">
  <img class="mySlides" src="img_snow_wide.jpg" style="width:100%">
  <img class="mySlides" src="img_mountains_wide.jpg" style="width:100%">

  <div class="w3-row-padding w3-section">
    <div class="w3-col s4">
      <img class="demo w3-opacity" src="img_nature_wide.jpg"
      style="width:100%" onclick="currentDiv(1)">
    </div>
    <div class="w3-col s4">
      <img class="demo w3-opacity" src="img_snow_wide.jpg"
      style="width:100%;display:none" onclick="currentDiv(2)">
    </div>
    <div class="w3-col s4">
      <img class="demo w3-opacity" src="img_mountains_wide.jpg"
      style="width:100%;display:none" onclick="currentDiv(3)">
    </div>
  </div>
</div>
Multiple Slideshows on the Same Page
To operate multiple slideshows on one page, you must class the members of each slideshow group with different classes:

Example
<div class="w3-content">
<img class="mySlides1" src="img_snowtops.jpg" style="width:100%">
<img class="mySlides1" src="img_lights.jpg" style="width:100%">
<img class="mySlides1" src="img_mountains.jpg" style="width:100%">
<img class="mySlides1" src="img_forest.jpg" style="width:100%">
</div>

<div class="w3-content">
<img class="mySlides2" src="img_la.jpg" style="width:100%">
<img class="mySlides2" src="img_ny.jpg" style="width:100%">
<img class="mySlides2" src="img_chicago.jpg" style="width:100%">
</div>
Animated Slides
Slide or fade in an element from the top, bottom, left or right of the screen with the w3-animate-* classes.


Example
<img class="mySlides w3-animate-top"    src="img_01.jpg">
<img class="mySlides w3-animate-bottom" src="img_02.jpg">
<img class="mySlides w3-animate-top"    src="img_03.jpg">
<img class="mySlides w3-animate-bottom" src="img_04.jpg">
Faded Animation
The w3-animate-fading class fades an element in and out (takes about 10 seconds).


Example
<img class="mySlides w3-animate-fading" src="img_01.jpg">
<img class="mySlides w3-animate-fading" src="img_02.jpg">
<img class="mySlides w3-animate-fading" src="img_03.jpg">
<img class="mySlides w3-animate-fading" src="img_04.jpg">


COLOR PICKER
colorpicker
HOW TO
Tabs
Dropdowns
Accordions
Side Navigation
Top Navigation
Modal Boxes
Progress Bars
Parallax
Login Form
HTML Includes
Google Maps
Range Sliders
Tooltips
Slideshow
Filter List
Sort List
SHARE


CERTIFICATES
HTML
CSS
JavaScript
SQL
Python
PHP
jQuery
Bootstrap
XML


