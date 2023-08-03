# Replace category posts count in Rank Math Title

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add this in the child theme's `functions.php` file:

```php
add_action('rank_math/vars/register_extra_replacements', function () {
    rank_math_register_var_replacement(
        'wasabi_category_posts_count',
        [
            'name' => 'Category posts count',
            'description' => 'Category posts count',
            'variable' => 'wasabi_category_posts_count',
            'example' => wasabi_child_category_posts_count(),
        ],
        'wasabi_child_category_posts_count'
    );
});

function wasabi_child_category_posts_count() {
    $category = null;

    if (is_single()) {
        $category = get_the_category()[0] ?? null;
    } elseif (is_admin() && isset($_GET['tag_ID']) && isset($_GET['taxonomy']) && $_GET['taxonomy'] === 'category') {
        $category = get_term($_GET['tag_ID'], 'category');
    } elseif (is_category()) {
        $category = get_term(get_query_var('cat'), 'category');
    }

    if (!$category instanceof \WP_Term) {
        return 0;
    }

    return (string) $category->count;
}

```
