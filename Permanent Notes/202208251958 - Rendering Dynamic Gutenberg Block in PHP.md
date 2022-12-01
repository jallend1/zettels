# Rendering Dynamic Gutenberg Block in PHP
**Topics:** [[202207052049 - Wordpress]]

```PHP 
add_action('init', function() {
	register_block_type('jasons/dynamic_block', [
	'editor_script' => 'jasons-dyanamic-block-js',
	'render_callback' => 'jasons_block_render' 
	]);
});

function jasons_block_render($attr, $content){
	// Block output content here!
	// $attr are the attributes defined in the block type
	// $content is whatever is saved via the save method in JavaScript, a thing useful for InnerBlocks especially!
}
```

## References
---
[[202208251928 - ARTICLE - Dynamic Blocks and PHP Render]]