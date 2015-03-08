Advanced CSS3 Animations
==========

> Learning [CSS3 Animations] with Tuts Plus [course](https://webdesign.tutsplus.com/courses/advanced-css3-animations).

## Transition

[Demo](http://codepen.io/danielabar/pen/Eaevjx)

Animation that occurs in response to change of state. Most commonly used on `hover`.

For example, anchor tag that is styled like a button, and would like button to grow larger when user hovers over it.

To create an animation type of transition:

* Define what property is going to be animated, for example
  ```css
  transition-property: width;
  ```
* Define how long animation will take in terms of seconds, for example
  ```
  transition-duration: 0.3s;
  ```
* Define beginning and ending values for that animation, for example
  ```
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

[Demo](http://codepen.io/danielabar/pen/qEMVBL)

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

## Animation

Occurs as browser loads, can be more flexible than a transition.
Can loop, add multiple keyframes etc.
