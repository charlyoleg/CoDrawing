===============
CoDrawing Usage
===============

Quick start
===========

- Install Inkscape_ on your laptop.
- Install git_

- Clone the CoDrawing_ project from GitHub_::

  > git clone https://github.com/charlyoleg/CoDrawing

- Look the drawings located in the directory *studio/* with Inkscape_ or with a browser such as FireFox_.
- Choose a drawing that you want improve
- Create a new *SVG file* in the directory *studio/library/* with Inkscape_ and draw a new character or new small scene.
- Add a link in the main drawing to your new piece of work (check *Inkscape tips and tricks*)
- Commit your contribution

Inkscape tips and tricks
========================

Create an *picture link* to a *SVG* file
----------------------------------------

The native format of Inkscape_ is SVG_. A SVG_ document can embed an external picture with the format PNG_ or SVG_. Inkscape supports this SVG feature. But the Inkscape GUI only propose to create an *dynamic picture link* to *PNG* file. So you need to hack a little to create an *dynamic picture link* to *SVG* file. Let's day, you want to create a link to the *SVG* file *embed.svg* into the main *SVG* document *main.svg*:

 - with Inkscape, create *main.svg*
 - create *embed.svg* and export the *page* as *embed.png*::

    Inkscape menu > File > Export Bitmap...
    In the *Export Bitmap* window,
      Export Area: Select *page*
      Choose the filename
      Export

 - with Inkscape, open *main.svg* and import the *embed.png*::

    Inkscape menu > File > Import...
    In the *Import* window,
      Select the file *embed.png*
    In the pop-up window *png GDK pixbuf Input*,
      Link or embed image: Chose *link*

 - save the document *main.svg* and quit Inkscape
 - with a *text editor*, open *main.svg*
 - find the line containing the path to *embed.png*
 - change this path to *embed.svg*
 - save the modification and re-open *main.svg* with Inkscape

You see *embed.svg* inside *main.svg*! *main.svg* contains only a link to *embed.svg*. If you modify *embed.svg*, after re-opening *main.svg*, you will get the modifications:)

Notice that, if you directly import *embed.svg* with the Inkscape GUI, the contain of the file *embed.svg* is copied into the file *main.svg*. The modification of *embed.svg* won't be seen from *main.svg*.

SVG syntax
----------

We mostly rely on Inkscape_ to create the SVG_ files. So we don't really need to know about the SVG syntax. But because we hack a little the SVG documents with a *text editor*, we need some hints:

 - SVG comments::

    <!-- this is a comment -->

 - absolute path to an external SVG file::

    xlink:href="file:///home/charli/Bis/Project/CardanCo/Charlyoleg_Github/CoDrawing/studio/library/wild_pig.svg"

 - relative path to an external SVG file::

    xlink:href="library/wild_pig.svg"

Change the size of a SVG document
---------------------------------

The *page* of a SVG document defines the *official* border of the drawing. You can draw inside and outside the *page*. The limits of the page are you when you export the document and you select *page*. Also, when you create a dynamic link to a SVG document, the coordinates of the page are use to crop and place the imported picture. Usually, you use the space around the page to make draft and write comments.
After drawing an object, you usually want to resize the page to a small surrounding around this object. You can select the object and resize the page to it but you want get any space between the enveloping rectangle of the object and the page. Some people prefer adding some margins between the object and the page borders. If you want such margin, follow this procedure:

- draw a rectangle with a *transparent fill* where you want to get the page
- select this rectangle and resize the page::

    Inkscape top menu > File > Document Properties...
    In the *Document properties* window,
      Unfold *Resize page to content...*
      click on *Resize page to drawing or selection*

- Delete or move the rectangle outside the page

Git howto
=========

http://git-scm.com/documentation

Github howto
============

http://opentechschool.github.io/social-coding/

CoDrawing good practises
========================

- Enhance the whole picture by adding local modifications. Improve or add a character or an object. Avoid big figure that cover more than 20% of the complete surface.
- Use external link for each object or character to minimize versioning conflict.
- Add comments, suggestions and ideas in the reStructuredText_ document *docs/drawings.rst*.

Licensing
=========

To improve the efficiency and the accuracy of the licensing, when you create a new file, add in comment of the file (namely outside the *page* in a *SVG*) the following line::

    (C) YYYY  YourName  CC BY-SA 3.0

With *YYYY* the current year and *YourName* your real name, artist name or pseudo.

If you modify an existing file, add the current year if it is not yet present and add your name and pseudo::

    (C) 2012, 2013  Tom Grant, Lucas Spring  CC BY-SA 3.0
  

View the drawing evolution
==========================

The script *scr/drawing_evolution.py* will create a series of picture that show you easily the evolution of a drawing.

.. _reStructuredText : http://docutils.sourceforge.net/docs/user/rst/quickref.html
.. _CoDrawing : https://github.com/charlyoleg/CoDrawing
.. _Inkscape : http://inkscape.org/
.. _GitHUb : https://github.com/
.. _SVG : http://www.w3.org/Graphics/SVG/
.. _git : http://git-scm.com/
.. _PNG : http://www.libpng.org/pub/png/
.. _FireFox : http://www.mozilla.org



