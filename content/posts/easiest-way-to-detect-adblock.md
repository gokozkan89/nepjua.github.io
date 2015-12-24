+++
date = "2014-11-04T00:46:44+02:00"
draft = false
title = "Easiest way to detect adblock"
slug = "easiest-way-to-detect-adblock"
aliases = [
	"easiest-way-to-detect-adblock"
]
type = "post"
+++
Today i wanted to share a super easy method to detect adblock. I discovered that any path that matches a regexp like `/ad/i` would be blocked by adblocker. I just try to fetch a dummy image named `ads.png` and check if the request was successfull. Here is a simple code with jQuery:

```language-javascript
$.ajax({
  url: '/ads.png',
  error: function() {
    console.log("WTF man i thought you were a friend, go close your adblocker.");
  },
  success: function() {
    console.log("Cool bro, you're a good friend");
  }
});
```
