# Make the featured image full width

Add this in `Appearance > Custom CSS`:

```css
body {
    overflow-x: hidden;
}

article .content .thumbnail {
    position: relative;
    max-width: none;
    width: 100vw;
    left: calc(-50vw + 50%);
}
```

