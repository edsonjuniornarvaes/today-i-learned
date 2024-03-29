# next/router

## useRouter

If you want to access the router object inside any function component in your app, you can use the useRouter hook, take a look at the following example:

## Example

```code
import { useRouter } from 'next/router'

function ActiveLink({ children, href }) {
  const router = useRouter()
  const style = {
    marginRight: 10,
    color: router.asPath === href ? 'red' : 'black',
  }

  const handleClick = (e) => {
    e.preventDefault()
    router.push(href)
  }

  return (
    <a href={href} onClick={handleClick} style={style}>
      {children}
    </a>
  )
}
```

export default ActiveLink

Reference:

 LINK: https://nextjs.org/docs/api-reference/next/router
