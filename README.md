# youtube-info-js
A simple js module, to parse some infos from a given Youtube video url.

## Overview
This is just a simple, tiny javascript module. You can use it in Node.js or in the browser, to:
- Validate some url, to make sure it is a valid Youtube video url.
- Extract the video id, from a given Youtube video url, by parsing the url.
- Fetch the video title, for a given Youtube video url, by fetching the title from web.
- Get the video thumbnail url, for a given Youtube video url, by parsing the url.

The module
- is written as an ECMA2015 module, using export and import
- is using promises with async/await
- make use of the node-fetch npm package (see https://www.npmjs.com/package/node-fetch)

## Motivation:
My intention, to write this module, was simply the fact, that nearly every npm package, for this job, failed for me.
- Either it failed, because of using the actual Google Youtube Api v3 and so you have to handle with API key.
- Or it failed, because it was massively outdated and a lot of security vulnerabilities popped up.
- Or it failed, because it has a million dependencies, no one needs.

## How to use:
Just copy the youtube.js file into your project and do some
```javascript
import Youtube from './youtube.js';
```
Now you can use the static functions 

const url = 'https://www.youtube.com/watch?v=123';

const valid = Youtube.validateUrl(url);
const id = Youtube.getVideoId(url);
const thumbnail = Youtube.getVideoThumbnailUrl(url);
const title = await Youtube.getVideoTitle(url);

console.log(valid);
console.log(id);
console.log(thumbnail);
console.log(title);

```
