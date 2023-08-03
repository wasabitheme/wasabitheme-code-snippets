# Show table of contents in mobile

Add this in `Appearance > Custom CSS`:

```css
@media screen and (max-width: 859px) {
    .table-of-contents {
        display: block !important;
        width: 100% !important;
        position: relative;
        float: none !important;
        padding: 0;
    }
}
```
