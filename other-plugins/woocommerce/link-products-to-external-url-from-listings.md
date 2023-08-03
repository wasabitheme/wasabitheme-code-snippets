# Link WooCommerce products to external URL from listings

1. Install and configure the [Wasabi Child Theme](https://wasabitheme.com/documentation/#child-theme).

2. Add this in the child theme's `functions.php` file:

```php
apply_filters('woocommerce_loop_product_link', function ($link, $product) {
    if (!$product->is_type('external')) {
        return $link;
    }

    return $product->add_to_cart_url();
}, 2);
```

