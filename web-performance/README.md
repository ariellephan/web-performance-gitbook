# Introduction to Web Performance



1.  Get familiar or revisit tools to solve performance
1.  Hands on examples 

Profiles

Timeline - layout invalidations

about:tracing for browser-level view


# Performance Strategy


## Setting Performance Budget


### Competition Baseline

Look at your competitors


### Average Baseline

[http://httparchive.org/](http://httparchive.org/)


## Metrics


### Page Weight



1.  Images make up 61% of an average website's page weight. \
— Optimize your PNG files. Consider reducing the quality of \
some JPEG files. \
— Take advantage of the new responsive image <picture> tag \
and srcset attribute to download appropriately sized \
images. \
— Set a budget and don't add image weight without removing \
another image.
1.  Too many custom fonts will quickly weigh your page down. \
— Set a font budget and consider not adding that second or third font. \
— Consider necessary font weights, as each font weight adds kilobyte weight to the font file. \
— While icon fonts are great, be mindful of the file size, as they can grow large quite quickly. Split the font up if one set is used for one section of the website, and another set for others. Also consider using inline SVGs instead, as you'll gain many of the benefits of icon fonts while only needing to load the required SVGs.
1.  JS frameworks, jQuery plug-ins, and CSS frameworks


### Number of HTTP 



1.  Reduce the number of HTTP requests. \
— Instead of serving up dozens of individual CSS and Java‐ \
Script files, concatenate them into single files. \
— Combine individual image files into a single image map or icon font. You'll find many great tools to do this for you \
automatically (Compass, Grunt/Gulp plug-ins). \
— Lazy-load assets not required for initial page load. This could be JavaScript that isn't needed until the user interacts with the page, or images that are far below the initial load \
Window.
1.  Increase the number of assets retrieved per round trip. \
— Splitting up your assets across different servers (or CDNs) will allow the browser to pull down more assets per round trip, as the limitations on concurrent connections is per server.


### Timing



1.  Time to 1st byte (TTFB) \
Time to first byte is the number of milliseconds between the browser requesting the web page, and the first byte being received by the browser. It is a measurement of the paths between the browser and the server, including DNS lookup, initial connection, and data receipt. This value is not the best judge of a website's per‐ formance, but it is a valuable number to keep an eye on.
1.  Time to start render \
A more useful time measurement is the "time to start render." This measurement is the time at which the user starts to see content on the page. This means that any blocking files have been loaded and the browser is able to start drawing out the DOM. You can improve this number by deferring blocking JS/CSS, putting critical CSS inline in the page head, replacing image assets with data URIs, and lazy-loading any blocking content that it loads after the document has completely rendered.
1.  Time to document complete \
Once all of the initially requested assets have been loaded, the document is considered to be "complete." Time to document com‐ plete doesn't include assets pulled in by JavaScript, so lazy-loading assets won't increase this metric.


## Hybrid Metrics


### PageSpeed Score

 \
PageSpeed is a website tool and Chrome extension made by Google that analyzes the performance and usability of a website, providing a score out of 100 and explaining ways that the user can improve that score. Tests include: \
• Presence of render-blocking JavaScript or CSS \
• Landing page redirects \
• Image optimization \
• File minification \
• Server response time \
• Server compression \
• Browser caching \
• Tap target size

• Viewport properly configured 

• Legible font sizes


###
Speed Index

[https://sites.google.com/a/webpagetest.org/docs/using-webpagetest/metrics/speed-index](https://sites.google.com/a/webpagetest.org/docs/using-webpagetest/metrics/speed-index)

The Speed Index is the average time at which visible parts of the page are displayed.  It is expressed in milliseconds and dependent on size of the view port.


# Performance Tests


## Lighthouse

[https://developers.google.com/web/tools/lighthouse/](https://developers.google.com/web/tools/lighthouse/)

Run audit in Chrome DevTools


## WebPageTest

[https://www.webpagetest.org](https://www.webpagetest.org)


## Automate Performance Regression

Run profiling for every commit - look for perf anti-patterns \
Automate this task and add to continuous integration


### browser-perf


### Perfjankie


# Development


## Quasar - Vue.js

[http://quasar-framework.org/guide/pwa-introduction.html](http://quasar-framework.org/guide/pwa-introduction.html)


## Dev Tools


### webpack bundle analyzer


## Checklist



1.  Route-based code-splitting
1.  Long-term asset caching
1.  Preloading



# Progressive Web Apps


## Stats

[https://www.pwastats.com/](https://www.pwastats.com/)


## Case Studies


### Pinterest

[https://medium.com/dev-channel/a-pinterest-progressive-web-app-performance-case-study-3bd6ed2e6154](https://medium.com/dev-channel/a-pinterest-progressive-web-app-performance-case-study-3bd6ed2e6154)


### Tinder

[https://medium.com/@addyosmani/a-tinder-progressive-web-app-performance-case-study-78919d98ece0](https://medium.com/@addyosmani/a-tinder-progressive-web-app-performance-case-study-78919d98ece0)


### Uber

[https://eng.uber.com/m-uber/](https://eng.uber.com/m-uber/)


### Twitter

[https://medium.com/@paularmstrong/twitter-lite-and-high-performance-react-progressive-web-apps-at-scale-d28a00e780a3](https://medium.com/@paularmstrong/twitter-lite-and-high-performance-react-progressive-web-apps-at-scale-d28a00e780a3)


### Treebo

[https://medium.com/dev-channel/treebo-a-react-and-preact-progressive-web-app-performance-case-study-5e4f450d5299](https://medium.com/dev-channel/treebo-a-react-and-preact-progressive-web-app-performance-case-study-5e4f450d5299)


# Debugging Web Performance


## Runtime Performance

[https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/)


## Page Load Performance

[https://developers.google.com/web/tools/chrome-devtools/network-performance/](https://developers.google.com/web/tools/chrome-devtools/network-performance/)


## Memory 

[https://developers.google.com/web/tools/chrome-devtools/memory-problems/](https://developers.google.com/web/tools/chrome-devtools/memory-problems/)

 
[https://blog.sessionstack.com/how-javascript-works-memory-management-how-to-handle-4-common-memory-leaks-3f28b94cfbec](https://blog.sessionstack.com/how-javascript-works-memory-management-how-to-handle-4-common-memory-leaks-3f28b94cfbec)

Puppeteer: trace perf issues

====================================================


# Courses

[https://app.pluralsight.com/library/courses/web-perf/table-of-contents](https://app.pluralsight.com/library/courses/web-perf/table-of-contents)

[https://app.pluralsight.com/library/courses/google-pagespeed-insights-web-performance/table-of-contents](https://app.pluralsight.com/library/courses/google-pagespeed-insights-web-performance/table-of-contents)

[https://app.pluralsight.com/library/courses/web-performance/table-of-contents](https://app.pluralsight.com/library/courses/web-performance/table-of-contents)

[https://app.pluralsight.com/library/courses/web-performance-tracking/table-of-contents](https://app.pluralsight.com/library/courses/web-performance-tracking/table-of-contents)


<!-- GD2md-html version 1.0β11 -->
