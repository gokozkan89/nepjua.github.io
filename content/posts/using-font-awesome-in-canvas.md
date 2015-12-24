+++
date = "2014-10-26T23:51:11+02:00"
draft = false
title = "Using font-awesome in canvas"
slug = "using-font-awesome-in-canvas"
aliases = [
	"using-font-awesome-in-canvas"
]
type = "post"
+++
Yesterday i wanted to use font-awesome in canvas. I researched and found out that we can use glyphs in canvas similar to how we use them in css. You just set font to "FontAwesome" and set content to the unicode character and you're ready to go.

I did some testing in browser console and with a little bit of effort i placed my icon in the canvas.

I thought that hard part was solved but the real hard part was to get unicode characters for each icon in font-awesome. One can get a json with doing some text editing to font-awesome.css, but i wanted to make a generic solution that can be applied to any glyph you want on internet.

The idea was that you'll have a function that gets unicode character of the glyph from the icon's dom element. For example you have font-awesome icon like:

```language=html
<i class="fa fa-bus"></>
```

This function will return `"\uF207"` when you call it with the DomElement instance. I found out [here](http://pankajparashar.com/posts/modify-pseudo-elements-css/) that we can get computed style of any element we want. Then i wrote a tiny script that gets all font-awesome glyphs when you run it on font awesome's icons page. Here is the script:

<script src="https://gist.github.com/yasinuslu/f03eafd9237b12f306d4.js?file=fa_extractor.js"></script>

And here is the complete list of font-awesome icons.

<script src="https://gist.github.com/yasinuslu/f03eafd9237b12f306d4.js?file=fa.js"></script>
