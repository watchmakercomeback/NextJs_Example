# NextJs_Example
My Notes when i was studying and learning Next

#What is it?

Next.js is a popular framework built on top of React that allows you to build React applications with server-side rendering (SSR) and several other features aimed at simplifying the development of production-ready React applications.

Here are some key aspects and features of Next.js:

Server-Side Rendering (SSR): One of the main advantages of Next.js is its built-in support for server-side rendering. This means that pages are rendered on the server before being sent to the client's browser, which can improve performance and SEO.

File-Based Routing: Next.js uses a file-based routing system. This means that each React component you create in the pages directory automatically becomes a route in your application. For example, a pages/about.js file will create a route for /about.

Automatic Code Splitting: Next.js automatically code-splits your application. Only the necessary JavaScript (and CSS) for each page is loaded, optimizing performance by reducing the initial download size.

API Routes: Next.js allows you to easily create API routes alongside your pages. These routes can be used to handle server-side logic and data fetching, providing a backend API within your Next.js application.

Static Site Generation (SSG): In addition to SSR, Next.js supports static site generation where HTML pages can be pre-rendered at build time. This is useful for content that does not change often and can lead to even better performance.

TypeScript Support: Next.js has excellent support for TypeScript out of the box. You can create a Next.js project with TypeScript by simply adding a tsconfig.json file.

CSS and Sass Support: Next.js supports importing CSS and Sass files directly into your components, providing seamless integration with popular styling solutions.

Image Optimization: Next.js optimizes images on the fly by automatically resizing, optimizing, and serving them in modern formats.
Environment Variables: Next.js allows you to easily configure environment variables for your application using .env files.

Authentication: Next.js can be integrated with authentication providers such as Auth0 or Firebase, allowing you to build secure applications with ease.

#Create Project
`npx create-next-app@latest`
`yarn create next-app`
`pnpm create next-app`
`bun create next-app`

#Fetch Example Server Components
###getStaticsProps
--> 
```
const fetchThing = () => {
  return fetch('https://jsonfetch.com/api').then(res => res.json())
}

export default asyn function asynComponentEx ({ params }){
  const posts = await fetchThing()
return(
<section>
{map your stuff or something}
</section>
)
}
```
###getServerSideProps
-->
```
return fetch('https://jsonfetch.com/api', { cache: 'no-store' }).then(res => res.json())
```
#Client component
```
'use Client'
import { useState } from 'react'

export function Component({ params }){
  return(<></>)
}
```

#Layouts
they are high order components, that wrap whats inner page in the actual folder and nested forlders, can be usefull to store some states
using parenthesis in folder name to make groups and don't nest routes but share things like layout.

#Use
festures for fonts and images 
`npm install @next/font -E`
```import { fontType } from '@next/font/google'
const font = fontType({
  weight: ['400', '700'],
  subsets: ['latin']
})
```

```
import Image from 'next/image'

<Image width='' height='' src={'https://mylink.com'}>
```
in next.config be sure to allow images sources
`images: { domains: ['https://mylink.com'] }`
