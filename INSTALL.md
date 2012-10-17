# Installing and configuring the SilverStripe Slideshow Module

## Installation

1. Install DataObjectManager < http://silverstripe.org/dataobjectmanager-module/ > and Uploadify < http://silverstripe.org/uploadify-module/ >

1. Put the slideshow folder inside your project

2. To enable the slideshow on all pages, add the following to your mysite/_config.php file:

DataObject::add_extension('Page', 'Slideshow');

To enable the slideshow on specific pages, for example your home page, add the following to your mysite/_config.php file:

DataObject::add_extension('HomePage', 'Slideshow');


3. Build the database (e.g. http://localhost/mysite/dev/build)

## Configuration options

To override the default effects with your own, customize this and add it to your mysite/_config.php file:

Slideshow::set_custom_effects(
	array(
		'None' => "fx:'none'",
		'Fade over' => "fx:'fade'",
		'Fade in / out' => "sync:0,fx:'fade'",
		'Scroll horizontal' => "fx:'scrollHorz',easing:'easeOutQuart'",
		'Scroll vertical' => "fx:'scrollVert',easing:'easeOutQuart'",
		'Scroll horizontal with bounce' => "fx:'scrollHorz',easing:'easeOutBounce'",
		'Scroll vertical with bounce' => "fx:'scrollVert',easing:'easeOutBounce'",
		'Scroll horizontal elastic' => "fx:'scrollHorz',easing:'easeOutElastic'",
		'Scroll vertical elastic' => "fx:'scrollVert',easing:'easeOutElastic'",
		'Scroll left/down/right/up' => "fx:'scrollLeft,scrollDown,scrollRight,scrollUp',easing:'easeInBack'",
		'Turn down (images only)' => "fx:'turnDown'",
		'Turn left (images only)' => "fx:'leftDown'",
		'Uncover, sliding right (images only)' => "fx:'uncover',sync:0",
		'Zoom in/out (images only)' => "fx:'zoom',sync:0",
		'Zoom in elastic / Zoom out with a bounce out (images only)' => "fx:'zoom',speedIn:2000,speedOut:1000,easeIn:'easeOutElastic',easeOut:'easeInOutBack',sync:0",
		'Random (images only)' => "fx:'all'"
	)
);

The syntax of the array fed to set_custom_effects() is as follows:
array( [title of effect] => [JQuery Cycle effect setting] );

Look here for inspiration for making your very own JQuery Cycle effects:
< http://jquery.malsup.com/cycle/browser.html >

For easing effects look here:
< http://gsgd.co.uk/sandbox/jquery/easing/ >

If you want to use a custom javascript initialization file instead of javascript/init_slideshow.js use:
Slideshow::$slideshow_js_file = [path to your js file];

