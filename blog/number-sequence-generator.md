<details>

```yaml
summary: 'Generate a sequence of numbers in JavaScript'
updated: '2020/07/23'
```
</details>

# Generate a sequence of numbers in JavaScript

I just discovered a neat trick to generate a sequence of numbers in JavaScript:

```javascript
Array.from({ length: 3 }, (v, i) => i) // [0, 1, 2]
```

Nice and simple using the (new in ES6) [Array.from()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from) method with an array-like object of length N (no need for actual items) and the `from()` method's second parameter map function! 💥

💬 [Create an issue to discuss!](https://github.com/stefcameron/website/issues/new?title=number-sequence-generator&template=blog-post-discussion.md&labels=discussion)
