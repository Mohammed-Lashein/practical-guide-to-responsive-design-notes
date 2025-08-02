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