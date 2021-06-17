# next/head

We expose a built-in component for appending elements to the head of the page:

## Example

```code
import Head from 'next/head'

function IndexPage() {
  return (
    <div>
      <Head>
        <title>My page title</title>
        <meta name="viewport" content="initial-scale=1.0, width=device-width" />
      </Head>
      <p>Hello world!</p>
    </div>
  )
}

export default IndexPage
```

export default ActiveLink

Reference:

 LINK: https://nextjs.org/docs/api-reference/next/head
