---
layout: project.njk

thumbnail: /img/sample/brews-bites-tile.jpg
description_short: a web-based cooking app
description_medium: app design, web development
eleventyNavigation:
  key: Case Study
  parent: Pocket Kitchen
  order: 0
---

# pocket kitchen

## app design process

## by Kristoff Lalicki

## Concept Development

### The Reason

There is a growing disconnect between young people and cooking. Traditional printed cookbooks can be difficult to follow, especially for someone without a strong foundation of skills and knowledge. Even digital cooking resources are often ineffective for young cooks. Many existing cooking sites focus on a curated selection of high-end dishes, rather than everyday meals, while other resources offer more practical recipes, but in an overwhelming and unorganized manner.

### The Project

I proposed creating a cooking app that would help young people learn to cook. By combining visual aids with simple and healthy recipes, I hope to make it easier for people to become more comfortable cooking.

## Content

### Recipe Collection

To gather content for this project, I looked through cookbooks and websites, and put together a list of recipes that represent a broad range of meals, while only using easy-to-find and inexpensive ingredients, and without elaborate cooking processes. I tested each recipe, recorded changes as necessary, and re-tested to ensure that users would be able to produce consistently good results.

### Video Production

I set up a semi-permanent filming rig in my living room to capture video for this project. All of the video footage for the project was captured on a cell phone, as it was the only device I have access to that can film in 4k resolution.

All of the videos for the project were broken into individual steps, then edited to fit within a 5 to 15 second time constraint. I chose to use the MPEG4/H264 format for the final output, as it is efficient, allows for high quality, and supported is by the majority of mobile browsers and devices.

# Design

### Analog Wireframing

I roughly sketched out ways I could present recipes on a phone screen. I want to emphasize the video/image elements, so they are currently occupying much of the display space.

![](img/manual-wireframes.jpg)

### Preliminary Digital Wireframing & Testing

I made some preliminary digital wireframes, and conducted initial user testing, both by myself and with an additional user, in the environment of a kitchen. I found that even oversized UI elements were difficult to interact with while cooking, especially while one’s hands were dirty. To address this, I proposed that the main interaction within the cooking interface would be through swipe-based gestures: left & right to move between steps, up or down to access the menu.

![](img/prelim-wireframes.jpg)

### Digital Wireframing

I created about 30 higher-fidelity digital wireframes, to experiment with different visual styles. I began to look at how color and space would be used in the app, and the different ways in which I could organize and separate the parts of the screen (lines, cards, etc.).

![](img/hifi-wireframes.jpg)

### Expanded Wireframing

I chose one wireframe to develop further, and created wireframes for the different types of pages in the app using that style. At this point, I began to develop a consistent pattern for colors, spacing, and typography.

![](img/hi-fi-2.jpg)

### Designing the Timer

One important part of this app is its integrated timer. I experimented with several layouts for the timer page, finally deciding on a round timer (similar to the Google Clock app that is bundled with many phones running stock Android.)

![](img/timers.jpg)

### Branding

After creating a list of about 30 potential names for the project, I looked through the list to see which ones were still available as domain names. I found the ".kitchen" TLD, which is still largely unoccupied, and chose to name the project **pocket kitchen**.

I first experimented with illustration in the logo, combining a chef's hat with a "play" icon. I paired this illustration with the project's URL in the same typeface used in the app ( [Fibra One](https://www.myfonts.com/fonts/los-andes/fibra-one/)).

I ultimately decided to move away from illustration, as the app's UI design does not use any illustrated elements. I chose a high-contrast serif typeface ( [Gastromond](https://www.myfonts.com/fonts/james-todd/gastromond/)), and removed the period from the name.

![](img/brand-explor-01.jpg)

# Development

### Development Begins

I began developing the app, initially using static filler content. I decided to build the layout using Flexbox, to allow it to adapt to various device sizes and amounts of content.

### The Search for the perfect JS Touch Scroller

One of the most important interactive elements in this project is the use of gestures to move between screens. I wanted this interaction to feel as close to a native app experience as possible. I tested a lot of different JavaScript scroll libraries, including [iscroll.js](https://github.com/cubiq/iscroll) and [jQuery touchSwipe.](https://github.com/mattbryson/TouchSwipe-Jquery-Plugin) I ended up using [Swiper,](http://idangero.us/swiper/) a very flexible scroll plugin that was designed for mobile devices, which also offered smooth and natural-feeling motion.

### Custom CMS

I experimented with several CMS systems, including Wordpress and Kirby. None of these had the degree of structure that I needed for my content, so I had to build my own CMS from scratch.

I created a client-side script that allows the app to dynamically load content in when the page loads, separating the content from the design & development of the app. At page load, the script loads a JSON file (which will eventually be specified via a query string), then parses the file and uses it to build up DOM elements on the page. Once the DOM is fully built, the script initializes the app’s interactivity.

While creating a template for the project's JSON files, I chose to add separate fields for quantities and units. In a future release, this will allow the app to recalculate quantities to make larger or smaller recipe sizes.

![](img/ajax-demo-01.jpg)

### Amazon S3

After I deployed a copy of the site to my server for testing, I found that the load time for the videos was very inconsistent, and often made the app hard to use. To fix this, I moved the high-bandwidth content (image and video) to an Amazon S3 bucket, which should have much higher performance than my server, in addition to being scalable.

### Lazy \[un-\]Loader

I found that many mobile devices were unable to reliably load all of the videos (approximately 20 MB) into memory at once. To overcome this, I built a lazy-loader/unloader that only keeps 3 videos in memory at any given time: the current video, the previous video, and the next video. Although it is possible to swipe through the app faster than the videos can load, this does not seem to present any issues in actual use of the app.

## The Outcome

### Ready for Launch!

On May 2, I officially launched the app at [www.pocket.kitchen](http://pocket.kitchen/app) and quickly ironed out a few bugs involving relative paths that weren't linked properly.

### Thesis Show

On May 4, I presented the project at our BFA thesis show. Despite technological difficulties the day of the show (lack of wifi in the show building), the event went smoothly.

![](img/showtable.jpg)

### Post-Show

During the show and the week following, I received a lot of positive feedback about the project. Everyone seemed to find the format of the app to be easy-to-follow.

## What's Next

### A Living Project

I intend to keep developing this project further. From the feedback I've received so far, the app could actually make a difference in many people's lives.

### More User Testing

While I did conduct user testing on low-fidelity wireframes of the app, I have not conducted formal user testing on the final high-fidelity interface. I plan to do so, and use this feedback to refine the app's user experience.

### A Wish List

While working on this project, I began to create an ongoing list of features or other concepts to explore, that I plan to incorporate in future releases.

- More content
- Ability to save progress in recipe
- Native version of app
- Recipe quantity modifiers
- Contextual information (tap on a word in the recipe to bring up a brief article about it)

## The End (for now)

### Thanks!

Thanks to professors Dimitry Tetin, Amy Papaelias, and Anne Galperin for their feedback and support, and thanks to all my friends (especially [Alex,](http://www.alexdmandel.com) [Rachel,](http://rachelstern.myportfolio.com) and [Tara](http://www.taradunaier.com)) for their love and support.
