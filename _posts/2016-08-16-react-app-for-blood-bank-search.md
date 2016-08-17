---
layout: post
title:  React app to search blood banks in India
date:   2016-08-16 21:00:00 +0530
categories: react
summary: A simple React app built on Flux architecture to search for blood banks in India.
---
I have been playing around with data & APIs from [data.gov.in](https://data.gov.in){:target="_blank"} for a while now to see if I can build some useful app in my free time. One dataset that I particularly liked is blood banks in India. Well, there are already a few sites that let you search for a blood bank using city name, pin code etc.

I wanted create this app to implement what I have learnt in React / Flux / Alt.js. Though I have been using these in a couple of projects at work, I wanted to do some app from scratch. This is not really a complex app - it just has a text box which takes city / pin code as input and lists all blood banks that match the query.

If you just want to check out the app, here you go (It's not fancy, you've been warned):

[Blood Banks Search - India](/apps/bloodbanks/){:target="_blank"}

Read on for more details.

App is built using React with Flux architecture. I have used [Alt.js](http://alt.js.org/){:target="_blank"} to manage the state of the app. I use [Webpack](http://webpack.github.io/){:target="_blank"} for bundling JS & SCSS/CSS (yet to write a dev config for webpack though!).

I am using static data from [here](https://data.gov.in/node/356981/datastore/export/json){:target="_blank"}. Since I wanted the data to be transformed to a more usable format, I wrote a small utility module. Also published [it on npm](https://www.npmjs.com/package/field-data-array-to-json){:target="_blank"}. I also wrote [another npm module](https://www.npmjs.com/package/index-json){:target="_blank"} to index JSON which makes it convenient to filter data. They are not super useful modules, but helped me learn how to publish a module to npm, how to use [Travis CI](https://travis-ci.org/){:target="_blank"} for testing builds and [coveralls](https://coveralls.io/){:target="_blank"} to check test coverage. Test cases are written using [Mocha](https://mochajs.org/){:target="_blank"} and [Chai](http://chaijs.com/){:target="_blank"}. You can find the code on Github - [https://github.com/tsriram/blood-banks-list](https://github.com/tsriram/blood-banks-list){:target="_blank"}

All assets (JS/CSS/JSON) are served through [rawgit](https://rawgit.com/){:target="_blank"} (Thanks to those good folks!)

Please check out the app and share your comment / feedback :)
