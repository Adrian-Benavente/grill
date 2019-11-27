# Grill

![Grill Logo](img/logo.png)

Grill is not another bootstrap, but a **mobile first**, **CSS only** framework based on Grid and written in Sass, intended for quickly making lay outs.
Many CSS frameworks out there do too much, my main goal is to keep it stripped-down to the minimum as much as possible. 

## Documentation

As I work on improving the documentation, you can take a look at the demo *index.html* file. Drag & drop it in your favorite browser.

### Usage

#### Grid classes

- **grid**: Tells an HTML element to become a grid container:

- **cols**: (From 1 to 12), defines how many columns the grid will have. You can also add the breakpoint from which it will start having that number of columns. For example:

``` html
<div class="grid cols-2-sm cols-4-md cols-6-lg cols-8-xl"></div>
```

- **gap**: The grid gutter, in `rem` units, from 1 to 5. Psst! You can add the `-half` suffix to use half a rem as your measure:

``` html
<div class="grid cols-2-sm cols-4-md cols-6-lg cols-8-xl gap-3-half"></div>
```

- **grid-flow**: `-column` or `-row`, though "row" is the default value, it specifies how elements within the grid are going to flow.

``` html
<div class="grid grid-flow-column cols-2-sm cols-4-md cols-6-lg cols-8-xl gap-3-half"></div>
```

- **colspan**: used to tell a row how many columns must span. It also accepts explicit breakpoints.

``` html
<div class="colspan-4-md colspan-6-lg"></div>
```

or simply

``` html
<div class="colspan-6"></div>
```

- **rowspan**: used to tell a column how many rows must span. It also accepts explicit breakpoints.

``` html
<div class="rowspan-4-md rowspan-6-lg"></div>
```

or simply

``` html
<div class="rowspan-6"></div>
```

- **alig-items**: `-stretch`, `-start`, `-center` or `-end`, specifies how elements within the grid will be aligned in the vertical axis.

- **justify-items**: `-stretch`, `-start`, `-center` or `-end`, specifies how elements within the grid will be aligned in the horizontal axis.

- **alig-self**: `-stretch`, `-start`, `-center` or `-end`, specifies how a child element will be aligned in the vertical axis.

- **justify-self**: `-stretch`, `-start`, `-center` or `-end`, specifies how a child element will be aligned in the horizontal axis.

#### Spacing classes

- **m-auto**: Auto margin (all axis)

- **mx-auto**: Auto margin (horizontal axis)

- **my-auto**: Auto margin (vertical axis)

##### All the following accept breakpoint suffix

- **m-**: Margin from 0 to 5 (all axis).

- **mx-**: Margin from 0 to 5 (horizontal axis).

- **my-**: Margin from 0 to 5 (vertical axis).

- **mt-**: Margin top from 0 to 5

- **mb-**: Margin bottom from 0 to 5

- **ml-**: Margin left from 0 to 5

- **mr-**: Margin right from 0 to 5

- **p-**: Padding from 0 to 5 (all axis)

- **px-**: Padding from 0 to 5 (horizontal axis)

- **py-**: Padding from 0 to 5 (vertical axis)

- **pt-**: Padding top from 0 to 5

- **pb-**: Padding bottom from 0 to 5

- **pl-**: Padding left from 0 to 5

- **pr-**: Padding right from 0 to 5

#### Color classes

- **text-**: Text color (`primary`, `success`, `warning`, `danger`, `dark`, `darker` or `light`)

- **bg-**: Background color (`primary`, `success`, `warning`, `danger`, `dark`, `darker` or `light`)

#### Breakpoints

- **-sm**: Starting from 576px

- **-md**: Starting from 768px

- **-lg**: Starting from 990px

- **-xl**: Starting from 1200px

#### Units

All units are in `rem` but as I mentioned before, you can add `-half` suffix to reduce it to the half.

#### Colors

- **primary**: #0b6daa;
- **success**: #00923f;
- **warning**: #f4ae00;
- **danger**: #cd2a21;
- **dark**: #222222;
- **darker**: #3d3d3d;
- **light**: #d1d3d4;

#### Icons

Grill uses material icons, check [the official site](https://material.io/tools/icons/?style=baseline) for the glyph codes. All classes are prefixed with `icon-` followed by the icon code and must be accompanied by the `icon` class. For example:

``` html
<span class="icon icon-museum"></span>
```
