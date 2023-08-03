# Fix bullets in the sidebar that misconfigure some elements

Add this in `Appearance > Custom CSS`:

```css
aside .widget.same-category-posts ul {
    padding-left: 0;
}

aside .widget.same-category-posts ul li {
    list-style: none;
    padding-bottom: 3px;
}
```
