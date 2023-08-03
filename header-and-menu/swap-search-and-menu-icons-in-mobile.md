# Swap the search and menu icons in the mobile header

Add this in `Appearance > Custom CSS`:

```css
@media screen and (max-width: 666px) {
    .top-bar .right {
        order: 1;
    }

    .top-bar .logo-container {
        order: 2;
    }

    .top-bar #js-subheader-menu-opener {
        order: 3;
    }
}
```
