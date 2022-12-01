# useRef as Mutable Reference
**Topics:** [[React]]
**Related:** [[202209062156 - useRef as DOM API Reference]]

useRef creates a mutable reference that *lasts for the lifetime of a component instance.* Useful for keeping track of data in a way that doesn't trigger re-renders, like with intervals:

```JSX
const intervalRef = useRef();

useEffect(() => {
	intervalRef.current = set Interval(() => setCount(count => count++), 1000);
	return () => clearInterval(intervalRef.current);
}, []);

return <button onClick={() => clearInterval(intervalRef.current)} />
```


## References
---
1. [[202209062015 - BLOG - useRef]]
