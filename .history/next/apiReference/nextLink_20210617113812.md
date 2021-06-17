# next/link

Client-side transitions between routes can be enabled via the Link component exported by next/link.

For an example, consider a pages directory with the following files:

```
- pages/index.js
- pages/about.js
- pages/blog/[slug].js
```
We can have a link to each of these pages like so:

## Example

```code
import Link from 'next/link'

function Home() {
  return (
    <ul>
      <li>
        <Link href="/">
          <a>Home</a>
        </Link>
      </li>
      <li>
        <Link href="/about">
          <a>About Us</a>
        </Link>
      </li>
      <li>
        <Link href="/blog/hello-world">
          <a>Blog Post</a>
        </Link>
      </li>
    </ul>
  )
}

export default Home
```

export default ActiveLink

Reference:

 LINK: https://nextjs.org/docs/api-reference/next/link
