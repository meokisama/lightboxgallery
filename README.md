<p align="center">
  <a href="https://meokisama.github.io">
    <img src="images/favicon.png" />
  </a>
</p>
<h1 align="center">Lightbox Photos Gallery</h1>

### Overview

Lightbox Photos Gallery is made up of three primary components:

- __The "main wrapper":__ The skinny little column on the right. Home to what little "regular" content you may have (header, footer, anything else you want to cram in there), as well as ...

- __The "thumbnails" section:__ A grid of thumbnails pointing to their respective full size images.

- __The "viewer":__ Basically the rest of the page, and basically where your full size images will show up when a thumbnail is clicked.

___Note:__ Only the main wrapper and the thumbnails section are actually present in index.html. The viewer will be dynamically created on page load._

### How it works:

Just add your thumbnails to the thumbnails section in the following format:
```
<article>
	<a class="thumbnail" href="path/to/fullsize.jpg">
		<img src="path/to/thumbnail.jpg" alt="" />
	</a>
	<h2>Title</h2>
	<p>Description.</p>
</article>
```
And that's it. Lightbox Photos Gallery will figure out the rest.

#### The _"data-position"_ attribute

As a full screen experience, the viewer will be subject to changes in its size and, consequently, its aspect ratio. Since your full size images are basically applied as backgrounds to the viewer itself, this means they'll probably get cropped. All is not lost, however, as you can use the optional __"data-position"__ attribute to control how the full size image is positioned within the viewer. To do this, simply add it to your thumbnail's ```<a>``` element and set it to any valid _"background-position" value_. For example, this:
```
<a class="thumbnail" href="path/to/fullsize.jpg" data-position="top left">...</a>
```
... positions this particular full size image in the top left corner of the viewer (as opposed to its center, the default), effectively limiting cropping to everything but the top left corner.

### Keyboard shortcuts

Lightbox Photos Gallery is set up to respond to the following keyboard shortcuts:

- __Left Arrow:__ Go to previous image.
- __Right Arrow: Go__ to next image.
- __Up Arrow:__ Go to image above the current one in the thumbnails section.
- __Down Arrow:__ Go to image below the current one in the thumbnails section.
- __Space:__ Go to next image.
- __scape:__ Toggle the main wrapper.

___Note:__ All keyboard shortcuts are disabled when the "xsmall" breakpoint is active (since they don't really make a whole lot of sense there)._

### Other stuff

- The main wrapper can be moved to the left by changing the "misc.main-side" variable in ```assets/sass/libs/_vars.scss``` to "left" (and of course recompiling your CSS).

- Additional tweakable settings can be found at the top of ```assets/js/main.js```, but be aware most of these need to sync with certain Sass variables (see comments for details).