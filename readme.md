### Load CSS Asynchronously
- One of the most impactful things we can do to improve page performance and resilience is to load CSS in a way that does not delay page rendering.  We can achieve the effect of loading CSS asynchronously with a short line of HTML.

  ```
  <link rel="stylesheet" href="/path/to/my.css" media="print" onload="this.media='all'">
  ```
- If you happen to want the high-priority fetch that rel=preload provides (in browsers that support it), you can combine it with the above pattern, like this:
  ```
  <link rel="preload" href="/path/to/my.css" as="style">
  <link rel="stylesheet" href="/path/to/my.css" media="print" onload="this.media='all'">
  ```
From [The Simplest Way to Load CSS Asynchronously](https://www.filamentgroup.com/lab/load-css-simpler/)

----
