# Footer menu with 4-column title

Add this in `Appearance > Custom CSS`:

```css
footer.main-footer > div.section.grid-cols-3 > div:nth-child(1) {
    grid-column: span 3/span 3;
    text-align: center;
}

footer.main-footer > div.section.grid-cols-3 > div:nth-child(1) .widget_nav_menu .title {
    border-bottom: none;
}

footer.main-footer > div.section.grid-cols-3 > div:nth-child(1) .widget_nav_menu ul.menu {
    display: grid;
    grid-gap: 10px;
    grid-template-rows: minmax(min-content, max-content);
    grid-template-columns: repeat(auto-fit, minmax(max(calc(100% / (4 + 1) - 10px * 4 / (4 + 1) + 1px), 229px), 0.25fr));
}
```
