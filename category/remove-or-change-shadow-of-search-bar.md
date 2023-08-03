# Remove or change the shadow of the search bar in category pages

### To remove it:

Add this in `Appearance > Custom CSS`:

```css
.hero:after {
    content: none;
}
```

### To change the color:

Add this in `Appearance > Custom CSS`:

```css
.hero:after {
    /* Change the color #000000 by the CSS color you want */
    background: #000000;
    /* Change the degree of transparency you want (it goes from 0 to 1. Use dots for decimals) */
    opacity: 0.5;
}
```
