# Make thumbnails full height and full width simulating a background

Add this in `Appearance > Custom CSS`:

```css
.post-item.post-grid-item.vertical {
    position: relative;
    /* You can reduce the image size (to improve quality) by reducing the denominator, e.g. 4/3 */
    aspect-ratio: 4/4;
}

.post-item.post-grid-item.vertical .thumb {
    position: absolute;
    height: 100%;
    width: 100%;
}

.post-item.post-grid-item.vertical .thumb img {
    width: auto;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
}

.post-item.post-grid-item.vertical .content {
    z-index: 9999;
    margin: auto auto 0 auto;
}

.post-item.post-grid-item.vertical .title span {
    color: white;
    text-shadow: 1px 1px 1px black;
}
```
