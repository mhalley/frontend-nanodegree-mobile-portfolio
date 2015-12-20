## Website Performance Optimization portfolio project

###Getting Started

To run frontend-nanodegree-mobile-portfolio, go to [http://mhalley.github.io/frontend-nanodegree-mobile-portfolio/](http://mhalley.github.io/frontend-nanodegree-mobile-portfolio/) or clone the repository to your machine: [https://github.com/mhalley/frontend-nanodegree-mobile-portfolio](https://github.com/mhalley/frontend-nanodegree-mobile-portfolio).

To run the pizza animations, open [Cam's Pizzeria](http://mhalley.github.io/frontend-nanodegree-mobile-portfolio/views/pizza.html). Scrolling up and down will cause the pizzas in the background to dance around on the page. Changing the size of the pizza on the slider will cause the pizzas next to the pizza names to resize.


###Optimizations

####Part 1: Optimize PageSpeed Insights score for index.html

- Added media attribute to print.css so won't load unless printing.
- Included CSS in index.html to avoid calls off the server.
- Removed Google Fonts to avoid scripting call to external server.
- Added asynch attribute to JavaScript files that were not essential for initial rendering.
- Placed Google Analytics script at bottom of page so wouldn't hinder rendering of above fold content 
- Resized large photos to needed dimensions.

####Part 2: Optimize Frames per Second in pizza.html
- Optimized resizePizzas function by saving repetitive requests for randomPizzaContainer class to a variable and removed costly dx calculations and simply used percent width.
- Optimized updatePositions function by saving repetitive requests for mover class to a variable and avoiding layout thrashing (because of Forced Synchronous Layout in a for loop) by saving request for scrollTop to a variable outside of the critical rendering path and saving math for 5 values generated in old calculation to an array that can be called by the for loop.
- Added will-change property to mover class to signal the browser that it should place pizzas on a different layer