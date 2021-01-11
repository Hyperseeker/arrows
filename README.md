# Essence

`arrows.css` is a simple CSS utility library which allows you to append or prepend text arrows to any¹ HTML element.

¹ excluding `<iframe>`, `<video>`, `<embed>`, and `<img>`; potentially excluding `<option>`, `<audio>`, `<canvas>`, `<object>`, and `<applet>`; see [MDN on replaced elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element) for details

You can see the library in action on [my website](https://hyperseeker.stream/). Note that list arrows is a distinct class of features and is not featured in this library.

# Reasoning

I needed arrow decorations for [my website](https://hyperseeker.stream/).

The site's design system is simple and local, so I was able to implement a plain, clear, single-word class system.

Given how it turned out to be fairly self-sufficient, I decided to release it.

# Usage

As you would a regular CSS library.

If you don't know how that works, [this brief how-to](https://www.w3schools.com/css/css_howto.asp) may help.

Then, add the following classes to the element:

*for each type, at least one value is required*

* `.arrow`
* `.before` or `.after` (positioning relative to the element)
* `.up`, `.down`, `.left`, `.right`, or any combination of either axis

## Examples

* `<a class="arrow after right" href="https://example.com">Visit my wonderful site</a>`
* `the <span class="arrow before up">examples above</span>`
* `<p class="arrow after down right">To exit, press the red button in the lower right corner</p>`

# Pros

* Unicode-based  
  *no SVG, image, or JS overhead*
* works for eight directions  
  *North + East + South + West + NE / NW / SE / SW*
* can be positioned before or after the element
* animated in direction of the arrow on `:hover` and `:focus` by default
* diagonal arrows animation movement is adjusted  
  *no overmovement compared to orthogonal arrows*
* arrows are padded  
  *no odd flickering on hovering over arrow's previous position*
* animation can be removed from arrow by adding the `.static` class
* uses CSS variables  
  *offset values are calculated on the fly*  
  *helps maintain positioning despite user's browser zoom or used font*

# Cons

* Unicode-based  
  *requires an appropriate font to look good*  
  *site uses* [Inter](https://rsms.me/inter/)
* implies using no other class-based CSS framework  
  *most likely to conflict if used*
* the containing element must be `position: relative`  
  *set by* `.arrow`
* positioning is in the inline axis only  
  *left/right in most writing systems, so before/after element*
  
## To Do
  
- [ ] padding is imperfect for text  
  *prevents about one character's worth of selection*
- [ ] no default location  
  *have to declare either* `.before` *or* `.after` *explicitly*
- [ ] all arrows use `:before` pseudo-element, regardless of positioning  
  *can declare one arrow per element only*

# Notes

* Unicode ranges:
  - orthogonal arrows `←``↑``→``↓` 2190-2193
  - diagonal arrows `↖``↗``↘``↙` 2196-2199

# License

MIT