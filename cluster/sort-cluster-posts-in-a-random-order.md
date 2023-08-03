# Sort cluster posts in a random order

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add one of these two codes (one or the other, not both) in the `functions.php` file of the child theme:

**Option 1:** If you want to randomize clusters of entries or specific pages.

```php
add_filter('wasabi_cluster_block_query_args', function ($query_args) {
    // Change the values to the ids of the pages or posts where the clusters are located.
    $post_or_page_ids = [1, 2];

    if (!is_singular() || !in_array(get_the_ID(), $post_or_page_ids, true)) {
        return $query_args;
    }

    return array_merge($query_args, [
        'orderby' => 'rand',
    ]);
});
```

**Option 2:** If you want to randomize all the clusters on the site.

```php
add_filter('wasabi_cluster_block_query_args', function ($query_args) {
    return array_merge($query_args, [
        'orderby' => 'rand',
    ]);
});
```
