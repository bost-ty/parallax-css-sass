True parallax effect made entirely in CSS. Find additional comments in the index.html and style.css files.






```html

<div class="container-for-parallax-layers">
  <div class="background layer"></div>
  <div class="midground layer"></div>
  <div class="foreground layer"></div>
</div>

```


```css

.layer {
  /* Positioning is important for good parallax ... */
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  padding: 0;
  /* ... and so is adding some extra space for scrolling ... */
  padding-top: 10vh;
  padding-bottom: 100vh;

}

.container-for-parallax-layers {
  /* ... but the magic here is primarily in (1) the perspective property ... */
  perspective: 1px;
  height: 100vh;
  overflow-x: hidden;
  overflow-y: scroll;
}


.background {
  /* and (2) the translateZ property (as well as the scale property). */
  /* To calculate scale, divide absolute value of translateZ by perspective and add 1 */
  transform: translateZ(-2px) scale(3);
  background-image: url("img/mountain.png");
  background-repeat: no-repeat;
  background-size: cover;
}

.midground {
  transform: translateZ(-1px) scale(2);
  background-image: url("img/treeline-midd.png");
  background-repeat: no-repeat;
  background-size: cover;
}

.foreground {
  transform: translateZ(0);
  background-image: url("img/treeline-fore.png");
  background-repeat: no-repeat;
  background-size: cover;
}


```

For more information, see Pure CSS Parallax Websites by Keith Clark:
http://keithclark.co.uk/articles/pure-css-parallax-websites/