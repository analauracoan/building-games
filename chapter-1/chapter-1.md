# CHAPTER 1
## The canvas element

The canvas element provides scripts with a resolution-dependent bitmap canvas, which can be used for rendering graphs, game graphics, art, or other visual images on the fly.

The canvas allows us to draw primitive shapes like lines, circles, and rectangles, as well as images and text, and has been optimized for fast drawing. Browsers have started enabling GPU-accelerated rendering of 2D canvas content, so that canvas-based games and animations run fast.

### Drawing Rectangles
The canvas uses a coordinate system with the origin (0, 0) at the top-left corner of the canvas, x increasing toward the right, and y increasing downward.

![](/home/ana/Downloads/001_image_game-learn.png)

We can draw a rectangle on the canvas using the context’s rectangle methods:
•	 fillRect(x, y, width, height): Draws a filled rectangle
•	 strokeRect(x, y, width, height): Draws a rectangular outline
•	 clearRect(x, y, width, height): Clears the specified rectangular area and makes it fully transparent.

### Drawing Complex Paths
•	 beginPath(): Starts recording a new shape;

•	 closePath(): Closes the path by drawing a line from the current drawing point to the starting point;

•	 fill(), stroke(): Fills or draws an outline of the recorded shape;

•	 moveTo(x, y): Moves the drawing point to x, y;

•	 lineTo(x, y): Draws a line from the current drawing point to x, y;

•	 arc(x, y, radius, startAngle, endAngle, anticlockwise): Draws an arc at x, y with specified radius.

Using these methods, drawing a complex path involves the following steps:

1. Use beginPath() to start recording the new shape.
2. Use moveTo(), lineTo(), and arc() to create the shape.
3. Optionally, close the shape using closePath().
4. Use either stroke() or fill() to draw an outline or filled shape. Using fill() automatically closes any open paths.

### Drawing Text
The context also provides us with two methods for drawing text on the canvas:

•	 strokeText(text, x, y): Draws an outline of the text at (x, y);

•	 fillText(text, x, y): Fills out the text at (x, y),

### Customizing Drawing Styles (Colors and Textures)
We can style and customize the lines, shapes, and text on a canvas. We can
draw using different colors, line styles, transparencies, and even fill textures inside the shapes.

If we want to apply colors to a shape, there are two important properties we can use:

•	 fillStyle: Sets the default color for all future fill operations;

•	 strokeStyle: Sets the default color for all future stroke operations,

Both properties can take valid CSS colors as values. This includes rgb() and rgba() values as well as color constant values. For example, context.fillStyle = "red"; will define the fill color as red for all future fill operations (fillRect, fillText, and fill).

In addition, the context object’s createTexture() method creates a texture from an image, which can also be used as a fill style. Before we can use an image, we need to load the image into the browser. For now, we will just add an <img> tag after the <canvas> tag in our HTML file:

### Drawing Images

We can draw images and sprites on the canvas using the drawImage() method. The context provides us with three different versions of this method:

•	 drawImage(image, x, y): Draws the image on the canvas at (x, y);

•	 drawImage(image, x, y, width, height): Scales the image to the specified width and height and then draws it at (x, y);

•	 drawImage(image, sourceX, sourceY, sourceWidth, sourceHeight, x, y,
width, height): Clips a rectangle from the image at (sourceX, sourceY) with dimensions (sourceWidth, sourceHeight), scales it to the specified width and height, and draws it on the canvas at (x, y),

### Transforming and Rotating

The context object has several methods for transforming the coordinate system used for drawing elements.
These methods are

•	 translate(x, y): Moves the canvas and its origin to a different point (x, y);

•	 rotate(angle): Rotates the canvas clockwise around the current origin by angle (radians);

•	 scale(x, y): Scales the objects drawn by a multiple of x and y along the respective axes,

Apart from rotating and translating back, you can also restore the canvas state by first using the save() method before starting the transformations and then calling the restore() method at the end of the transformations.

## The audio element

The audio element has several other attributes, such as the following:

•	 preload: Specifies whether or not the audio should be preloaded;

•	 autoplay: Specifies whether or not to start playing the audio as soon as the object has loaded;

•	 loop: Specifies whether to keep replaying the audio once it has finished,

There are currently three popular file formats supported by browsers: MP3 (MPEG Audio Layer 3), WAV (Waveform Audio), and OGG (Ogg Vorbis).