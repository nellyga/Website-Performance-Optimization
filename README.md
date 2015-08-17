Website Performance Optimization  project

*************************************************************

##Optimization

###Index Page

The index page originally had a Google PageSpeed score less than 90 (85/100) for mobile. After making changes the score increased to [96 / 100]( the only thing that is preventing a score of 100/100 is Google's own analytics script.)

######CSS

[Inlined](https://developers.google.com/speed/pagespeed/module/filter-css-inline) all of the CSS into the head of the document and added the HTML [media="print"](https://developer.mozilla.org/de/docs/Web/HTML/Element/link) attribute to the external style sheet link for print styles.

######JS

Added the [HTML async attribute](https://developer.mozilla.org/en-US/docs/Games/Techniques/Async_scripts) to all script 
######Images

######Resized images that were too large and compressed all images with the [Kraken](https://kraken.io/web-interface) image compression tool.

**********************************************************************

Part 2: Optimize Frames per Second in pizza.html
Ensuring a consistent frame rate of 60fps 
<<<<<<< HEAD
for the project I used: Udacity Website Performance optimiyation course https://www.udacity.com/course/viewer#!/c-ud884-nd/l-1464158641/m-1558420368, http://creativejs.com/resources/requestanimationframe/.
=======

1. reducing the number of pizzas created to 20 (line 531)
2. usng translate instead of basic left positioing (line 510): 
items[i].style.transform = 'translateX(' + (100*phase) + 'px)';
3. moving the calculation of a big number ouside the loop (line 506) : 
var number=document.body.scrollTop / 1250;

>>>>>>> origin/master
--------------------------------------------------------------------------------------------------------
Resources:
1. [Why Moving Elements With Translate() Is Better Than Pos:abs Top/left](http://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/)
2.[PageSpeed Tools](https://developers.google.com/speed/pagespeed/)
3.https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads
4. https://www.udacity.com/course/viewer#!/c-ud884-nd/l-1464158641/m-1558420368
5.* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")

