Phing Build Script for CakePHP projects

* Minifies JS and CSS
* Concatinates Multiple JS and CSS Files
* Compresses View files
* Turns off debug mode in Config/core.php
* Replaces links to css and js in layouts to their minified and concatinated versions

## Setup

* Install Phing (http://www.phing.info/trac/wiki/Users/Installation)
* Drop into your Cake root directory (same level as app)
* Javascript and CSS and files should be included in the layout (ie: View/Layouts/default.ctp) like this:

    <?php
    $build_css = array('styles.css', 'bootstrap/bootstrap.css', 'bootstrap/bootstrap-responsive.css');
	echo $this->Html->css($build_css);
	$build_js = array('custom.js');
	echo $this->Html->script($build_js);
	?>

* Update build.properties with your css and js filenames