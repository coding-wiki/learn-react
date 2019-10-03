# React time hooks

## `setInterval` hook

> https://overreacted.io/making-setinterval-declarative-with-react-hooks/  
> (written by Dan Abramov, React developer)

### Example

```js
  const [interval, setInterval] = useState(500);

  let count = 0;
  useInterval(() => {
    setInterval(interval * count);

    count += 1;
  }, interval);
```
