# Offline first

by Rowdy Rabouw

## Official Slides

[Slides](https://github.com/nfrankel/confoo-2024/blob/main/2024-02-21/offline_first_rowdy_rabouw.pdf)

## Service Worker

- run in the background -> non blocking (javascript single threaded but sw brings new opportunity)
- scoped to a website
- can't modify the page; can't access to the DOM

sw is between the browser and the server

## Static Cache

vs

## Dynamic cache

- caches as long as the user fetches some pages
- if we fetch something from the server, we put it inside the dynamic cache

Cool but the user has to visit the page before we can cache it, so lets get into prefetch

`<link ref="prefetch" />`

- programmatically add them with a javascript function that look at all the links
- but not supported ios

- add data-\* to the links that we want to prefetch instead of querySelectorAll('a') because it good be external links etc...

  - could be data-skip-prefetch or data-prefetch

- better: use IntersectionObserverAPI, and fetch the resource and put it inside the service worker fetch (we can ensure not to refetch by adding a list of fetched links inside the local storage)

- but if the user is in a low connection, it might not be the good solution to do, so:
  NetworkInformation.effectiveType (NetworkInformation API badly support), NetworkInformation.saveData (only supported on android)

## Optimised Offline

sw.js file

```
let setDynamicVersionInLocalStorage = true;

if (setDynamicVersionInLocalStorage) {
 // postMessage to the client
}
```

client.js

```
// Inside addEventListener('message')
if (event.data.action === "setDynamicVersionInLocalStorage") {
    // put inside a localStorage
}
```

- then we create a cache with those links
