# Hide search bar and background image in category pages

### To hide everything:

Add this in `Appearance > Custom CSS`:

```css
body.category header.hero {
    display: none !important;
}
```

### To hide only the search bar:

Add this in `Appearance > Custom CSS`:

```css
.category .hero .search-form, .category .hero .title:after {
    display: none;
}

.category .hero .title {
    margin: 0;
    padding: 0;
}
```

### To hide search bar and background, but not H1 and breadcrumbs:

Add this in `Appearance > Custom CSS`:

```css
body.category .hero .search-form, body.category .hero .title:after {
    display: none;
}

body.category .hero .title {
    margin: 0;
    padding: 0;
}

body.category .hero:after {
    content: none;
}
```
