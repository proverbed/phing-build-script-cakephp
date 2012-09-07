## Simple Phing Build Script for CakePHP projects

* Minifies JS and CSS
* Concatinates Multiple JS and CSS Files
* Compresses View files
* Turns off debug mode in Config/core.php
* Replaces links to css and js in layouts to their minified and concatinated versions

## Setup

* Install Phing (http://www.phing.info/trac/wiki/Users/Installation)
* Drop into your Cake root directory (same level as app)
* Javascript and CSS and files should be included in the layout (ie: View/Layouts/default.ctp) like this:

```php
    <?php
    //if debug level is 0, this is production
    if(Configure::read('debug') <= 0){
    	//lets display our minified and concatinated files
    	echo $this->Html->css('styles.min.css');
		echo $this->Html->script('scripts.min.js');

		//I put google analytics snippet in here as well

	} else {
		//for our development environment, we'll want uncompressed css and js
		echo $this->Html->css(array('bootstrap/bootstrap.css', 'styles.css'));		
		echo $this->Html->script(array('jquery-1.7.1.min.js', 'underscore-min.js', 'backbone-min.js', 'custom.js'));
	}
	?>
```

* Update build.properties with your css and js filenames