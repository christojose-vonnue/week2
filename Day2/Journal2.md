# DAY 2

> Reference Modules
> ## CSS-Tricks -  A Complete Guide to Flexbox
>
> link : https://css-tricks.com/snippets/css/a-guide-to-flexbox/
>
> ## Video
>
> https://www.youtube.com/watch?v=u044iM9xsWU
>

**Learning, watching video shared**

*Taking notes....*

1. Contents inside a flex box are called as flex items
2. Philosophy of flex is to **get the contents inside as small it can without breaking the line,fitting in its parent**
3. But as the screen size changes the flex-tems can shirnk or grow and break into next line
4. `flex-grow` is a property that re distributes the lefover white space b/w the contents. (default value : 0)
5. `flex-wrap: wrap` allows the contents to squish inside, this ensures that there is no-wrap
6. `flex-basis` it dictates how the filex-items are displayed. `flex-basis:100%` does it (*`flex=1` is a shorter version*)
7. `flex-directions: row` by default , so the main axis on the parent is horizaontal so child elements appear vertically , when `flex-direction: coloumn` child elements appear as rows.. *Mordern browsers switch these directions as the width of the size grows to create responsive web pages*
8. **`justify-content : value`** The value **available leftover space** is distributed
- `center` : Centers the content
- `space-evenly` : Spaces are distributed evenly
- `flex-start` : default

> Note : if flex-grow is on , then there will no leftover space to justify

9. `align-items : value` How the containers in the **cross axis** distribute there space
- `flex-strech` : default, fills the space
- `center` , `flex-start` and `flex-end`

*Completed Video.. Lunch break*

<span style="color:pink">Attempting Task 1..</span>
<hr>

**Learnt About**

- Importance of min-height and max-height
- Applied all above properties
- Tried all values of align-content,align-items and justify content

<span style="color:pink">Attempting Task 2..</span>
<hr>

>The order property specifies the visual order of a flex item or grid item in a flex or grid container.
>Note: If the element is not a flex item or grid item, the order property has no effect.

**Learnt About**
- `{order : value}` , which changes the order of how the contents appear in display without changing html

<span style="color:pink">Attempting Task 3..</span>
<hr>

Truly understood the use of `justify-content : center` and `align-items : center`

- used `@media (max-width:768px) {}` to make the page responsive
- Implemented a sticky navbar

<span style="color:pink">Attempting Task 4..</span>
<hr>

- Implemented a flex container
- Cascaded multipe `@media` statements for a better responsive design

<span style="color:pink">Attempting Task 5..</span>
<hr>

<span style="color:pink">Attempting Task 6..</span>
<hr>

- Completed successfully
- Utilized `input:user-invalid` to higlight boxes which are invalid.
- Pop-up like red-message is styled using `~` sibiling finder.

<span style="color:pink">Attempting Task 7..</span>
<hr>

- Explored more about box-shadow and transition properties

<span style="color:pink">Attempting Task 8..</span>
<hr>

- Learnt the difference between vw and %
- **%** is the size of the box rleative to its **parent**
- **vw/vh** is the size relative to the browser
> vw/vh is used to span across entire browser while % is more safer option for layouts
- Realized the role of scroll bar wrt to viewport size
- Visualized the `flex-wrap:wrap` and discovered a different method comapred to task 4 (**a better way**) responsive designing.

<span style="color:tomato">All Tasks are over</span>

## Check-Boxses

END-OF-DAY SELF-CHECK - TICK EVERY BOX BEFORE YOU LOG OFF:

□​​ I can explain main axis vs cross axis and how flex-direction changes both

□​ I know the difference between justify-content (main axis) and align-items (cross axis)


□​ I can use flex-grow, flex-shrink, and flex-basis independently


□​ I can build a responsive Flexbox layout that degrades from three to one column


□​ I can vertically centre content in a flex container without a fixed height


<span style="color:tomato">I have impleneted these to my best, But more practice is required to truly master these concepts</span>
<hr>

## Final Questions

DAILY JOURNAL - WRITE YOUR ANSWERS IN YOUR LEARNING JOURNAL:


•​ When would you choose Flexbox over Grid and vice versa? Write three examples of each.

1. `flex-box` would be used when we want the contents to be dynamically allocated whereas `grid` is applied when the layout is more rigid
2. `flex-box` can be more useful in cases where we need to fill a certain amount off space ,  like a navigation bar
3. `flex-box` has higher tolerance to re-shape due to properties like `flex-shrink` , `flex-grow` , `flex-basis`

<span style="color:tomato">More precise answers require tommorrows excersise to be completed</span>

•​ Why is margin-top: auto useful in a flex column? How does it work?

Because it automatically alings so that as the website's viewport or size changes.. Hard coded margins may not behave as expected

Task 4 has one such Use-case implemented for nav-bar, where `margin-left : auto` was used to align central div in a horizontal flex-box

