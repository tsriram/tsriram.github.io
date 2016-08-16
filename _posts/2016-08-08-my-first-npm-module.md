---
layout: post
title:  My first npm module!
date:   2016-08-08 15:13:00 +0530
categories: nodejs
---
Of late, I have been dabbling around with APIs from [data.gov.in](https://data.gov.in) to see if I can build any useful app with them for the use of public. While there are APIs to access data, the site also lets users export data in various formats like XML, CSV, JSON etc. 

I wanted to build a client side app which can just be added to any web page. But the API requires to send my API key, which is not a secure way to do from a client side app. Also, since many of the datasets are kind of static and not going to be updated (like PIN codes), I thought it might be easier just to export a dataset and use it in the app from a static file.

But the exported JSON, to my surprise, is in a format which is not readily usable. For example, it is in this format:

{% highlight json %}
{
  "fields": [
    {
      "id": 1,
      "label": "city"
    },
    {
      "id": 2,
      "label": "state"
    }
  ],
  "data": [
    [
      "Chennai",
      "Tamilnadu"
    ],
    [
      "Mumbai",
      "Maharashtra"
    ]
  ]
}
{% endhighlight %}

But what I wanted is like this:

{% highlight json %}
[
  {
    "city": "Chennai",
    "state": "Tamilnadu"
  },
  {
    "city": "Mumbai",
    "state": "Maharashtra"
  }
]
{% endhighlight %}

Though it is very simple to transform the former to the latter format, I could not find any readymade solution for this. So I wrote it myself and fullfilled my long due wish of publishing an npm module. You can find it here - [https://www.npmjs.com/package/field-data-array-to-json](https://www.npmjs.com/package/field-data-array-to-json)

Of course, it is in its simplest form and there's a lot to improve. I am quite not sure if it'll be useful for anyone but surprised to see it's been downloaded 73 times at the time of this writing. Now the real task is to write some app to put this data to use.

