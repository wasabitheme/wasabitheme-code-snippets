# Make the secondary menu smaller in mobile

Add this in `Appearance > Custom CSS`:

```css
@media screen and (max-width: 540px) {
    .subheader [class*=grid-cols-] > li > ul {
        grid-template-columns: repeat(3, minmax(0, 1fr)); /* Cambia el 3 por el número de columnas deseadas */
        display: grid;
        font-size: 0.75em;
    }

    .subheader [class*=grid-cols-] ul.sub-menu > li,
    .subheader [class*=grid-cols-] .sub-menu ul {
        display: contents;
    }

    .subheader [class*=grid-cols-] > li > a {
        font-size: 0.9em;
    }
}
```
