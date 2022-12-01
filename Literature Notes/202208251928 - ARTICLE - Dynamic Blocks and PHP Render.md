# Dynamic Blocks and PHP Render
**Source:** https://awhitepixel.com/blog/wordpress-gutenberg-create-custom-block-part-9-dynamic-blocks-php-render/

- Set the save function inside the JavaScript function to null
- Add the 'render_callback' key to the register_block_type in PHP
	- render_callback' => 'my_block_rendering_function' to the PHP
- Function itself takes two parameters
	- $attributes - The attributes defined in this function, as well as those in the index.js
	- $content - Whatever is saved via the save method in JavaScript (Useful for InnerBlocks!)
	- 
```PHP
function my_block_rendering_function($attr, $content){

// The stuff to return!

}
```
