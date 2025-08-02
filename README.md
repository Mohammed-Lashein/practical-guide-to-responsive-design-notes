Here I write my notes on following along with [practical guide to responsive design by kevin powell](https://youtu.be/x4u1yp3Msao).
_____
### What is the need for this css declaration for an `img` reset?

```css
img {
  max-width: 100%;
  display: block;
}
```

The above line of code makes the image adapt to the screen instead of overflowing the screen (and thus showing unnecessary horizontal scrollbar).

I have made a small recording to visualize the effect of the above css declaration (Note: that in the video, I just used `max-width: 100%;` because it just worked)

https://github.com/user-attachments/assets/98305f8d-67b7-46ed-b0de-23dac4cf0c67
____
### `width: 100%` vs `width: auto`
[This video explains it visually in a good way](https://youtu.be/-st14lUQD3U), but in a nutshell:
- `width: 100%`: will result in a body overflow if the element had a `margin`, because `100%` means "get all of the space of the container" whose value will be added to the margin.
- `width: auto`: won't cause any overflow. our element adapts to the space available within the viewport without overflowing. 
___
### CSS viewport insights 
Notes are taken from [this mdn article](https://developer.mozilla.org/en-US/docs/Web/CSS/CSSOM_view/Viewport_concepts) 
- Visual viewport: the part of the webpage that is currently visible in the browser
- Layout viewport: the part into which the browser draws a web page

When a user zooms in, the layout viewport **doesn't change** whereas the visual viewport is zoomed in.
___
### Make a responsive grid with no media queries
```css
.grid {
  display: grid;
  grid-template-columns: repeat(autofit, minmax(250px, 1fr))
}
```
That last line needs some explanation
- Normally, `repeat` function gets the 1st arg as a number, but there is a special case where it can get special keywords, like `autofit`.
In this case, the grid will try to make its children **fit** (pun intended) the grid and any empty grid cell its space will be distributed among other non-empty grid cells.