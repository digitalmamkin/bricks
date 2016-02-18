# Bricks
A responsive, justified image layout plugin written in JavaScript, and inspired by Google Images.

## Demo
<a href="">View</a>

## Install

If you're not using NPM then you can download the files from this repo.

### NPM
```
npm install bricks-layout --save-dev
```

## Setup

#### Markup
```html
<div class="bricks">
	<img src="path/to/image.jpg">
	<img src="path/to/image.jpg">
	<img src="path/to/image.jpg">
	<img src="path/to/image.jpg">
</div>
```

#### Link to CSS
```html
<link rel="stylesheet" href="build/css/bricks.min.css">
```

#### Link to JS
```html
<script src="build/js/bricks.min.js"></script>
```

#### Initialize
```html
<script>
	// Select Bricks element in DOM
	var bricksElement = document.querySelector('.bricks');

	// Create instance of Bricks
	var bricksInstance = new Bricks(bricksElement);
</script>
```

#### Module Bundler
```js
// Require Bricks module
var Bricks = require('bricks');

// Select Bricks element in DOM
var bricksElement = document.querySelector('.bricks');

// Create instance of Bricks
var bricksInstance = new Bricks(bricksElement);
```

## Options
<table>
	<thead>
		<tr>
			<th>Name</th>
			<th>Type</th>
			<th>Default</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>afterLoad</td>
			<td>function</td>
			<td></td>
			<td>A callback function that is fired after the images are loaded and resized.</td>
		</tr>
		<tr>
			<td>animation</td>
			<td>boolean</td>
			<td>true</td>
			<td>If true, the images will animate after they load.</td>
		</tr>
		<tr>
			<td>animationDelay</td>
			<td>number</td>
			<td>50</td>
			<td>In milliseconds, the delay between the animation of each image.</td>
		</tr>
		<tr>
			<td>beforeLoad</td>
			<td>function</td>
			<td></td>
			<td>A callback function that is fired before the images are loaded or resized.</td>
		</tr>
		<tr>
			<td>imageClassName</td>
			<td>string</td>
			<td>bricks__img</td>
			<td>The class name that tells Bricks that the image is part of the layout.</td>
		</tr>
		<tr>
			<td>imageContainerElement</td>
			<td>string</td>
			<td>div</td>
			<td>The element that the images will be wrapped in, e.g: 'div', or 'span'.</td>
		</tr>
		<tr>
			<td>imageLoadedClassName</td>
			<td>string</td>
			<td>bricks__img--loaded</td>
			<td>The class name applied to the image when it is finished loading.</td>
		</tr>
		<tr>
			<td>margin</td>
			<td>number</td>
			<td>0</td>
			<td>The horizontal space between each image.</td>
		</tr>
		<tr>
			<td>maxHeight</td>
			<td>number</td>
			<td>250</td>
			<td>The maximum height for a row of images.</td>
		</tr>
	</tbody>
</table>

## API

#### .addNewImages(images)
This method is for adding more images to the Bricks element. You can fire this event on click, scroll, resize, etc...
<table>
	<thead>
		<tr>
			<th>Argument Name</th>
			<th>Type</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>images</td>
			<td>array</td>
			<td>An array of strings. The strings should be the `src` attribute for the image.</td>
		</tr>
	</tbody>
</table>

Example:
```js
// Array of image paths
var imageSources = ['images/1.jpg', 'images/2.jpg', 'images/3.jpg'];

// Call method on Bricks instance
bricksInstace.addNewImages(imageSources);
```

#### .removeImages(images)
This method is for removing images from the Bricks element. You can fire this event on click, scroll, resize, etc...
<table>
	<thead>
		<tr>
			<th>Argument Name</th>
			<th>Type</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>images</td>
			<td>array</td>
			<td>An array of image nodes.</td>
		</tr>
	</tbody>
</table>

Example:
```js
// Nodelist of images
var imageNodes = document.querySelectorAll('.bricks__img');

// Array of images to remove
var imagesToRemove = [imageNodes[2], imageNodes[5], imageNodes[9]];

// Call method on Bricks instance
bricksInstace.removeImages(imagesToRemove);
```

#### .reloadImages()
This method reloads all of the images in the Bricks element.<br>
<small>Note: The images are fully reloading/downloading, not just re-animating.</small>

Example:
```js
bricksInstance.reloadImages();
```

## Browser Support
- Chrome
- Firefox
- Safari
- IE 10+
- Edge

## License
#### MIT License
<a href="https://opensource.org/licenses/MIT">MIT</a>
&copy; 2016 Arjan Jassal

