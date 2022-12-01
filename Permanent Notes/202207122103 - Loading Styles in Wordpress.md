# Loading Styles in WordPress
**Topics:** [[202207052049 - Wordpress]]

```php
function sample_style_loading(){
	wp_enqueue_style('stylesheet', get_stylesheet_uri(), 
		['another-css-file-you-want-loaded-first'], 
		filemtime(get_template_directory() . '\style.css'));
	
	wp_enqueue_style('css-you-want-loaded-first', 
		get_template_directory_uri() . '\main.css');
	}
	
	add_action('wp_enqueue_scripts', 'sample_style_loading')
```

**Referenced Functions:** 
- [[202207122131 - wp_enqueue_style()]]
- [[202207122140 - filemtime()]]

## References
---
1. [[202207052043 - VIDEO - Advanced WordPress Theme Development]]