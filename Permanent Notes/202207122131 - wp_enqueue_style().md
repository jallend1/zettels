# wp_enqueue_style()

**Related:** [[202207122103 - Loading Styles in Wordpress]]

Example Usage:

```php
wp_enqueue_style('unique-identifier', 'source', [dependencies], 'version_number', 'media');
```

```PHP
wp_enqueue_style('stylesheet', get_stylesheet_uri(), 
		['another-css-file-you-want-loaded-first'], 
		filemtime(get_template_directory() . '\style.css'));
```

- Unique name: 'stylesheet'
- Source: get_stylesheet_uri()
- Dependencies: ['another-css-file-you-want-loaded-first']
- Version: filemtime(get_template_directory() . '\style.css')


**Related:** [[202207122140 - filemtime()]]

## References
---
1. https://developer.wordpress.org/reference/functions/wp_enqueue_style/