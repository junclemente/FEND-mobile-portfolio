# Website Performance Optimization portfolio project

The original repo for this project can be found here: [https://github.com/udacity/frontend-nanodegree-mobile-portfolio](https://github.com/udacity/frontend-nanodegree-mobile-portfolio)

The repo for the optimized site can be found here: [https://github.com/kajun/FEND-mobile-portfolio](https://github.com/kajun/FEND-mobile-portfolio)

The live site can be found here: [https://kajun.github.io/FEND-mobile-portfolio/](https://kajun.github.io/FEND-mobile-portfolio/)

## Optimization

Optimization of the original code is described below. The optimization resulted in a PageSpeed Insights score of *90* for mobile and *92* for desktop for **index.html**. For *pizza.html*, the javascript code was optimized to remove jank and achieve a site that runs at 60FPS.

### Optimizing **index.html** to improve PageSpeeds Insights
- The webfont "Open Sans" was removed since it was used for all text and therefore did not have any added value
- Both *style.css* and *print.css* files have been minimized and placed inline to prevent render blocking.
- Links to javascript files have been set to async and defer to prevent render blocking.
- Photos have been optimized for web use and resized as necessary


### Optimizing **pizza.html** and **main.js** to remove jank and run at 60FPS
- To optimize the side-scrolling background pizzas and remove jank, the total number of pizzas drawn is dynamically determined by the available viewport. At the same time, **will-change: transform** has been added to the *class* **movers**. 
- To optimize *changePizzaSizes()*, the for-loop has been optimized by moving **var dx** and **var newwidth** outside of the for-loop since the value stays the same through each iteration. Additionally, based on some research, *getElementById* and *getElementsByClassName* works more efficiently than *querySelector* and *querySelectorAll*. Therefore *var windowWidth, dx, and newwidth* have been changed to utilize *getElementsByClassName* and *getElementById*.
