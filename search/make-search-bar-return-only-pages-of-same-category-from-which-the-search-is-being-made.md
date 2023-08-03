# Make the search bar return only pages of the same category from which the search is being made

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add this in the child theme's `functions.php` file:

```php
add_filter('pre_get_posts', function (\WP_Query $query) {
    if (!$query->is_main_query() || !$query->is_search() || is_admin()) {
        return $query;
    }

    $referer = wp_get_referer();

    if (!$referer) {
        return $query;
    }

    $page_id = url_to_postid($referer);

    if (empty($page_id)) {
        return $query;
    }

    $category = get_the_category($page_id)[0] ?? null;

    if (empty($category)) {
        return $query;
    }

    $query->set('cat', $category->term_id);

    return $query;
});
```
