# Show post update date under the H1 title

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add this in the child theme's `functions.php` file:

```php
add_action('wasabi_entry_header_after', function () {
    if (!is_single()) {
        return;
    }

    printf(
        '<p style="text-align:center;">Updated at %s</p>',
        get_the_modified_time('F j, Y')
    );
});
```

