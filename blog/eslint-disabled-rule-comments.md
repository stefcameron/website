# ESLint disabled rule comments

<details>

```yaml
summary: 'Add comments to disabled ESLint rule directives'
updated: '2020/05/14'
```
</details>

_Finally_, with __ESLint 7.0.0__ (released early May 2020), it's now possible to [annotate a directive with a comment](https://eslint.org/docs/user-guide/migrating-to-7.0.0#descriptions-in-directive-comments) (the RFC explains it better)! This means that instead of doing this to explain why you're disabling a rule that would otherwise be enabled and cause a lint error:

```javascript
// trust me, I know what I'm doing!
if (foo == bar) { // eslint-disable-line eqeqeq
```

you can now do this (which makes it a lot more clear, especially if Prettier relocates your comments even more, what you're referring to with "trust me..."):

```javascript
if (foo == bar) { // eslint-disable-line eqeqeq -- trust me, I know what I'm doing!
```

By now, I'm sure you all know I'm a big proponent of clarity in code. This is a welcome addition for me! I'm upgrading projects to ESLint 7. You should too!

💬 [Create an issue to discuss!](https://github.com/stefcameron/website/issues/new?title=eslint-disabled-rule-comments&template=blog-post-discussion.md&labels=discussion)
