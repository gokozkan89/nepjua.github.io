+++
date = "2014-08-14T00:01:25+03:00"
draft = false
title = "Making a game"
slug = "making-a-game"
aliases = [
	"making-a-game"
]
type = "post"
+++
I'm not very experienced at game developing. I started developing games 4 months ago and my first game is [Circular 2048](https://play.google.com/store/apps/details?id=com.ttygames.circular2048&hl=en) which taught me many things about game development.

After looking into [gabrielecirulli's 2048](https://github.com/gabrielecirulli/2048) we thought it will be easy to develop circular version of 2048. We couldn't be more wrong.

We first started with [Phaser](http://phaser.io/) and started drawing shapes instead of using sprites we resulted into drawing really crappy visuals not mentioning awful performance then we found a better way to draw our shapes and fixed crappy visuals. But that didn't solve our performance problems and we start thinking of ways to use sprites.

We designed square sprites for all the tiles and used masks to clip our sprites to be circular. We achieved better visual's and a little better performance but it wasn't even performant at browser. Then we started looking for other engines and found cocos2dx-js, that seemed good at theory so we start making experiments with it. We rendered circles with different radius on every frame to see performance but it wasn't good enough to port our game to cocos2dx-js.

We decided to gove another shot for phaser and decided to cache our masks at booting and then used that on game. We definitely fixed performance problems with it but overlapping tiles bump into our life. All of these took nearly 1 month and right as we started losing our motivation we realized that we needed a library that's meant to draw shapes not sprites. That was the moment we found that we can use svg to render our shapes.

At first we started using RaphaelJS library and it was really good but we were having problems with syncing tiles on screen with the tiles in our game then we go back to research for another library. That was the moment we met with the magical world of d3js. They had a perfect pattern that lets you easily sync your data and it's visual representation.

We completed our game and started focusing on other things such as increasing user experience on mobile devices.

You can install "Circular 2048" from:

- https://play.google.com/store/apps/details?id=com.ttygames.circular2048

- https://itunes.apple.com/us/app/circular-2048/id902346134?ls=1&mt=8
