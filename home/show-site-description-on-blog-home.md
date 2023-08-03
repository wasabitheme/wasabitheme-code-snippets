# Show site description on blog home page

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add this in the child theme's `functions.php` file:

```php
global $desc_added_to_blog_page;

$desc_added_to_blog_page = false;

add_action('wasabi_entry_before', function () {
    global $desc_added_to_blog_page;
    if (is_home() && !$desc_added_to_blog_page) {
        $desc_added_to_blog_page = true;
        printf('<p>%s</p>', get_bloginfo('description') ?? '');
    }
});
```

