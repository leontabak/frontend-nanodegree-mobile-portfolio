
## Project 4
## Leon Tabak
## 30 July 2015
## update 04 August 2015

This project includes HTML, CSS, and JavaScript. A copy of the
code that includes my modifications is available on GitHub: 

https://github.com/leontabak/frontend-nanodegree-mobile-portfolio

I modified the code in index.html and views/js/main.js.

HOW TO RUN CODE

I have placed this code on GitHub:

  https://github.com/leontabak/frontend-nanodegree-mobile-portfolio

To run the code:
  - open index.html in a browser
  - click on the link to Cam's Pizzeria that is at the bottom of the page
  - scroll up and down on the Cam's Pizzeria page
  - use the scroll bar that is part way down on that page to 
    change the size of the pizzas drawn on the page.

My goal on this project was to improve the performance of
the Web site. 

  - I measured the performance using Google's PageSpeed Insights.
    You can access this tool by visiting the site with your browser:

      https://developers.google.com/speed/pagespeed/insights/

    Then enter the URL for project. I ran an HTTP server on my
    laptop computer and used ngrok to make the site visible
    through the Internet.  

    I have since deployed the project on an HTTP server 
    that runs all of the time:

      http://www.countingfromzero.com/projects/frontend-nanodegree-mobile-portfolio/index.html

  - I measured performance using Google's Chrome
    browser. You can do examine the performance in the same
    way that I did by selecting View/Developer/Developer's Tools
    from the menu in Chrome. 
      * Open the Timeline tab and use the record button to the time
        required to redraw the pizza.html while scrolling. 
      * Open the Console tab to see messages logged by the 
        main.js script.

SUMMARY OF CHANGES

1) Optimization of PageSpeed Insights score for index.html

  - replace pizzeria.jpg with smaller version of image, scaled to match size
    at which it will be displayed

  - load scripts asynchronously

  - inline specifications of style

  - use Google's WebFont API to load fonts

2) Optimization of the frames per second rate in views/pizza.html

  - steps taken
    * create smaller version of pizza.png so that size of
      the image in file matches the size with which it will be 
      drawn

    * move repeated operations out of loops
      > program computes sines of just five angles---compute 
        these values before entering the loop, store values in an array, 
        and then retrieve values as needed for operations inside the loop

    * draw only as many pizzas as are needed to fill
      the screen with an array of pizzas---instead of
      200, draw 24

    * search through DOM to find and collect nodes
      that belong to a specified class just once
      (instead of repeating the operation during each
      pass through a loop)

    * replace divisions with additions
      > loop computes (i % 5) for successive values
        of i---create another variable j to repeatedly
        count from 0 to 4
      > loop computes floor(i/cols)---this is a step
        function whose value increases when i % cols === 0,
        so again a counter variable and addition can be
        used to eliminate a division

  - location of changes in views/js/main.js
    * creation of object to hold global values at line 21

    * definition of changePizzaSizes() beginning at line 703

    * definition of updatePostions() beginning at line 777

    * call to document.addEventListener() beginning at line 832

DIRECTIONS GIVEN TO ME

## Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository, inspect the code,

### Getting started

####Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ngrok 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

####Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js. 

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

### Optimization Tips and Tricks
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>

### Sample Portfolios

Feeling uninspired by the portfolio? Here's a list of cool portfolios I found after a few minutes of Googling.

* <a href="http://www.reddit.com/r/webdev/comments/280qkr/would_anybody_like_to_post_their_portfolio_site/">A great discussion about portfolios on reddit</a>
* <a href="http://ianlunn.co.uk/">http://ianlunn.co.uk/</a>
* <a href="http://www.adhamdannaway.com/portfolio">http://www.adhamdannaway.com/portfolio</a>
* <a href="http://www.timboelaars.nl/">http://www.timboelaars.nl/</a>
* <a href="http://futoryan.prosite.com/">http://futoryan.prosite.com/</a>
* <a href="http://playonpixels.prosite.com/21591/projects">http://playonpixels.prosite.com/21591/projects</a>
* <a href="http://colintrenter.prosite.com/">http://colintrenter.prosite.com/</a>
* <a href="http://calebmorris.prosite.com/">http://calebmorris.prosite.com/</a>
* <a href="http://www.cullywright.com/">http://www.cullywright.com/</a>
* <a href="http://yourjustlucky.com/">http://yourjustlucky.com/</a>
* <a href="http://nicoledominguez.com/portfolio/">http://nicoledominguez.com/portfolio/</a>
* <a href="http://www.roxannecook.com/">http://www.roxannecook.com/</a>
* <a href="http://www.84colors.com/portfolio.html">http://www.84colors.com/portfolio.html</a>
