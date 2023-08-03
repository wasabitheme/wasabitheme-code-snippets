# Change the HTML tag of cluster links to H3 (or another tag)

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add this in the child theme's `functions.php` file:
```php
add_filter('wasabi_cluster_link_anchor_html', function (string $html) {
    return str_replace(['<span>', '</span>'], ['<h3 class="cluster-h3">', '</h3>'], $html);
});
```

3. Add this in `Appearance > Custom CSS`:

```css
h3.cluster-h3 {
    border-bottom: unset;
    color: unset;
    font-size: unset;
    padding-bottom: unset;
    background-color: unset;
    font-weight: unset;
    margin: unset;
}
```
