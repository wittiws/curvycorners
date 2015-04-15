## Official Website ##

http://curvycorners.net

## Introduction ##

Rounded boxes are a stock-in-trade of modern web page design. Unfortunately, some browsers still don't support them natively. This has obliged ingenious web designers to come up with alternative solutions. Typically these involve the cumbersome generation of specialized images, or alternatively javascript that needs special style-related parameters. Both these solutions involve a reduplication or scattering of style information. Many fail to support the various combinations of CSS border styles.

By contrast, curvyCorners provides a painless way to support legacy browsers, whilst at the same time enabling page designers to specify their styles entirely in CSS.

## Details ##

For those browsers with native rounded corners support, curvyCorners delegates all styling to the browser. For the rest, curvyCorners interprets the CSS and applies the styles at page load time, creating high-quality anti-aliased box corners on boxes surrounded by, and containing, image background content.

curvyCorners supports fluid width and height, background-image and background-repeat on the rounded box and its parent, almost all solid border configurations, and (with a modicum of script support) dynamic redrawing.

Typically, there is no need to generate extra script or background images. Simply design your page for Webkit/Safari/Chrome, and include the curvyCorners script. If a page requires certain items to be dynamically redrawn, the curvyCorners API makes this simple.

## Using it ##

There is a tutorial available at http://curvycorners.net. There is a manual, usage.html, included in the doc subdirectory of the repository.

## Contributing ##

curvyCorners is an open source project. If you want to contribute changes to the source code or make improvements etc. then please email me via the email address under Project Owners on the right.

## Downloading ##

You can download the latest version from the Downloads tab above. Make sure you download the file with the highest version number.

## Discussion ##

We have a Google Group! If you need help then I recommend you visit the Google group at http://groups.google.com/group/curvyCorners .

## Known Issues ##

See the KnownIssues page.

## New Issues and Bugs ##

If you have found a new issue or bug with the software please click on the [Issues tab](http://code.google.com/p/curvycorners/issues/list) above and report it.

## Members ##

If you plan on making changes to the code please copy the files in trunk to a sub-folder under branches. You can then checkout from there. Once you are happy with your changes and want them merged back into the trunk please request a code review by clicking the Request Code Review link under the source tab.