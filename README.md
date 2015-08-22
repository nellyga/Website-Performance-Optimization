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
#####saving more than 100 mss  line 452
function changePizzaSizes(size) {
      //moved these lines out of the 4 loop, saving more than 100 ms
      var dx = determineDx(document.querySelectorAll(".randomPizzaContainer")[1], size);
      var newwidth = (document.querySelectorAll(".randomPizzaContainer")[1].offsetWidth + dx) + 'px';
      var pizzacount = document.querySelectorAll(".randomPizzaContainer").length;

      for (var i = 0; i < pizzacount; i++) {

          // previously the slower document.querySelectorAll(".randomPizzaContainer")[i].style.width = newwidth;
          document.getElementsByClassName("randomPizzaContainer")[i].style.width = newwidth;
      }
  }

  changePizzaSizes(size);
  ###############################################################################################################
  #### Outside the for statement/loop I declare the variable pizzasDiv,so the function only makes one DOM call
var pizzasDiv  line 476
#######changed number of mover pizzas from 200 to 100
// This for-loop actually creates and appends all of the pizzas when the page loads
for (var i = 2; i < 100; i++) {
  pizzasDiv = document.getElementById("randomPizzas");
  pizzasDiv.appendChild(pizzaElementGenerator(i));
}

####### Outside the for statement/loop I declare the variable pizzasDiv,so the function only makes one DOM call
var pizzasDiv line 477
// This for-loop actually creates and appends all of the pizzas when the page loads
for (var i = 2; i < 100; i++) {
  pizzasDiv = document.getElementById("randomPizzas");
  pizzasDiv.appendChild(pizzaElementGenerator(i));
}
###################################################################################################################

  ##### Outside the for statement/loop I declare the variable phase,so the function only makes one DOM call
  var phase  line 517
  for (var i = 0; i < itemsLength; i++) {
   phase = Math.sin(scrollPosition + (i % 5));
    items[i].style.left = items[i].basicLeft + 100 * phase + 'px';
  }
####################################################################################################################
The number of background pizzas should be reduced to at least 40 or 48, both multiple of the current cols value as well, to cover the most common screen resolutions. A better approach is to dynamically calculate the number of pizzas needed to fill the screen, based on browser window resolution.
line 541
document.addEventListener('DOMContentLoaded', function() {	
    var  cols = 8;
    var s = 256;
    //** Outside the loop */
    var movingPizzas = document.getElementById('movingPizzas1');
    for (var i = 0; i < 100; i++) {
        console.log(i);
        var elem = document.createElement('img');
        elem.className = 'mover';
        elem.src = "images/pizza.png";
        elem.style.height = "100px";
        elem.style.width = "73.333px";
        elem.basicLeft = (i % cols) * s;
        elem.style.top = (Math.floor(i / cols) * s) + 'px';
        movingPizzas1.appendChild(elem);
    }
    updatePositions();
});

###################################################################################################################



--------------------------------------------------------------------------------------------------------
Resources:
1. [Why Moving Elements With Translate() Is Better Than Pos:abs Top/left](http://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/)
2.[PageSpeed Tools](https://developers.google.com/speed/pagespeed/)
3.https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads
4. https://www.udacity.com/course/viewer#!/c-ud884-nd/l-1464158641/m-1558420368
5.* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
6. Udacity Website Performance optimiyation course https://www.udacity.com/course/viewer#!/c-ud884-nd/l-1464158641/m-1558420368, http://creativejs.com/resources/requestanimationframe/.
