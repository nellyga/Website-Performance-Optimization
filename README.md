Website Performance Optimization  project

*************************************************************

Part 1: Optimize PageSpeed Insights score for index.html
I optimized the index.html by :

1. Minify CSS, HTML and JavaScript
2. Eliminate render-blocking JavaScript and CSS in above-the-fold content
3. Optimize images by replacing them with optimized versions of them
4. Leveraging browser caching using max-age attributes
5. Using "async" for non -render blocking javascript
6. inlining CSS

**********************************************************************

Part 2: Optimize Frames per Second in pizza.html
Ensuring a consistent frame rate of 60fps 

1. reducing the number of pizzas created to 20 (line 530)
2. usng translate instead of basic left positioing (line 510): 
items[i].style.transform = 'translateX(' + (100*phase) + 'px)';
3. moving the calculation of a big number ouside the loop (line 506) : 
var number=document.body.scrollTop / 1250;

--------------------------------------------------------------------------------------------------------
Resources:
1. [Why Moving Elements With Translate() Is Better Than Pos:abs Top/left](http://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/)
2.[PageSpeed Tools](https://developers.google.com/speed/pagespeed/)
3.https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads
4. https://www.udacity.com/course/viewer#!/c-ud884-nd/l-1464158641/m-1558420368
5.* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")

