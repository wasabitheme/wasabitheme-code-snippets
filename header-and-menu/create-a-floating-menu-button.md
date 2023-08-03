# Create a floating menu button

### If you do NOT use the "back to top" option:

Add this in `Appearance > Custom CSS`:

```css
@media only screen and (max-width: 600px) {
    button#js-subheader-menu-opener {
        position: fixed;
        top: auto !important;
        bottom: 30px !important;
        right: 30px;
        height: auto;
        background: white;
        border-radius: 50%;
        box-shadow: 0px 5px 10px 0px rgb(0 0 0 / 50%);
        width: 50px;
        padding: 12px;
        z-index: 999999;
    }

    .subheader-opened .top-bar {
        z-index: 9999;
        background: none;
        border-top: none;
    }

    .subheader-opened .logo-container,
    .subheader-opened .right {
        display: none;
    }

    .subheader-opened #js-subheader {
        position: fixed;
        top: 0;
        bottom: 0;
        overflow-y: scroll;
        overflow-x: hidden;
    }
}
```

### If you USE the "back to top" option:

Add this in `Appearance > Custom CSS`:

```css
@media only screen and (max-width: 600px) {
    button#js-subheader-menu-opener {
        position: fixed;
        top: auto !important;
        bottom: 90px !important;
        right: 30px;
        height: auto;
        background: white;
        border-radius: 50%;
        box-shadow: 0px 5px 10px 0px rgb(0 0 0 / 50%);
        width: 50px;
        padding: 12px;
        z-index: 999999;
    }

    .subheader-opened .top-bar {
        z-index: 9999;
        background: none;
        border-top: none;
    }

    .subheader-opened .logo-container,
    .subheader-opened .right {
        display: none;
    }

    .subheader-opened #js-subheader {
        position: fixed;
        top: 0;
        bottom: 0;
        overflow-y: scroll;
        overflow-x: hidden;
    }
}
```

### Settings:

- Change `600px` to the maximum width at which you want to see the floating button.
- Button right margin: `right: 30px;`
- Button width and height: `width: 50px;`
- Button background: `background: white;`
- Icon color:
  ```css 
    /* Add the following rule (changing #000000 to the desired color): */
    button#js-subheader-menu-opener svg.main-color * {
      fill: #000000;
    } 
    ```
