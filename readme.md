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
Posted by SCOTT JEHL of filament group 07/19/2019 [The Simplest Way to Load CSS Asynchronously](https://www.filamentgroup.com/lab/load-css-simpler/)

----

### A CSS Snap-Points based carousel (and lightweight polyfill)

- Include dependencies, plus the css and js files in the src dir.
- Use the markup pattern below.
```
<div class="snapper">
	<div class="snapper_pane">
		<div class="snapper_items">
			<div class="snapper_item" id="img-a">
				<img src="a-image.jpg" alt="">
			</div>
			<div class="snapper_item" id="img-b">
				<img src="b-image.jpg" alt="">
			</div>
			<div class="snapper_item" id="img-c">
				<img src="c-image.jpg" alt="">
			</div>
			<div class="snapper_item" id="img-d">
				<img src="d-image.jpg" alt="">
			</div>
		</div>
	</div>
</div>
```
- Trigger an "enhance" event on a parent of the markup to initialize. You might do this on domready, as shown below:

  ```
  $( function(){
	  $( document ).trigger( "enhance" );
  });
  ```
- Also able to add thumbnails, pagination, multiple images, partial reveals

Snips from GitHub [repo](https://github.com/filamentgroup/snapper)

-----
