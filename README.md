# Grill

![Grill Logo](logo/logo_transparent-small.png)

Grill is not another Bootstrap, but a **mobile first**, **CSS-only** library based on [Grid Layout](//www.w3.org/TR/css-grid-1/) 
and written in [Sass](//sass-lang.com/), intended for quickly making layouts. Many CSS frameworks out there do too 
much, my main goal is to keep it stripped down to the minimum as possible. 

## Table of Contents

- [Usage](#usage)
- [Grid Classes](#grid-classes)
- [Helpers](#helpers)
- [Breakpoints](#breakpoints)
- [Implicit grid](#implicit-grid)
- [Donate](#donation)

## Usage

Because of the way grid works, you don't need two levels of html containers, one to declare a row and then another to
 declare the columns. With Grill, you declare the number of columns (template) directly on the top-level container. 
Nevertheless, since grids can be nested, any child of a grid container can also be a grid itself, having the `grid` 
class name on it and thus including its own columns declaration. 
  
### Disclaimer

CSS Grid is a huge, very powerful module in CSS. Due to the limitations of relying exclusively on classes, **Grill** 
isn't able to take advantage of Grid's full potential, but provides the necessary set of rules for the majority of the
  tasks you're going to face when it comes to making layouts. I suggest you to read [this very comprehensive article](https://css-tricks.com/snippets/css/complete-guide-grid/) 
to better understand the true power and benefits of CSS Grid.

## Grid classes

### Container

- **grid**: Defines and element as a grid container.

- **inline-grid**: Defines an element as an inline grid container.

- **cols**: From 2 to 12 (1 is the default), defines how many columns the grid will have. You
 can also add the breakpoint from which it will start having that number of columns. For example:

``` html
<div class="grid cols-2-sm cols-4-md cols-6-lg cols-8-xl"></div>
```

- **rows**: From 2 to 12 (1 is the default), defines how many rows the grid will have (though I don't encourage limiting
 this, I prefer setting the number of columns and leave the rows generate automatically). 
 You can also add the breakpoint from which it will start having that number of rows. For example:

``` html
<div class="grid rows-8-sm rows-6-md rows-4-lg rows-2-xl"></div>
```

- **gap**: The grid gutter, in `rem` units, from 1 to 5. If only one value is present, it'll apply to both sides (column
 and rows). You can use different values for both columns and rows in which case the first one will apply to
 column gap, and the second one to row gap. 
 
``` html
<div class="grid cols-2-sm cols-4-md gap-3-1"></div>
```
_Notice that you cannot use the same value for both axis in this mode, ie: `gap-3-3`, that would be redundant, instead
 you must just use `gap-3`._

- **grid-flow**: `-column`, `-row` (default) or `-dense`, it specifies the direction elements are going to flow along
 the grid.

``` html
<div class="grid cols-2-sm cols-4-md grid-flow-column"></div>
```

- **auto-cols**: From 2 to 12 (1 is the default). It defines how many portions of the remaining space will take columns 
that are added implicitly. 
For more info, see [MDN Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-columns).

``` html
<div class="grid cols-2-sm grid-flow-row auto-cols-3"></div>
```

- **auto-rows**: From 2 to 12 (1 is the default). It defines how many portions of the remaining space will take rows
 that are added implicitly. For more info, see [MDN Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-rows).

``` html
<div class="grid cols-2-sm grid-flow-column auto-rows-3"></div>
```

### Children

- **colspan**: used in any direct child of the grid container, indicates how many columns it will span. It also accepts
 breakpoints.

``` html
<div class="colspan-4-md colspan-6-lg"></div>
```

or, for all screen sizes:

``` html
<div class="colspan-6"></div>
```

- **rowspan**: used in any direct child of the grid container, indicates how many rows it will span. It also accepts
 breakpoints.

``` html
<div class="rowspan-4-md rowspan-6-lg"></div>
```

or, for all screen sizes:

``` html
<div class="rowspan-6"></div>
```

- **subgrid-cols**: if applied to a grid child, it will inherit the column template from the outer grid.

- **subgrid-rows**: if applied to a grid child, it will inherit the row template from the outer grid.

- **subgrid**: if applied to a grid child, it will inherit both column and row templates from the outer grid.

**Warning:** At the time of writing this, subgrid is only supported by Firefox. You may want to check if it's been adopted
by other browsers before using it: https://caniuse.com/#search=subgrid. 


### Alignment

When we say "block" and "inline" axes, we're referring to the vertical and horizontal axes respectively, according to
the [Box Alignment Specification](https://drafts.csswg.org/css-align/). 

- **align-items**: `-start`, `-center` or `-end`, specifies how the elements inside the grid cells will be aligned
 in the block axis; `-stretch` is the default value if you skip this class.

- **justify-items**: `-start`, `-center` or `-end`, specifies how the elements inside the grid cells will be 
aligned in the inline axis; `stretch` is the default value if you skip this class.

- **place-items**: `-start`, `-center` or `-end`, specifies how the elements inside the grid cells will be aligned 
in both axes; `stretch` is the default value if you skip this class.

- **align-content**: `-start`, `-center`, `-end`, `-space-around`, `-space-between` or `-space-evenly` specifies how 
  the content inside the grid will be aligned  in the block axis; `-stretch` is the default value if you skip this 
  class.

- **justify-content**: `-start`, `-center`, `-end`, `-space-around`, `-space-between` or `-space-evenly` specifies how 
  the content inside the grid will be aligned in the inline axis; `-stretch` is the default value if you skip this 
  class.

- **place-content**: `-start`, `-center`, `-end`, `-space-around`, `-space-between` or `-space-evenly` specifies how 
  the content inside the grid will be aligned in both axes; `-stretch` is the default value if you skip this class.

- **align-self**: `-start`, `-center` or `-end`, specifies how a single element within a grid cell will be aligned in 
the block axis; `stretch` is the default value if you skip this class.

- **justify-self**: `-start`, `-center` or `-end`, specifies how a single element within a grid cell will be aligned in 
the inline axis; `stretch` is the default value if you skip this class.

- **place-self**: `-start`, `-center` or `-end`, specifies how a single element within a grid cell will be aligned in 
both axes; `stretch` is the default value if you skip this class.


## Helpers

### Spacing

- **m-auto**: Auto margin (all axis)

- **mx-auto**: Auto margin (horizontal axis)

- **my-auto**: Auto margin (vertical axis)

All the following accept breakpoint suffix, ie: `mr-2-md`. Size measures are in *rem* units.

- **m**: Margin from 1 to 5 (all axis).

- **mx**: Margin from 1 to 5 (horizontal axis).

- **my**: Margin from 1 to 5 (vertical axis).

- **mt**: Margin top from 1 to 5

- **mb**: Margin bottom from 1 to 5

- **ml**: Margin left from 1 to 5

- **mr**: Margin right from 1 to 5

- **p**: Padding from 1 to 5 (all axis)

- **px**: Padding from 1 to 5 (horizontal axis)

- **py**: Padding from 1 to 5 (vertical axis)

- **pt**: Padding top from 1 to 5

- **pb**: Padding bottom from 1 to 5

- **pl**: Padding left from 1 to 5

- **pr**: Padding right from 1 to 5

### Text alignment

- **text-start**: Aligns text to the start according to your native reading orientation.
- **text-center**: Aligns text to the center.
- **text-end**: Aligns text to the end according to your native reading orientation.

### Accessibility

- **sr-only**: Using this class the element will be hidden to the GUI user but still accessible to screen readers and
 other assistive technologies.

## Breakpoints

- **sm**: Starting from 600px

- **md**: Starting from 960px

- **lg**: Starting from 1280px

- **xl**: Starting from 1440px

- **xxl**: Starting from 1920px

## Implicit grid

- If you don't specify any breakpoint at all, it'll assume the given number for all screen sizes, for example `cols-2
` means 2 columns on any screen size.
- If you include a class without a breakpoint and another which does have one, the first one will apply for any screen
 size below the other. For example if `cols-2 cols-6-lg`, the grid will have 2 columns until
  1280px and then 6 columns starting from that resolution. If there were more breakpoints present it'll continue as
   normal, meaning that `cols-2 cols-6-lg cols-8-xl` should result in 2 columns until 1280px, 6 columns from that
    point, and 8 columns from 1440px and beyond.
- Because the default number of columns and rows is 1, if you don't specify any breakpoint it'll assume 1
 column/row until the first given breakpoint. For example, using `cols-6-lg` alone will result in 1 column
  until 1280px and then it will start having 6 columns. If you want to define a number of columns/rows below *sm
  *, you should do it this way: `cols-2 cols-3-sm`.

## Donation

Did Grill save your day? I'd be thankful if you [buy me a coffee](https://www.buymeacoffee.com/fena). If you can
't, a star would motivate me. You also find me on [Patreon](https://patreon.com/fenavente) and 
[Paypal](https://paypal.me/adrianbenavente). In case you're in Argentina and use **Mercado Pago**, you can buy me a 
coffee through [Cafecito](https://cafecito.app/fena).
