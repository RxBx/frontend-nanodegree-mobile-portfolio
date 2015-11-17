# Website Performance Optimization portfolio project

##Introduction

For Project 4 in the Front End Development NanoDegree program, Udacity supplied HTML, CSS, JS & images for a portfolio site and apply optimazation methods from the Critical Rendering Path courses on Website Performance and Browswer Rendering.

I edited files and wrote original code to increase performance of index.html, and the JS performance during operations of pizza.html files.

###Loading and Examing the project

- You can view and analyze a live version of the project thru GitHub Pages:
rxbx.github.io/frontend-nanodegree-mobile-portfolio/

- You can examine the original files at the following link:
https://github.com/RxBx/frontend-nanodegree-mobile-portfolio
Downloading these files will also let you perform the pages locally on your computer.

##Optimizations

Here is a summary of optimizations I made to improve performance on the two specified pages:

###index.html
- inlined CSS subtract a "server round trip" from the load
- Used BEM method to turn some selector strings into class names
- minified the CSS
- used "media query" to put a "print" CSS sheet out of the Critical Rendering Path
- used "onload" and "async" to move non-critical Javascript out of CRP
- made Google Fonts load asynchronously after Page Speed Insights flagged them as a problem. (The method at https://github.com/typekit/webfontloader)
- reduced file size for 2 images after Page Speed Insights flagged them as a problem.

###pizza.html

Generally: used faster selector methods "getElementById" & "GetElementsByClassName" instead of "querySelector" etc.

####"slider"
- reduced complexity of calculation for new column widths when user activates "size slider"
- used a variable to capture all items in class before entering style loop (reduced look ups in loop)

####"updatePositions" / Background pizza animation
- reduced the number of animated pizzas built at load, from 200 to 40, since the great proportion of animated pizzas were off screen.
- for the updatePositions function, I moved a layout measurement out of a style.left loop.
- made a phase array that captured all the 5 possible values for phase, which I then used inside the style.left loop.