mathmode
========

Turns LaTeX math mode expressions into images

Installation
============

This code uses the `preview` LaTeX environment and GraphicsMagick, which you will need to install.  To do this on Debian, use the following command:

    sudo apt-get install texlive texlive-latex-extra imagemagick

On OS X, you can do this using MacPorts:

    sudo port install texlive texlive-latex-extra imagemagick
    
I have no idea how to do this on Windows, (but if you do, please open an issue).  I believe it may be possible using cygwin.

Once all that is done, you can then install the npm package directly:

    npm install mathmode

Here is an example of how to use the library.  Running the following command:

    require("mathmode")("e^{i \\pi} = -1").pipe(process.stdout)
    
Will write a png image of the famous Euler identity to stdout.


`require("mathmode")(expr[, options])`
--------------------------------------

Turns the LaTeX expression `expr` into an image encoded as a stream.  You can tweak this behavior a bit by specifying extra parameters via the `options` struct:

* `pdflatex_path`: A path the `pdflatex` executable.  Default `pdflatex`
* `imagemagick_path`: A path to image magick's convert tool.  Default `convert`
* `format`:  Resulting image format. Default `png`
* `packages`: A list of extra LaTeX packages to include.  Default `["amsmath"]`
* `macros`: A list of LaTeX preprocessor macros.  Default `""`
