# CSS to the rescue

Live Demo: https://sjorswijsman.github.io/css-to-the-rescue-2021/

## Weekly Progress
To track my progress during the 4 weeks of this course I documented the changes and experiments I did every week.

### Week 1
The first week I spent quite some time figuring out what I wanted to do for this project, eventually I decided I wanted to focus on CSS text manipulation. 

My first experiments were moving text along a set path. The results of those experiments looked like this:

![first experiment](https://s4.gifyu.com/images/first-experiment.gif)

[Commit](https://github.com/SjorsWijsman/css-to-the-rescue-2021/commit/1ddc337217dd9ebf3bfee13349c618e5dd68ce3b)

### Week 2
My next goal was to recreate a movie poster or album cover using mostly text and quotes/lyrics from the movie or album respectively. After some searching around I settled on recreating the Donnie Darko movie poster, which looks like this:

![Donnie Darko Movie poster](http://media.filmz.ru/photos/full/filmz.ru_f_31514.jpg)

After some playing around I got a decent layout of the poster in HTML:

![decent layout](https://s4.gifyu.com/images/decent-layout.gif)

[Commit](https://github.com/SjorsWijsman/css-to-the-rescue-2021/commit/55ef12eedadf7850add165ac1b405499639aebe5)

Eventually I added Frank's (the bunny) face to the layout as an overlay with the text incorperated inside his face:

![frank overlay](https://s4.gifyu.com/images/frank-overlay.gif)

[Commit](https://github.com/SjorsWijsman/css-to-the-rescue-2021/commit/bae809557592884bf2b38b2ec8654b372296ab00)

### Week 3
The third week was spent trying to fit the text inside of Frank's face. This proved to be more difficult than I initially hoped, as placing text around an object is a lot easier to do, for example with `shape-outside`. Sadly there's no way to easily fit text inside of a shape (`shape-inside` might be [coming soon](https://www.w3.org/TR/css-shapes/#intro) however), there are some workarounds, but most of them boil down to inverting the shape and using `shape-outside`. Which I didn't want to use, as it'd make creating the bunny's smaller details harder and give me less creative freedom. I instead decided to keep it how it was and work on making the text inside the bunny more interactive, the first step was to make it scrollable:

![scrollable text](https://s4.gifyu.com/images/scrollable-text.md.gif)

[Commit](https://github.com/SjorsWijsman/css-to-the-rescue-2021/commit/cbdda5521589bc44fe742c56699cd181daad36be)

### Week 4 & Result
The last week was mostly spend on making the poster more interesting and working on adding pseudorandomness to the text, hopefully adding some extra chaos to the picture. I did this by using the [cicada principle](https://devopedia.org/cicada-principle). By selecting every prime number in range of all the children and adding styling to those selectors you can create patterns that never repeat, making the styling look "random". I expanded on this concept by giving every selector a random value that gets added to a total "cicada" value. This value can then be used to add numerical styling, for example:

```css
transform:
  rotate(calc(var(--cicada) * 2deg))
  skewX(calc(var(--cicada) * 2deg))
  translateZ(calc(var(--cicada) * 0.4rem));
font-size: calc(var(--cicada) * 0.1rem + 0.8rem);
filter: blur(calc(var(--cicada) * -0.05rem));
opacity: calc(1 / var(--cicada) + 0.7);
```

The result of this and end result of the project looks like the following (also viewable [here live](https://sjorswijsman.github.io/css-to-the-rescue-2021/)):

![result](https://s4.gifyu.com/images/resultef120156f7870c45.gif)

[Commit](https://github.com/SjorsWijsman/css-to-the-rescue-2021/commit/887421fd60b0496934114d1cf1d1807a3717e1ff)
