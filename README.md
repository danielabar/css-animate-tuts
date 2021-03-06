<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [Advanced CSS3 Animations](#advanced-css3-animations)
  - [Transition](#transition)
    - [Transition Shorthand Syntax](#transition-shorthand-syntax)
  - [3D Transform](#3d-transform)
  - [Perspective](#perspective)
  - [Animate Perspective on Hover](#animate-perspective-on-hover)
  - [CSS Animation Review](#css-animation-review)
  - [CSS Animation Properties](#css-animation-properties)
  - [Keyframes In Between](#keyframes-in-between)
  - [Animating Images](#animating-images)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

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

  ```css
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

[HTML](transform-3d/transition-primer.html) | [CSS](transform-3d/styles.css) | [Demo](http://codepen.io/danielabar/pen/wBEyMb)

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

## Perspective

[HTML](portfolio/index02.html) | [CSS](portfolio/portfolio02.css)

Works together with transform

  ```css
  perspective: 500px;
  ```

Translate - move in 3D space, for example, move forward by 60 pixels

  ```css
  transform: translateZ(60px);
  ```

## Animate Perspective on Hover

[HTML](portfolio/index03.html) | [CSS](portfolio/portfolio03.css)

## CSS Animation Review

[HTML](animation-review/animationReview.html) | [CSS](animation-review/animationPrimer.css)

Occurs as browser loads, can be more flexible than a transition.
Can loop, add multiple keyframes etc.

Whereas transitions typically occur on hover, animation, by default occurs as soon as browser loads.

Two different types of animation:

1. Goes from one value to a second value

1. Goes from one value to a second value, with a number of _keyframes_ in between

Example of first kind (note still using `keyframes`)

  ```CSS
  /* Give the animation a name: left-to-right */
  @keyframes left-to-right {

    /* Define the starting point with 'from' keyword, specifying a css attribute and starting value */
    from { left: 0; }

    /* Define the ending point with 'to' keyword, specifying a css attribute and ending value */
    to { left: 400px; }
  }
  ```

This animation is then attached to a class to be animated, via the `animation` attribute, for example

  ```css
  .my-box {
    width: 200px;
    height: 200px;
    position: absolute;
    background-color: #060;
    animation: left-to-right 2s;
  }
  ```

NOTE: To animate position of an object, must give it an absolute position.

By default, when animation is done, it jumps back to its starting position.

## CSS Animation Properties

[HTML](animation-properties/animationProperties.html) | [CSS](animation-properties/animationProperties.css)

These properties are associated with the object being animated.

* `animation-name` Name of defined  `@keyframe` animation
* `animation-duration` Duration of animation in seconds
* `animation-timing-function` Defaults to `linear`, can also use `ease`
* `animation-delay` Number of seconds to delay start of animation, by default, its set to `0s` (i.e. start as soon as browser has loaded)
* `animation-iteration-count` How many times to loop the iteration, by default, set to `1`.
Can also set this to `infinite` to loop the animation forever (as long as browser window is open)
* `animation-direction` Defaults to `normal`, will loop in expected direction.
Can set to `alternate`, to make it go forwards and backwards with respect to `from` and `to` keyframe definitions.
* `animation-play-state` Default is `running` which means animation is running, can also set to `paused`.
Would use JavaScript to update this attribute to pause animation.

To define all of the above properties in the shorthand form, they must be defined in this order. For example

  ```css
  .my-box {
    -webkit-animation: left-to-right 2s ease 0s infinite alternate;
  }
  ```

## Keyframes In Between

[HTML](in-between/inBetween.html) | [CSS](in-between/inBetween.css)

Can have as many keyframes as you like, instead of `from` and `to`, specify percentages. For example

  ```css
  @keyframes left-to-right {
    0% { left: 0px; }
    50% {left: 600px; }
    100% { left: 400px; }
  }
  ```

Note that multiple properties can be listed inside any of the keyframes. For example, to move down and right at same time

  ```css
  @keyframes left-to-right {
    0% { left: 0px; top: 0px; }
    50% {left: 300px; top: 200px; }
    100% { left: 600px; top: 0px; }
  }
  ```

Technically, don't need to specify `left: 300px` in above example, because it will already be there.

## Animating Images

[HTML](pig-animation/index02.html) | [CSS](pig-animation/css/pig02.css)

When preparing images for animation, leave empty space around the image, for transformations.

Anchor point for css image rotation (or any object) is the center of the object.

To achieve rotation around a different part of the image, make it have empty space around it.

Or could use `transform-origin` css property to change the origin of rotation,
but it uses percentages and can be tricky to work with.

Place images in html in stacking order, furthest away from camera first.
Give each image an id so it can be accessed in css for animation.

### Animation Technique

Move parts "in place" with rotation from left to right,
while background image moves across, to give illusion of front image "walking".

To animate the fence (background), notice the image is wider than the container, so it can loop around.
