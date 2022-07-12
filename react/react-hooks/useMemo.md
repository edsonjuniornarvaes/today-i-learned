# useMemo

Pass a “create” function and an array of dependencies. useMemo will only recompute the memoized value when one of the dependencies has changed. This optimization helps to avoid expensive calculations on every render.

## Example

```code
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

Reference:

LINK: https://reactjs.org/docs/hooks-reference.html#usememo
