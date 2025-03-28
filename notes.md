A memo function is a wrapper around a component, which looks if the props of the component function are different; then the component will be rerendered.

Don't overuse memo()!
- Use it as high up in the component tree as possible 
    > blocking a component execution there will also block all child component executions.

- Checking props with memo() costs performance!
    > don't wrap it arount all your components - it will just add a lot of unnecessary checks

- Don't use it on components where props will change frequently
    > memo() would just perform a meaningless check in such cases (which costs performance)


useMemo can be wrapped around normal functions (with a complex calculation), to prevent the function will be executed again if the prop is not rerendered.

With an empty dependencies array the function will never be executed again.

Note that memo can be used for component functions and useMemo for normal functions.

MILLION.JS
Consider using million.js to improve performance of your react app.