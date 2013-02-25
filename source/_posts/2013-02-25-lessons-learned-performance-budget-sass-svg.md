---
layout: post
title: "Lessons Learned Building the New dmolsen.com: Static, A Performance Budget, Sass & SVG"
date: 2013-02-25 14:10
permalink: /2013/02/25/lessons-learned-static-performance-budget-sass-svg
---
Building off of my _[Re-introduction](/2013/02/25/a-re-introduction)_ post I wanted to share some of the things that I learned as I built the new, responsive edition of _dmolsen.com_. I figure that my experience with doing this might provide some insight to other folks looking to integrate new techniques and technology into their own projects. The [source for the site is on GitHub](https://github.com/dmolsen/dmolsen.com). All projects start with requirements...

## Dropping WordPress &amp; Going Static with Octopress

I've been toying with the idea of dropping WordPress for a while. While it was easy to get up and running it never seemed like it was a good fit for me. It has to be updated constantly, the post editor is a serious pain in the ass, and it sucks down RAM. Between not really getting enough traffic to justify my RAM-driven hosting costs and the fact that the post creation process was more of a hinderance than a help I decided to make a big change with this redesign. Out went WordPress and in came old-school static HTML.

One big plus of using a CMS like WordPress though is having the ability to use templates. To make sure I still had this feature I looked for a good static site generator. It would give me the flat files I wanted but, hopefully, make it easier to maintain my site. I finally settled on [Octopress](http://octopress.org). 

To be clear, Octopress definitely has its own drawbacks. Upgrading [Ruby](http://www.ruby-lang.org/en/) on my Mac was a serious headache and I'm not a big fan of [Liquid-based templates](http://liquidmarkup.org). That said, I feel like I'm back in control of every aspect of my site. I was able to quickly stub out my own templates and design. I can now write my posts in [Markdown](http://daringfireball.net/projects/markdown/basics), a format I love, and I can write whenever I have the desire too because the files are all local to my computer.

## The 50K Performance Budget

The second major decision was setting my performance budget for the basic template for the site. Both Tim Kadlec ([@timkadlec](https://twitter.com/tkadlec)) and Clearleft ([@clearleft](https://twitter.com/clearleft)) have written on this topic recently. See _[Setting a Performance Budget](http://timkadlec.com/2013/01/setting-a-performance-budget/)_ and _[Responsive Design on a Budget](http://clearleft.com/thinks/responsivedesignonabudget/)_ respectively. This is a technique that our team had used for our 2011 responsive holiday card website (_sadly, it's is no longer online_). The budget for that had been 100K. For this site I wanted it to be 50K. A very aggressive goal but, hey, why not?

If you don't count web fonts the basic template easily fits within my 50K budget. My CSS, JavaScript, images, and mark-up only add up to 39K. Cut out Google Analytics and [Gaug.es](http://get.gaug.es) and the page weight drops to 23K. Unfortunately, I'm a sucker for web fonts. Because of my lack of design skills as well as the large blocks of text that naturally make up a blog I knew type was going to have to be an important visual component of my site.

I ended up using two fonts, [Roboto](http://www.google.com/webfonts/specimen/Roboto) and [Roboto Condensed](http://www.google.com/webfonts/specimen/Roboto+Condensed), that total 69K. Combining that number with the other assets the total weight for the basic template for my site ends up being around 109K.

Did I blow my budget by including the fonts? Sure. **But performance optimization is, like many things, a compromise.** The type face makes a huge difference, I think. The 50K goal was completely arbitrary and aggressive but having a tight ceiling made me think more critically about design and feature choices. In the future my performance budgets will also include things like total number of requests and a max time-to-document-ready threshold.

## Sass is Snazzy

[Sass](http://sass-lang.com), a CSS pre-processer, has blown up in our office. Between being baked into our new CMS, a _[Build Responsively](http://buildresponsively.com)_ workshop, and the introduction of [CodeKit](http://incident57.com/codekit/) it seems like everyone here is using it. I hadn't had the opportunity to use it but, since it is included as part of Octopress, I figured I'd give it a whirl. **I love it.** Here is how it helped me:

*    Being able to have a large number of SCSS files [organized by which region of the page the styles affected](https://github.com/dmolsen/dmolsen.com/tree/master/sass/partials) that get merged into one file in production made the whole process of remembering where styles were and tweaking them that much faster and easier.
*    [Variables](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html#variables_) meant that I could [tweak a breakpoint](https://github.com/dmolsen/dmolsen.com/blob/master/sass/_base.scss) and be assured every element affected by the change would be updated.
*    [Nesting](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html#nested_rules) reduced what I had to type and, again, helped me [organize my styles](https://github.com/dmolsen/dmolsen.com/blob/master/sass/partials/_navigation.scss) better.
*    I only used one [mixin](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html#mixins) in my project but I can see how, for example if you needed to create cross-platform gradients,  it could make your life a whole lot easier.

My site is simple and I barely scratched the surface of [what Sass can do](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html). And, to be clear, you don't have to use Octopress to take advantage of Sass.

## SVG: A Different Kind of Logo

One of the challenges that I set for myself when I started redesigning this site was to try to create a logo that required only CSS. Unfortunately, using CSS to clip text to a circle isn't very well-supported across browsers. Once I had settled on the clipped look, though, I really wanted it so I looked at another solution, [SVG](http://en.wikipedia.org/wiki/Scalable_Vector_Graphics). Within two hours I went from basically not knowing anything about SVG to the hot logo that you see today. It's really just a [simple text file](https://github.com/dmolsen/dmolsen.com/blob/master/source/images/logo.svg) with a linked web font.

While straightforward to build I don't think I've made the best use of SVG. The web font works on most SVG-supporting browsers but fails, for example, on the default browser on Android 4.2. This results in a shortened logo. Also, by linking to a web font I took what is a nicely performant 0.7K text file and essentially turned it into an 18K text file-web font combo. An image would be way better in this case. That said, I think SVG offers promise as a format. Being high-DPI and responsive-layout friendly are definite plusses. By the way, take a look at [the source for the header](https://github.com/dmolsen/dmolsen.com/blob/master/source/_includes/header.html) and you can see how I provide a fallback for browsers that don't support SVG at all.

If you're interested in learning more about SVG and how you might be able to take advantage of it check out David Bushell's ([@dbushell](https://twitter.com/dbushell)) two SVG articles, _[A Primer to Front-end SVG Hacking](http://dbushell.com/2013/02/04/a-primer-to-front-end-svg-hacking/)_ and _[Resolution Independence with SVG](http://dbushell.com/2013/02/04/a-primer-to-front-end-svg-hacking/)_.

## Other Interesting Bits

This post is getting quite long! Some other things that I found useful/interesting as I put together the new version of my site:

*    **HTML5:** Rather than use a JavaScript solution for backwards compatibility you might notice that I actually use `<divs>` nested within the HTML5 elements. All of my styles hook into these elements. It's not the most semantic solution but relying on JavaScript seemed odd to me.
*    **nth-child():** This pseudo-selector melted my brain for a little bit (_for the son of a math teacher I really suck at math_) but once I got a handle on it was incredible useful. The navigation at small viewports is completely driven by `nth-child()`. Chris Coyier ([@chriscoyier](https://twitter.com/chriscoyier)) has a [great write-up about it](http://css-tricks.com/how-nth-child-works/) on _CSS Tricks_. 
*    **:before & :after combined with 'content':** I had no idea the CSS property `content` even existed. Again, Chris Coyier with [a good overview](http://css-tricks.com/css-content/). The bars in the nav and pips for lists use it. Blockquote also uses `content` but it uses the `open-quote` value. Note, if you use the `open-quote` value make sure `blockquote:after` is set to `content: no-close-quote` so that other `<blockquote>`s get the appropriate type of opening quote. 
*    **HTML5 Canvas:** One requirement that I gave myself was that the image on the right must randomly change when the site is being viewed in larger viewports. What better way to achieve this than `canvas`? After some false starts I ended up using `toDataURL()` and `background-image` (_[the JavaScript](https://github.com/dmolsen/dmolsen.com/blob/master/source/_includes/js/canvas_circles.html)_). If you look at the source for this page you'll see a lot of random gibberish in the `#canvas-container` `div`. That's that image.
*    **@-ms-viewport:** Last but not least is the use of the [@-ms-viewport](http://msdn.microsoft.com/en-us/library/ie/hh869615.aspx) rule for Windows RT. Tim Kadlec recently did a good write-up about issues with IE10 on Windows RT, _[IE10 Snap Mode and Responsive Design](http://timkadlec.com/2012/10/ie10-snap-mode-and-responsive-design/)_. I found it really useful for getting IE10 to properly register the viewport on device rotation. 

## Wrapping It Up

This article is primarily about the requirements that I set up for myself as I developed the new version of this site as well as some of the technical features I implemented. What's missing is anything that is really about responsive design. In a few days I'll have the follow-up, _Media Query-less Design, Content-based Breakpoints &amp; Tweakpoints_.