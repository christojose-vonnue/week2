# Day 3

> Reference Materials
>
> **Diagram**
> Read : https://css-tricks.com/snippets/css/complete-guide-grid/ <br>
> https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids


## Watching Kevin & Wes Bro

*Taking Notes*

https://www.youtube.com/watch?v=u044iM9xsWU

Practicing in practice.html

```.stdiv{
    display: grid;
    grid-template-columns: 50% 20% 100px;
    gap:20px;
}

.inside-grid{
    background-color: rgb(252, 151, 0);
}
 ```

 Practiced by changing variable values for grid-template-columns

```
.stdiv{
    display: grid;
    grid-template-columns: 50% 20%;
    grid-template-rows: 70px;
    grid-auto-columns: 10px ;
    grid-auto-flow: column;
    gap:20px;
}
```

**auto-column/row helps to control the size of the implicit containers**
**auto-flow is like flex-direction ; the direction in which the new children are born**

<span style="color:tomato">Never try to add upto a 100%, because all the extra padding, gap, margin will also add upto it. Therefore use fr , which deals with the rest of the space available </span>

`grid-auto-column : auto` It allocated by the rule maximum width possible, some cases

- Case I : auto 200px; (200px will be reserverd, rest will be autofiled)
- Case II : auto 1fr; (auto will act like max content and rest will be filled for fr)
- Case III : auto 1fr auto; (auto will act like max content and rest will be filled for fr)

You can mixup repeat,with all sorts of combinations of repeat and

```
.stdiv{
    display: grid;
    grid-template-columns: 1fr 1fr;
    
    grid-auto-columns: 10px ;
    
    gap:20px;
}

.inside-grid{
    background-color: rgb(252, 151, 0);
}

#two{
    grid-row: span 2;
}

#six{
    grid-column: span 6;
}
```

This is another important example of span
Individual grid items can be custom controlled by

`grid-row : span _` : SPAN A ITEM IN MULTIPLE ROWS,VERTICALLY

`grid-column: span _` : SPANS AN ITEM HORIZONATLLY ACROSS MULTIPLE COLUMNS

If span exceeds the explicit layout then it would do implicit layout and checks for any presribed auto rules or simply automates it as if auto

<span style="color:tomato">`grid-row: 1/-1` can be used to span across an entire row provided the columns are not a implicit.</span>

**Visulaized the difference between `auto-fill` and `auto-fit`**

In `auto-fill` maximum number of columns that can be produced with the constraints of gtc would be *layed* out

But in `auto-fit` maximum no of columns will not be layed out rather, the content will be squished to fit-in 

`repeat(auto-fill/auto-fit),minmax(value,value)`can be used to responsively design websites / grids without using media queries

```
 <h2>Holy grail -  grid</h2>
     <div class="holy">
        <div class="header"></div>
        <div class="header"><h4>Header</h4></div>
        <div class="header" id="span"></div>
        
        <div class="side"></div>
        <div class="content"></div>
        <div class="side-2"></div>
  
        <div class="side"></div>
        <div class="content"></div>
        <div class="side-2"></div>    
        
        <div class="footer"></div>
        <div class="footer"></div>
        <div class="footer"></div>

     </div>

css
---
.header{
    background-color: antiquewhite;
     grid-area: header;
}

.side,.side-2{
    background-color: aqua;
}

.footer{
    background-color: yellowgreen;
    grid-area: footer;
}
.holy{
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
    grid-template-rows: 100px 100px 100px 100px;
    border: solid 2px red;
    border-radius: 5px;
    grid-template-areas: 
    "header header header"
    "side   content side-2"
    "side   content side-2"
    "footer footer  footer"
}

.side{
    grid-area: side;
}
.side-2{
    grid-area: side-2;
}
@media (max-width: 600px){
    .holy{
    grid-template-rows: 100px 100px 200px 100px 100px;
    grid-template-areas: 
    "header header header" 
    "side   side side"
    "content   content content"  
    "side-2 side-2 side-2"
    "footer footer footer"
}

```

**Succesfully implemented a holy grail layout using `grid-areas` , easily made it responsive via `@media` queries**

`grid-autoflow:dense` Removes maximum available space which care caused in between the files. There will always be minimal space between

**Layout Properties**

`justify` : *deals with rows*
`align` : *deals with colums*

`-content` : deals with the space between overall content in the row axis + overall leftover *horizontal* space with respect to the entire grid-box

`-item` : deals with how each **grid-item** is located in its allocated space

`-self` : For each item, we can custom position its space. **Applicable - only for items**

`order` : helps to re-arrange , but default `order` is 0 so,every item must be later given `order`

<span style="color:pink">Attempting Task 1..</span>
<hr>

Completed succesfully.. No major doubts

<span style="color:pink">Attempted Task 2,3,4..</span>
<hr>

Completed Successfully.. No major doubts

<span style="color:pink">Attempted Task 5..</span>
<hr>

All requirements are completed.. but I am havin issues in reasoning why my main-grid layout is over-flowed in mobile views

Seeking Claude to clear this doubts after many failed attempts to understand

Mistakes I made ..

`height : auto` 
...
`grid-template-rows: 70%`

The issue was, I tried to measure height in % with heght being an `auto` value, `%` requires a definite value to work smoothly

Another mistake was to **define** an element with `min-height:100px` and then later while making it responsive, `grid-template-rows` I reduced the height less than the `min-height` defined!!

These issues caused overflow of the contents!!!

<span style="color:pink">Attempted Task 6..</span>
<hr>

Working on making is responsive now..
Seems like a bottleneck..
Requires full re-working of the grid using `grid-template-area`..
Will work on it later.

<span style="color:pink">Attempted Task 7 and 8..</span>
<hr>

Completed the tasks as required.

END-OF-DAY SELF-CHECK - TICK EVERY BOX BEFORE YOU LOG OFF:

□​ I can explain the difference between explicit and implicit grid tracks

□​ I can use grid-template-areas to define a complete page layout

□​ I can create a fully responsive grid without media queries using auto-fill or auto-fit

□​ I know when to use Grid vs Flexbox and can combine them

□​ I can use the DevTools grid overlay to debug a layout

All of these concepts are learned and applied.

<hr>
DAILY JOURNAL - WRITE YOUR ANSWERS IN YOUR LEARNING JOURNAL:

•​ Build the same three-column layout twice - once with Flexbox, once with Grid. Write three differences in how you approached each.

1. In the case of grid we have to expicitily define template row/column must set out a layout before we build anything in grid..While in flex we dont need to pre-define the layout

2. There is no concept or need to set a grid-direction like in flex.So when we design layout we dont need to mention the direction like in flex.

3. It is not possible to assign flex-areas like `grid-template-areas`.So there are such differences when designing a flex and a grid layout


•​ When is auto-fill better than auto-fit? Draw a diagram to explain.

Autofill is better in the cases where we expect further more grid-contents.
Both `auto-fill` and `auto-fit` can accomodate new grid-content but `auto-fit` might completely re-define the grid-lines and grid-tracks.

Imgaine a 2x2 grid, with one content
gtr : 1fr 1fr
gtc : 1fr 1fr

`[content]`       `_________` <br>
.........................................

`_________`         `_________`<br>
.....................................

In the case of `auto-fill` there will be **two grid-row lines**,but In the case of '`auto-fit` there will **only be one grid-row line**.
as seen below.

`[content]`       `_________` <br>
.........................................

Thank you Jesus!!






