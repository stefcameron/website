# Why use the React Testing Library

<details>

```yaml
summary: 'Why should you use the React Testing Library?'
updated: '2020/06/01'
```
</details>

[Kent C Dodds](https://kentcdodds.com), the author of the [React Testing Library](https://testing-library.com/docs/react-testing-library/intro), recently [blogged](https://kentcdodds.com/blog/common-mistakes-with-react-testing-library) an awesome "how to" and "how not to" article on properly using the React Testing Library. It highlights why we're using it in our Design System Library: Because it forces us to test right in the DOM, the closest we can get to what the user will interact with when they use our components.

And thanks to this article, we will be able to fix a few things in our tests to make them even better! There are some things we (myself included!) need to do better, like making better use of [jest-dom](https://www.npmjs.com/package/@testing-library/jest-dom) queries at our disposal, leveraging some new [eslint](https://github.com/testing-library/eslint-plugin-testing-library) [plugins](https://github.com/testing-library/eslint-plugin-jest-dom), and using their new [user event library](https://github.com/testing-library/user-event) instead of `fireEvent()`.

💬 [Create an issue to discuss!](https://github.com/stefcameron/website/issues/new?title=why-use-react-testing-library&template=blog-post-discussion.md&labels=discussion)
