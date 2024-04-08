# React Server Components

by Sébastien Castiel

## Key dates

2013 - React
2015 - Server-Side Rendering
2017 - NextJs
2022 - React Server Components

## Client components

Interactivity - Browser APIs - Calling APIs - Forms

## Server Components

call database - internal APIs - Async

NextJS now by default uses server components (the only framework that does it)
Server Components have access to apis on the server (apiKey)

Instead of fetch inside useEffect, we only can create a react async component (only because its a server component)

```
export default async function Movies () {
    const movies = await fecthMovies();

    return {
        movies.map ...
    }
}
```

- No local state, no useEffect, no loading
- HTML returned by the server

But if we have a delay or a long request, we even need a loading state, so how to do that ?

- using Suspense, Suspense will wrap the async server component that fetches movies

### Server Action

async function that call a database for example

## When to use Clients vs Server components

- Client: PWA - Offline-first - Mobile
- Server: E-commerce - Blog - Content
  - Drawback -> need a framework (NextJs)

## Refs

Article - [RSC from Scratch](https://github.com/reactwg/server-components/discussions/5) by Dan Abramov
