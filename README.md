Advanced CSS3 Animations
==========

> Learning CSS3 Animations with Tuts Plus [course](https://webdesign.tutsplus.com/courses/advanced-css3-animations).

## Transition

[HTML](transition-intro/index.html.html) | [CSS](transition-intro/css/lesson00.css.css) | [Demo](http://codepen.io/danielabar/pen/Eaevjx)

Animation that occurs in response to change of state. Most commonly used on `hover`.

For example, anchor tag that is styled like a button, and would like button to grow larger when user hovers over it.

To create an animation type of transition:

* Define what property is going to be animated, for example

  ```css
  transition-property: width;
  ```

* Define how long animation will take in terms of seconds, for example

  ```css
  transition-duration: 0.3s;
  ```

* Define beginning and ending values for that animation, for example

  ```css
  .top-nav li {
    /* Beginning state of animation is width of 150px */
    width: 150px;
    transition-property: width;
    transition-duration: 0.3s;
  }
  .top-nav li:hover {
    /* End state of animation is width of 160px */
    width: 160px;
  }
  ```

### Transition Shorthand Syntax

[HTML](transition-review/transition-primer.html) | [CSS](transition-review/css/styles.css) | [Demo](http://codepen.io/danielabar/pen/qEMVBL)

  ```
  .box {
    transition: transform 0.5s ease;
  }
  ```

<dl>
  <dt><strong>transform</strong></dt>
  <dd>Property to be animated</dd>
  <dt><strong>0.5s</dt>
  <dd>Transition duration in seconds</dd>
  <dt><strong>ease</strong></dt>
  <dd>Timing function</dd>
</dl>

## 3D Transform

[HTML](transform-3d/transition-primer.html) | [CSS](transform-3d/styles.css) | Demo TBD...

If no axis is specified, rotate operates in 2D space

  ```css
  .myclass:hover {
    transform: rotate(360deg);
  }
  ```

To rotate about the X axis, i.e. 3D horizontal axis:

  ```css
  .myclass:hover {
    transform: rotateX(360deg);
  }
  ```

To rotate about the Y axis, i.e. 3D vertical axis:

  ```css
  .myclass:hover {
    transform: rotateY(360deg);
  }
  ```

To rotate about the Z axis, it looks the same as 2D rotation

  ```css
  .myclass:hover {
    transform: rotateZ(360deg);
  }
  ```

Combine all axes for a full 3D transformation

  ```css
  .myclass:hover {
    transform: rotateX(360deg) rotateY(360deg) rotateZ(360deg);
  }
  ```

## Animation

Occurs as browser loads, can be more flexible than a transition.
Can loop, add multiple keyframes etc.
