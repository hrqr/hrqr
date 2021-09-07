# HRQR
Human Readable Quick Response Created by Valentin Heun


## Generator

If you want to embbed HRQR Codes in to your own webpage, you have two possibilities:

1. Go to hrqr.org enter your message and copy past the generated iframe.

2. Do the following steps:

Add the two scripts "HRQRLetterdatabase.js" and "HRQR.js" to your webpage.
If you want to stay conform with the main project, you can include the letter database directly from this project.

Example:
```
 <script src="https://raw.githubusercontent.com/hrqr/hrqr.github.io/master/HRQRLetterdatabase.js"></script>
 <script src="HRQR.js"></script>
```

Define a div tag where the tag should be drawn in to.

Example:
```
  <div id="svgDiv"></div>
```

Then call the javascript function:
```  
  drawHRQR("svgDiv","message");
```   

* "svgDiv" should be the ID of your div tag.
* "message" should be the message you want to encode in HRQR.


You can change some properties of the library by defining values in an object called: globalStates

Example:
```
globalStates.color = "0000FF";
```

The following properties can be changed:

The Width and Height allways should be identical:
* .width
* .height


This defines the left and top white space between the div boarder and the tag.

* .left
* .top


This thefines the color of the tag.

* .color


## Decoder
The decoder allows you to search for HRQR codes within images or video streams.

1. Load the libraries `HRQRDecoder.js` and `3rdparty/opencv.js` into your webpage.

2. Instantiate the library `let hrqr = new HRQR();`

3. Initialize the library once opencv is loaded `hrqr.init()`

4. Send a canvas image pixel stream to the library and in case there is a HRQR code within that image, the return is the content of the code. `let msg = hrqr.render(<canvasPixels>)`
