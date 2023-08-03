# Fix Twitter URL in Rank Math Structured Data

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add this in the child theme's `functions.php` file:

```php
add_filter('rank_math/json_ld', function($data, $jsonld) {
    foreach ($data as $key => $items) {
        if (!isset($items['sameAs'])) {
            continue;
        }
        
        foreach ($items['sameAs'] as $sameAsKey => $url) {
            if (substr_count($url, 'https://twitter.com/') === 2) {
                $data[$key]['sameAs'][$sameAsKey] = preg_replace('/(https:\/\/twitter.com\/)/', '', $url, 1);
            }
        }
    }

    return $data;
}, 99, 2);
```

