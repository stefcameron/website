# Jest toBeDefined expectation

<details>

```yaml
summary: 'How to properly use the toBeDefined() expectation in Jest'
updated: '2020/06/12'
```
</details>

I just realized something very important: In Jest, `toBeDefined()` should be used explicitly to check if a value is _not undefined_ (`value !== undefined`). It should not be used to check if a value is anything other than `undefined`. If `null` is also bad for you, then you might be better served by `toBeTruthy()`, which will blow-up 💥 if the expectation results in `undefined` or `null` (or empty string, or zero, or `false`).

So far, I've been incorrectly using `toBeDefined()` to make sure that DOM queries with `querySelector()` are working, which is bad because `document.querySelector()` will return `null`, not `undefined`, if the node isn't found, and `toBeDefined()` is happy with `null`... For this type of test, use `toBeInTheDocument()` (which probably tests for "not `null`" behind the scenes).

💬 [Create an issue to discuss!](https://github.com/stefcameron/website/issues/new?title=jest-to-be-defined-expectation&template=blog-post-discussion.md&labels=discussion)
