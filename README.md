impress.js recompilation 
============

It's a recompilation of utilities that allows that the use of impress.js can be more comfortable

**FEATURES**

impress.js-progress by m42e https://github.com/m42e/impress.js-progress .

impress.js substeps by tehfoo https://github.com/tehfoo/impress.js .

impress presenter console by regebro https://github.com/regebro/impress-console .

mods by Talisantos https://github.com/Talisantos/impress.js .

HOW TO USE IT
---------------

impress.js-progress
===================

Add a div for progressbar and/or progress as you can see it here before impress initial div:

	<div class="progressbar"><div></div></div>
	<div class="progress"></div>

include the CSS in the header 

    <link href="css/impress-progress.css" rel="stylesheet" />

and include the script

	<script src="js/impress-progress.js"></script>
	
just before including impress.js.

Until m42e/impress.js@f367c84 isn't accepted there's the need to patch js/impress.js to add the steps data to init().

Changing line 402 like this:

	triggerEvent(root, "impress:init", { api: roots[ "impress-root-" + rootId ] });
	triggerEvent(root, "impress:init", { api: roots[ "impress-root-" + rootId ], steps: steps });
	
	
	

impress.js substeps
===================

Use class = "substep"

Example

    <div id="introduction" class="step" data-x="0" data-y="0">
      <h1 class="line">Can Haz Substep?</h1>
        <ul>
          <li class="substep">Sure!</li>
          <li class="substep">Why Not?</li>
          <li class="substep">Just Add the Substep Class</li>
          <li class="substep">And Amaze Friends</li>
          <li class="substep">With Substep Goodness</li>
        </ul>
      </div>

	  The corresponding css code for substep it is added in impress.css file
	  
	  
	  
impress.js presenter console
===================


To use it put impressConsole.js in the js directory under your presentation,
and put impressConsole.css in the css directory under your presentation. The
console will look for css/impressConsole.css, so you need to locate it there.

Then add the following to the bottom of your presentation HTML::

    <script src="js/impressConsole.js"></script>
    
And add this to the script where you call impress.init()::

    impressConsole().init();

You can then open the speaker window with the <P> key. You can also open it
automatically with::

    impressConsole().open();


All in all, the impress.js initialization at the end of the file hence should
look something like this::

    <script src="js/impress.js"></script>
    <script src="js/impressConsole.js"></script>
    <script>
        impress().init();
        impressConsole().init();
        impressConsole().open(); // If you want them to open automatically
    </script>

The timer at the bottom of the screen starts automatically, and will reset if
you click on it.


Adding notes
============

You add presenter notes to your impress.js presentation by simply
adding a <div class="notes">The notes go here</div> to any
step/slide that you want to have notes. The contents of that <div>
will be picked up by the console.


To FINISH
---------------------------------------

All the previous steps are added in the current repository and can be viewed in the example
