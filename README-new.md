For index.html
- minified and inline css files
- removed webfont
- downloaded image files 
- removed inline style and resized images

For js/main.js
- To optimize the side-scrolling background pizzas, the total number of pizzas drawn is dynamically determined by the available viewport. At the same time, "will-change: transform" has been added to the class "movers". 
- To optimize "changePizzaSizes()", the for-loop has been optimized by moving "var dx and var newwidth" outside of the for-loop since the value stays the same through each iteration. Additionally, based on some research, getElementById and getElementsByClassName works more efficiently than querySelector and querySelectorAll. Therefore var windowWidth, dx, and newwidth have been changed to utilize getElementsByClassName and getElementById
