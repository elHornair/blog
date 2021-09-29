---
title: Creating a simple blog
title2: with Nuxt.js
publishedAt: 2021-09-27
---

This is just the summary of the article
<!--more-->

Now the full content of the article starts
Intro test

## Some subtitle

So, if you want to use Nuxt.js, you have to write a little bit of code:

```js[nuxt.config.js]
import slugify from '@sindresorhus/slugify';

hooks: {
  'content:file:beforeInsert': (document) => {
    document.slug = slugify(document.title)
  }
}
```

## Another subtitle

Even more text
