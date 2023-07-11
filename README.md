# Media_Not_function

## CSS 에 Media 형식으로 반응형이 구현되어 있는데 인식하지 않을 때 해결했던 방법

```ts

export default function useWindowDimensions() {
    const [windowDimensions, setWindowDimensions] = useState(getWindowDimensions());

    useEffect(() => {
        function handleResize() {
            setWindowDimensions(getWindowDimensions());
        }

        window.addEventListener('resize', handleResize);
        return () => window.removeEventListener('resize', handleResize);
    }, []);

    return windowDimensions;
}
```

```ts
  <div className="paging_box" style={ width < 1155 ? {display: "none"} : {}}>
```
