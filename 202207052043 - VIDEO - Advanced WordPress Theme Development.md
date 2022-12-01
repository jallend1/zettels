# Advanced WordPress Theme Development
**By:** Imran Sayed

- Minimum number of files for a Wordpress Theme
    - index.php
    - style.css
        - Comments required to describe theme
- Other files
    - functions.php
	Loading Styles
		function sample_style_loading(){
			wp_enqueue_style('stylesheet', get_stylesheet_uri(), ['another-css-file-you-want-loaded-first'], filemtime(get_template_directory() . '\style.css'));
			wp_enqueue_style('another-css-file-you-want-loaded-first', get_template_directory_uri() . '\main.css');
			}
            add_action('wp_enqueue_scripts', 'sample_style_loading')
	wp_enqueue_scripts is the hook, sample_style_loading is the name of the function to call at that hook
	- get_template_directory_uri()
		- Returns the theme directory

        get_stylesheet_uri()
            Returns the path to style.css

        filemtime('file-path_name);
            Returns the modify time of a file, useful for version number of files
    - header.php
	    wp_head() - Pulls in both your styles and scripts, as well as WordPress
	    Called with get_header() function in parent file
		Retrieves header.php by defeault
		If a parameter is passed, will retrieve a particular header. i.e. get_header('special') retrieves a file called header-special.php

    - footer.php
        wp_footer() - Pulls in the scripts just before the closing body tag
        get_footer()
- Hooks
    - wp_enqueue_scripts

- Functions
    - language_attributes()
    - bloginfo('charset')
    - body_class()
        Adds a series of useful class names on the body across your WordPress site
        Syntax: <body <?php body_class('my-own-classes'); ?> > combines 'my-own-classes' in addition to the WordPress generated classes
    - wp_body_open()
        Useful hook for Google Analytics and Facebook
        <!-- make sure it exists -->
        if( function_exists( 'wp_body_open')){
            wp_body_open();
        }

wp_enqueue_scripts is the hook, wp_enqueue_script is the function

  

wp_register_style - Registers the style, but doesn't enqueue it and instead allows for conditional enqueing (page specific, other conditions met, etc...) -- BEST PRACTICE?? Investigate that!

  

get_template_part()

 - Convention is to use subdirectory called template-parts

- Passing template part path to function loads that

- Can also pass slug? -- Seems interesting

  

Namespaces 

* Way to capture a number of items

* Prevents collisions with popular names by quarantining your names

-- Non-namespaces way

* class Product {}

$product = new Product();

-- Namespaces Way:

namespace App;

class Product{}

$product = new App\Product();

  

Autoloaders

- Loads classes automatically

spl_autoload_register( function ( $class) {

   include 'includes/' . $class . 'php';

})  

  

new Student();

--> When class is instantiated, autoloader runs and loads all classes present in file

  

  

Traits

 - Alternative to passing properties only through class inheritance in order to avoid long chains drilling down 

- Traits introduced in pHp 5.4 

- Allows you to extend methods to separate classes that are otherwise not connected

- Similar to classes, but much more narrowed focus

- Traits cannot be instantiated into their own entity

  

trait Say_World {

public function say_hello() {

   echo "hello trait";

   }

}

  

class Base { 

  use Say_World;

}

  

$base = new Base();

$base ->say_hello();

  

  

Singleton

 -- Restricts instantion of a class to a single object

 -- Instead of creating multiple objects of the same name and different references

-- Traditional way:

   class User{};

   $user1 = new User();

   $user2 = new User();