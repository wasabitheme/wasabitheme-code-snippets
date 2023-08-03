# Move the logo above the main menu

Add this in `Appearance > Custom CSS`:

```css
@media screen and (min-width: 860px) {
    .top-bar {
        height: auto;
    }

    .top-bar .section {
        flex-wrap: wrap;
    }

    .top-bar .logo-container {
        /* Adjust to the desired maximum logo size */
        max-width: 210px;
    }

    .top-bar .right {
        flex-basis: 100%;
        text-align: center;
    }

    .top-bar .js-search {
        display: none;
    }
}
```
