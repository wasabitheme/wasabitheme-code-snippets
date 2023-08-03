# Increase the max limit of posts in clusters

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add this in the child theme's `functions.php` file:

```php
apply_filters('wasabi_cluster_block_query_args', function ($args) {
    $query_args['posts_per_page'] = 200;
    return $query_args;
});
```

