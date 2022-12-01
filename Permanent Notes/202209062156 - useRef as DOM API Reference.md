# useRef as DOM API Reference

**Topics:** [[React]]

**Related:** [[202209062206 - useRef as Mutable Reference]]

useRef creates a reference object to a DOM element easily accessed through a component in the "current" property of that object.

Example that focuses on an input :

```JSX

function App(){

	const inputReference = useRef(null);
	useEffect(() => {
		inputReference.current.focus();
	}, []);

	return (
		<input ref={inputReference} />
	);

}
```

## References
---
1. [[202209062015 - BLOG - useRef]]