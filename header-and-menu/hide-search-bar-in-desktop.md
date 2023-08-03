# Hide the search bar only in desktop version

Add this in `Appearance > Custom CSS`:

```css
@media screen and (min-width: 667px) {
    .top-bar .js-search {
        display: none !important;
    }
}
```
