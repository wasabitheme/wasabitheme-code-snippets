# Change from ItemList to Product in Product Block Schema

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add this in the child theme's `functions.php` file:

```php
add_filter('wasabi_json_ld_output', function ($data) {
    if (isset($data['@type']) && $data['@type'] === 'ItemList') {
        $data['@type'] = 'Product'; // Me lo invento.
    }

    return $data;
});
```
