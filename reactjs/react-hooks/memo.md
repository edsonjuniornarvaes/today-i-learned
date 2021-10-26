# memo

If your component renders the same result given the same props, you can wrap it in a call to React.memo for a performance boost in some cases by memoizing the result. This means that React will skip rendering the component, and reuse the last rendered result.

## Example

```code
const MyComponent = React.memo(function MyComponent(props) {
  /* render using props */
});
```

Reference:

LINK: https://reactjs.org/docs/react-api.html#reactmemo
