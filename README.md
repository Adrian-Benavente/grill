# Grill

![Grill Logo](logo/logo_transparent-small.png)

Grill is not another bootstrap, but a **mobile first**, **CSS-only** library based on Grid Layout and written in Sass, intended for quickly making layouts.
Many CSS frameworks out there do too much, my main goal is to keep it stripped down to the minimum possible. 

## Table of Contents

- [Usage](#usage)
- [Grid Classes](#grid-classes)
- [Helpers](#helpers)
- [Breakpoints](#breakpoints)
- [Implicit grid](#implicit-grid)
- [Donate](#donation)

## Usage

Because of the way grid works, you don't need two levels of html containers, one to declare a row and then another to declare the columns. In Grill, you declare the number of columns directly on the top-level container. Nevertheless, since grids can be nested, any child of a grid container can also be a grid, having the `grid` class name on it and thus including its own columns declaration. I suggest you to read [this very comprehensive article](https://css-tricks.com/snippets/css/complete-guide-grid/) to better understand the great power and benefits of CSS Grid.

## Grid classes

### Container

- **grid**: Tells an HTML element to become a grid container.

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
 and rows). You can use different values for both columns and rows in which case the first one will belong to
 column gap, and the second one to row gap. 
 
``` html
<div class="grid cols-2-sm cols-4-md gap-3-1"></div>
```
_Notice that you cannot use the same value for both axis in this mode, ie: `gap-3-3`, that would be redundant, instead
 you must use `gap-3`._

- **grid-flow**: `-column`, `-row` (default) or `-dense`, it specifies the direction elements are going to flow along
 the grid.

``` html
<div class="grid cols-2-sm cols-4-md grid-flow-column"></div>
```

- **auto-cols**: From 2 to 12 (1 is the default). It defines how many portions of the remaining space will take columns that are added
 implicitly. For more info, see [MDN Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-columns).

``` html
<div class="grid cols-2-sm grid-flow-row auto-cols-3"></div>
```

- **auto-rows**: From 2 to 12 (1 is the default). It defines how many portions of the remaining space will take rows
 that are added implicitly. For more info, see [MDN Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-rows).

``` html
<div class="grid cols-2-sm grid-flow-column auto-rows-3"></div>
```

### Children

- **colspan**: used in any direct child of the grid container, indicates how many columns it shall span. It also accepts
 breakpoints.

``` html
<div class="colspan-4-md colspan-6-lg"></div>
```

or simply:

``` html
<div class="colspan-6"></div>
```

- **rowspan**: used in any direct child of the grid container, indicates how many rows it shall span. It also accepts
 breakpoints.

``` html
<div class="rowspan-4-md rowspan-6-lg"></div>
```

or simply:

``` html
<div class="rowspan-6"></div>
```

- **align-items**: `-stretch`, `-start`, `-center` or `-end`, specifies how elements within the grid will be aligned
 in the vertical axis.

- **justify-items**: `-stretch`, `-start`, `-center` or `-end`, specifies how elements within the grid will be aligned in the horizontal axis.

- **align-self**: `-stretch`, `-start`, `-center` or `-end`, specifies how a child element will be aligned in the
 vertical axis.

- **justify-self**: `-stretch`, `-start`, `-center` or `-end`, specifies how a child element will be aligned in the horizontal axis.

## Helpers

### Spacing

- **m-auto**: Auto margin (all axis)

- **mx-auto**: Auto margin (horizontal axis)

- **my-auto**: Auto margin (vertical axis)

All the following accept breakpoint suffix, ie: `mr-2-md`. Size measures are in *rem* units.

- **m-**: Margin from 1 to 5 (all axis).

- **mx-**: Margin from 1 to 5 (horizontal axis).

- **my-**: Margin from 1 to 5 (vertical axis).

- **mt-**: Margin top from 1 to 5

- **mb-**: Margin bottom from 1 to 5

- **ml-**: Margin left from 1 to 5

- **mr-**: Margin right from 1 to 5

- **p-**: Padding from 1 to 5 (all axis)

- **px-**: Padding from 1 to 5 (horizontal axis)

- **py-**: Padding from 1 to 5 (vertical axis)

- **pt-**: Padding top from 1 to 5

- **pb-**: Padding bottom from 1 to 5

- **pl-**: Padding left from 1 to 5

- **pr-**: Padding right from 1 to 5

### Text alignment

- **text-start**: Aligns text to the start in your native reading orientation.
- **text-center**: Aligns text to the center.
- **text-end**: Aligns text to the start in your native reading orientation.

### Accessibility

- **sr-only**: Using this class the element will be hidden to the GUI user but still accessible to screen readers and
 other assistive technologies.

## Breakpoints

- **-sm**: Starting from 600px

- **-md**: Starting from 960px

- **-lg**: Starting from 1280px

- **-xl**: Starting from 1440px

- **-xxl**: Starting from 1920px

## Implicit grid

1. If you don't specify any breakpoint at all, it'll assume the given number for all screen sizes, for example `cols-2
` means 2 columns all the time.
2. If you include a class without a breakpoint and another which does have one, the first one will apply for any screen
 size below the other. For example if `cols-2 cols-6-lg`, the grid will have 2 columns until
  1280px and then 6 columns starting from that resolution. If there were more breakpoints present it'll continue as
   normal, meaning that `cols-2 cols-6-lg cols-8-xl` should result in 2 columns until 1280px, 6 columns from that
    point, and 8 columns from 1440px and beyond.
3. Because the default number of columns and rows is 1, if you only use the breakpoint declarations it'll assume 1
 column/row until the first given breakpoint. For example, using `cols-6-lg` alone will result in 1 column
  until 1280px and then it will start having 6 columns. If you want to define a number of columns/rows below *sm
  *, you should do it this way: `cols-2 cols-3-sm`.

## Donation

Did Grill save your day? I'd be thankful if you [buy me a coffee](https://www.buymeacoffee.com/fena). If you can
't, a star would motivate me. You also find me in [Patreon](https://patreon.com/fenavente) and [Paypal](https://paypal.me/adrianbenavente). In case you
're in Argentina and use **Mercado Pago**, you can buy me a coffee via [Cafecito](https://cafecito.app/fena).
