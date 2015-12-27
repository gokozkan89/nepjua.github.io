+++
date = "2015-12-27T04:16:31+02:00"
draft = false
description = ""
title = "Disable inactive pane overlay in atom"
aliases = [
	"a-cool-menu-button"
]
type = "post"
+++

Sometimes i have two components that does similar things and i want to compare
them side by side. I use split pane feature in atom to do this but when you
use split panes atom puts an overlay over inactive pane and i really hate that
today i decided to disable that i googled if there is any option to do that. I
couldn't find anything on web so i decided to disable it myself. I love how you
can easily customize atom using web developer tools since atom uses web
technologies.

Anyway here is css to disable that:

```css
/* disable inactive pane overlay */
atom-pane:not(.active) {
  opacity: inherit;
}

atom-pane-container atom-pane {
  background-color: inherit;
}

atom-pane:not(.active) atom-text-editor {
  background-color: inherit;
}
```

If you don't know where to add this code, here is how:

- Hit `Ctrl + Shift + P` ( `Cmd + Shift + P` for OSX )
- Start typing `open your stylesheet` when you see `Open Your StyleSheet` hit
`Return`
