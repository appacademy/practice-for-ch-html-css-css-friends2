# CSS Friends, Part 2

It's time to finish your CSS Friends project! Just download the starter repo
from the `Download Project` button at the bottom of this page to get started.

> **Note:** The starter repo contains additional images and features that your
> Part 1 solution lacks.

## Phase 0: Sidebar

### Topics

- Positioning
- [Pseudo-selectors][t-pseudo-selectors]

### Screenshots

- [Screenshot A][ss-06-a]
- [Screenshot B][ss-06-b]
- [Live][live-06]

Divide the sidebar up into three sections: `.profile-picture`, `.profile-info`,
and `.profile-nav`.

Have the `.profile-picture` be a link that contains an image tag with the
provided `./images/cat.jpg` picture. Make the link a `block` element and style
it. Thanks to your earlier reset, the image will now expand to fill the full
width of the link.

To pull the `.profile-picture` partly out of its sidebar section, use a negative
`margin-top`. This is better than absolute positioning, as it is still in the
document flow and won't leave a gap but will pull everything up with it.

To make sure it is in front of the `.content-header` section, you will have to
position it `relative`. You do not need to nudge it (we used `margin-top` to do
that) or give it a z-index. As they're now both `relative`, order of appearance
on the page dictates the stacking order. This is in our favor, as
`.profile-picture` is declared later.

To get the divider lines between all the `.profile-nav` list elements, but also
at the top and bottom, you'll want to use a pseudo selector like `:first-child`,
`:last-child`, or `:nth-child()`.

### Before you move on

**Remember!** All of your CSS files are included in the __cats.html__ file
through the use of `<link>` tags in the document's `<head>`:

```html
<head>
  <meta charset="utf-8">
  <title>App Academy Friends</title>
  ...
  <link rel="stylesheet" href="css/06-sidebar.css" type="text/css">
</head>
```

Phase 0's `<link>` tag is already included, but you'll be responsible for adding
the rest!

[ss-06-a]:
  https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/06-sidebar-a.png
[ss-06-b]:
  https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/06-sidebar-b.png
[live-06]: http://appacademy.github.io/css-friends/solution/06-sidebar.html
[t-pseudo-selectors]: http://css-tricks.com/pseudo-class-selectors/

## Phase 1: Online

### Topics

- [Positioning][t-positioning]
- [Overflow][t-overflow]
- [Transform][t-transform]
- [Letter-spacing][t-letter-spacing]
- [Text-transform][t-text-transform]
- [Box-shadow][t-box-shadow]

### Screenshots

- [Screenshot A][ss-07-a]
- [Live][live-07]

Celebrate being online with a nice ribbon! Put an `.online` element inside of
the `.profile-picture` link. Position it absolute to be on top of the image.
Then go bonkers styling it using fancy `transform` properties like `rotate()`
and `translateX()`. Pay attention to typography and don't forget to add a tiny
`box-shadow`.

[ss-07-a]: https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/07-online-a.png
[live-07]: http://appacademy.github.io/css-friends/solution/07-online.html

[t-transform]: https://developer.mozilla.org/en-US/docs/Web/CSS/transform
[t-letter-spacing]: https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing
[t-text-transform]: https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform
[t-box-shadow]: https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow
[t-positioning]: https://www.w3schools.com/css/css_positioning.asp
[t-overflow]: https://developer.mozilla.org/en-US/docs/Web/CSS/overflow

## Phase 2: Thumbs

### Topics

- [Border-radius][t-border-radius]
- [Pseudo-content][pseudo-content]
- [Positioning][t-positioning]
- [Transform][t-transform]
- [Triangles][t-triangles]

### Screenshots

- [Screenshot A][ss-08-a]
- [Screenshot B][ss-08-b]
- [Live][live-08]

A grid of friends! Use a list and flexbox every `<li>`! Spacing them out
properly will be tricky. You will need to use `:nth-child()` pseudo-selectors to
add some left and right margin to the middle of every three `<li>`s.

Create a `.thumb` class to style the links that contain the thumbnails. You can
use the same `../docs/images/cat.jpg` picture for the `<img>` tag. You will want
to reuse this `.thumb` class later.

Add `title` attributes containing friend names to the link tags. You should have
something like: `<a href="#" class="thumb" title="Jonathan">`. Then use
`:before` pseudo-content to grab this title and inject it into the link. Style
this to make it a tool tip, making it a `block` element and position it
absolute.

To position an `absolute` element in the center relative to its parent, use a
combination of `left: 50%` and `transform: translateX(-50%)`. The `left`
percentage is relative to its parent and will set the current element's leftmost
pixel to half its parent's width. Since this is too far to the left, you have to
adjust this by subtracting half our own width. The `translateX()` value takes a
percentage relative to itself, which is exactly what you need.

To create a little triangle below the tooltip, you'll need to inject more
pseudo-content. Fortunately, you have two injection points, `:before` and
`:after`. Since you used `:before`, you will now use `:after`. Look at [this
demo][t-triangles] for a demonstration of how you can make a triangle out of
borders.

If you'd like an additional hint, check out this [tool tip][t-tooltip] demo. But
give it a shot yourself first!

[ss-08-a]:
  https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/08-thumbs-a.png
[ss-08-b]:
  https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/08-thumbs-b.png
