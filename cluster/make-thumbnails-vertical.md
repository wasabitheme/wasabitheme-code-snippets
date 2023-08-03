# Make cluster thumbnails vertical

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add this in `Appearance > Custom CSS`:

```css
/* STYLES 1 and 2 */
body .post-grid-item:not(.vertical) {
    height: 240px;
}

body .post-grid-item:not(.vertical) .thumb {
    flex: 1;
}

body .post-grid-item .thumb img {
    height: 100%;
    width: auto;
    left: 41%;
}

/* STYLES >= 3  */
body .post-grid-item.vertical {
    max-width: 250px;
    margin-left: auto;
    margin-right: auto;
}
```

3. Add this in the child theme's `functions.php` file:
```php
add_image_size( 'custom-vertical-archive-post-thumbnail', 250, 425, true );

add_filter('post_thumbnail_size', function($size){
    if($size !== 'archive-post-thumbnail'){
        return;
    }

    return 'custom-vertical-archive-post-thumbnail';
});
```


