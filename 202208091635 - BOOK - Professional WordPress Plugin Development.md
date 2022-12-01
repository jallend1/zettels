# Professional WordPress Plugin Development
## By: Brad Williams, Justin Tadlock, John James Jacoby

* Standard WordPress Loading Process
	* wp-config
	* Functions
	* Plugins
	* Pluggables
	* Translations
	* Theme
	* Page Content
* mu-plugins
	* Plugins that are always executed placed here
	* Sub-folders not read by WordPress, so all plugins need to have a file in the main directory
* Namespaces
	* First code after opening php tag and inline comments in your PHP file
	* Example: 
	```php
	<?php 
		// A nifty little comment
		namespace KCLSVoice;
	
		function my_function_name(){}
	?> 
	```
- Code case
	- kebab case: this-is-kebab-case
	- snake case: this_is_snake_case
	- Camel Case: thisIsCamelCase
- Determining Paths
	- plugin_dir_path()
		- Returns the filesystem directory path to your plugin
		- __FILE__ is PHP constant to current file
		```PHP 
		<?php echo plugin_dir_path(__FILE__); ?>
		```
		- Common practice to store the location of the root directory of the plugin in its own variable for easy access: 
		```php 
		<?php define('MYPLUGIN_DIRECTORY', plugin_dir_path(__FILE__)); ?>
		```
	- plugin_dir_url()
		- Used to locate assets like images or JS files
		```php
			<?php $url = plugin_dir_url(__FILE__) . 'public/js/test.js'; ?>
		```
	- home_url() refers to the URL of the site, whereas site_url() refers to the location of the WordPress installation
- Indentation
	- WordPress standard is to indent all tabs
	- Exception is for lining up rows of similar items, such as variables being lined up by the equal sign
- Never use the PHP shorthand tags of <? ?> when developing plugins