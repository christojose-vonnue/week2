# Day4

> Reference : MDN - Responsive designRead the full article. Focus on the mobile-first approach and why min-width queries are the correct method.
>https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design

## Reading and excercising

**Responsive web design isn't a separate technology — it is an approach.**

<cite>A common approach when using media queries is to create a simple single-column layout for narrow-screen devices (for example, mobile phones), then check for wider screens and implement a multiple-column layout when you know that you have enough screen width to handle it. Designing for mobile first is known as mobile first design.</cite>

**Use relative units**

### Diffrent ways to make RWD 

1. Media queries
2. Flexible Grids
3. Relative Units
4. Min-max unit values


<cite>
In flexbox, flex items shrink or grow, distributing space between the items according to the space in their container. By changing the values for flex-grow and flex-shrink you can indicate how you want the items to behave when they encounter more or less space around them.
</cite>

```
@media screen and (width >= 600px) {
    .wrapper {
        display: flex;}
        .col1 {
    flex: 1;
    margin-right: 5%;
  }
  .col2 {
    flex: 2;
  }
}
```
Experimented with various combinations in flex values

- Flex tries to fit it all columns in one row by shrinking other contents
- Values in `flex` acts like proportions like `fr` units in `grid`

- Typography can be controlled using media queries

```
h1{
    font-size:2em;
}

@media scren and (width>600){
    h1{
       font-size:4em; 
    }
}
```

<cite>
The problem with doing the above is that the user loses the ability to zoom any text set using the vw unit, as that text is always related to the size of the viewport. Therefore you should never set text using viewport units alone
</cite>

The `meta` tag with viewport attribute overrides mobiles default viewport settings , which may not be accurate.. So that the responsive design is not overruled due to flase width size

> Reference :Read the full article. Focus on @keyframes syntax, animation-fill-mode, and animation-play-state.
>https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations/Using_CSS_animations

## Reading and excercising

### CSS Animations

**3 Advantages over JS animations**

1. Simple animations run smoothly with very low load
2. Simplicity in writing the lines of code
3. Browser controls animations , thus it willl run in such a way that the performance is optimized

<cite>
Animations consist of two components: a style describing the CSS animation and a set of keyframes that indicate the start and end states of the animation's style, as well as possible intermediate waypoints.
</cite>

animation property can do styling
animation-
1. `animation-delay` : How delayed the animation must begin
2. `-duration` : how long the animation must run
3. `-direction` : Initial direction of where the animation must go
4. `-fill-mode` : Unclear
5. `iteration-count` : How many times you want to repeat the animation
6. `name` : specifies the name of the keyframes use
7. `play-state` : Whether to puse or play
8. `-timeline` : to control the progress of a CSS animation
9. `-timing-function` : how it transitions through keyframes

<cite>
After you've configured the animation's timing, you need to define the appearance of the animation. This is done by establishing one or more keyframes using the @keyframes at-rule. Each keyframe describes how the animated element should render at a given time during the animation sequence.
</cite>

Understood that shorthands exist to save space,
Also so some edge cases where multiple `animation-name` exist refering multiple animations, How value mismatch is handled

*Trying one example*

```
#one{
  color: rgb(252, 4, 4);
  font-size: x-large;
  animation-name: Apple;
  animation-duration: 5s;
}

@keyframes Apple {
  from{
    color: blueviolet;
    translate:0 100vh;
    scale: 100% 1;
}

to{
  color: rgb(25, 23, 27);
  translate:0 0;
  scale:100% 1;
}
}
```

Experimented with various values of translate, scale , animation-duration..

translate deals from , start from where to where to end, values are with respect to the original position of the element (0,0) is th ebase position.

Further properties
`animation-iteration-count` , `opacity` inside `@keyframes` , were experimented.

`@media (prefers-reduced-motion: reduce)`

Write the same animation code with lesser frame rate along with slower transitions fo people with vestibular motion disorders (inner ear issues)

### `clamp()` Function

> https://developer.mozilla.org/en-US/docs/Web/CSS/clamp
> Read the full article. Use clamp(min, preferred, max) for every heading size today.

<cite>
The clamp() CSS function clamps a value within a range of values between a defined minimum bound and a maximum bound. 
</cite>


The function takes three parameters: 

`min` : a minimum value, most negative value **Lower Bound** 
, and a maximum allowed value.

`val` : A preferred value , resultant value

`max` :  The maximum value is the largest (most positive) expression value to which the value of the property will be assigned if the preferred value is greater than this **upper bound.**

<cite>
It has the same effect as the code in Fluid Typography but in one line, and without the use of media queries.
</cite>


So this is a simpler method to compute text sizes in a fluid manner.

**The Prefered** value must always be a relative unit (eg: vw)

So as the  parent of relative unit changes its width , the width of the font/width/height changes

<span style="color:pink">Attempting Task 1,2..</span>

### `@container` Queries

<cite>
Container queries are an alternative to media queries, which apply styles to elements based on viewport size or other device characteristics.
</cite>
<br>

`@container` queries applies styles based on :
1. `container-name`
2. `container-type`

We can apply styles directly to `div` and specifically by identifying it with `id`

Similarly

We can apply styles directly to all containers with type.

`inline-size` :Track the container's width (most common).

`size` : Track both width and height.

`normal` : Do not track size

<span style="color:pink">Attempting Task 3..</span>

### Various animation-timing-function

**Fundamentally,all animations are a cubic-bezier function with 4 point values**

For example : `linear` = cubic-bezier(0.0,0.0,1.0,1.0) animates in an even speed

`ease` : Equal to cubic-bezier(0.25, 0.1, 0.25, 1.0), the default value, increases in velocity towards the middle of the animation, slowing back down at the end.

`ease-in` : Equal to cubic-bezier(0.42, 0, 1.0, 1.0), starts off slowly, with the speed of the transition of the animating property increasing until complete.

`ease-in-out` : Equal to cubic-bezier(0.42, 0, 0.58, 1.0), with the animating properties slowly transitioning, speeding up, and then slowing down again.

`ease-out` : Equal to cubic-bezier(0, 0, 0.58, 1.0), starts quickly, slowing down the animation continues.

`cubic-bezier(<number [0,1]> , <number> , <number [0,1]> , <number>)`
An author defined cubic-bezier curve, where the first and third values must be in the range of 0 to 1.

**Learned about fill mode** : `animation-fill-mode : backwards/forward/both` 

`backwards` : Go to frame at 0% before delay
`afterwards` : Do not reverse to css, stay at 100% , keyframe
`both` : Combines both

<span style="color:pink">Attempting Task 4,5..</span>

- Learnt about `:target` selector and filtered sections

<span style="color:pink">Attempting Task 6..</span>

Applied the intelligent usage of flex-box and flex-direction, Visualized the usage of `~` operator.

<span style="color:pink">Attempting Task 7..</span>

Used `@media (prefers-color-theme :dark)`

<span style="color:pink">Attempting Task 8..</span>

Used `<link href="files_with_styles.css" media="print" rel=stylesheet > `

and

`@media print` statement to define styles for the printed file