[live-08]: http://appacademy.github.io/css-friends/solution/08-thumbs.html
[t-triangles]: http://appacademy.github.io/css-demos/triangle.html
[t-tooltip]: http://appacademy.github.io/css-demos/tooltip.html
[t-border-radius]:
  https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius
[pseudo-content]: https://www.w3schools.com/css/css_pseudo_elements.asp

## Phase 3: Forms

### Topics

- [Pseudo-selectors][t-pseudo-selectors]
- [Box-shadow][t-box-shadow]
- [Border-radius][t-border-radius]
- [Calc][t-calc]

### Screenshots

- [Screenshot A][ss-09-a]
- [Screenshot B][ss-09-b]
- [Screenshot C][ss-09-c]
- [Screenshot D][ss-09-d]
- [Live][live-09]

Reuse your `.thumb` class. Use flexbox to position the thumbnail and the form
next to each other. Wrap your inputs and labels in container elements with an
`.input` class. Wrap the button in a `.submit` container. Style them so you can
reuse them. Pay special attention to the `:focus` and ':active' pseudo-classes.

**Bonus:** CSS can do math too! Though not required today, you may use the
`calc()` function. It can be especially nice to do math with combined units. For
instance, you can easily subtract 100px off of a 100% width by setting `width:
calc(100% - 100px)`. You can do addition, subtraction, multiplication, and
division. You can even use parentheses to denote order.

[ss-09-a]: https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/09-forms-a.png
[ss-09-b]: https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/09-forms-b.png
[ss-09-c]: https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/09-forms-c.png
[ss-09-d]: https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/09-forms-d.png
[live-09]: http://appacademy.github.io/css-friends/solution/09-forms.html
[t-calc]: https://developer.mozilla.org/en-US/docs/Web/CSS/calc

## Phase 4: Posts

### Topics

- [Pseudo-content][pseudo-content]
- [Calc][t-calc]

#### Screenshots

- [Screenshot A][ss-10-a]
- [Live][live-10]

Crush this using semantic tags and your flexbox skills. How about using
pseudo-content to inject little bullets `·` in between the list items?

[ss-10-a]:
  https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/10-posts-a.png
[live-10]: http://appacademy.github.io/css-friends/solution/10-posts.html

## Phase 5: Icons

### Topics

- [Pseudo-selectors][t-pseudo-selectors]
- [Background-size][t-background-size]
- [Background-position][t-background-position]
- [Overflow][t-overflow]

#### Screenshots

- [Screenshot A][ss-11-a]
- [Screenshot B][ss-11-b]
- [Live][live-11]

Icons make things look so good! And lucky you, you're going to use a technique
called a *sprite*. This is one image file that contains many smaller images. You
combine them to dry up your CSS and--most importantly--to reduce HTTP request
overload. You only have to fetch one image instead of many. This makes things
crazily snappy!

Check out your [sprite][sprite]. Then look at the [specs][specs].

You will create a slew of icon classes, one for each icon. You will prefix each
class with `.icon-`. Let's start off with the post icons: create classes for
`.icon-comment`, `.icon-reblog`, and `.icon-favorite`.

Add these classes to the `<a>` tags you wrote in the previous phase.

Back in your CSS, you can select all of these classes using the
`[class*="icon-"]` pseudo-selector. Let's first write some general rules that
apply to all icons. Set the supplied __../docs/images/sprite.png__ image as the
background image. You will want to set the `background-size` property to the
specs' sprite size, as the sprite image is in double resolution for retina
screens.

Then set the display property of all icons to `inline-block`. This allows us to
set a width and height. Set a `width` and `height` of `25px` as per the specs.
Go look at the results. Notice the background image with the text on top of it.

You want to get rid of the text, but you do not want to take it out of your
HTML, as it conveys meaning. Let's use CSS to push the text out of the box!
First add an `overflow: hidden` rule. See how that clips off the text at the
sides?

Now let's push the text out completely. Remember how padding is part of an
element and shows the background image? Let's use a `padding-top` that is equal
to the height, and set the `height` to `0`. This effectively pushes the text
outside the box, as it does not fit in a `0` height element. Your overflow
settings then proceed to clip it off. Check it out!

Next, start showing the correct part of the sprite for each class you wrote.
In each individual icon class selector you will only have to set the
`background-position` coordinates.

Once you have these in place, also create selectors with the `:hover` state.

For the small icons you're going to use the `.icon-small-` prefix. Go ahead and
flesh those out.

You can then select all of them with the `[class*="icon-small-"]` selector.
Notice how the general rules of your earlier selector will also apply. You can
override the `width` and `padding-top` for the small icons.

When it comes to applying these icons to your HTML, you don't want these smaller
icons hiding the text of the links; rather, you want them to be an addition. For
this, you will repurpose the `<i>` tag, which seems suitable for an icon.

Go ahead and add empty `<i>` tags with icons classes inside of links on the
page. You'll end up with something like this: `<a href="#"><i
class="icon-small-wall"></i> Wall</a>`.

[ss-11-a]: https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/11-icons-a.png
[ss-11-b]: https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/screenshots/11-icons-b.png
[live-11]: http://appacademy.github.io/css-friends/solution/11-icons.html
[specs]: https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/SPECIFICATIONS.md
[sprite]: https://assets.aaonline.io/fullstack/html-css/micro-projects/css-friends/docs/images/sprite.png
[t-background-position]: https://developer.mozilla.org/en-US/docs/Web/CSS/background-position
[t-background-size]: https://developer.mozilla.org/en-US/docs/Web/CSS/background-size
