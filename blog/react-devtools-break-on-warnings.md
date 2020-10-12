<details>

```yaml
summary: 'React DevTools break on warnings feature'
updated: '2020/07/11'
```
</details>

# React DevTools break on warnings

FYI, if you use [React DevTools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en) and suddenly, for the past couple of days, you keep automatically (annoyingly!) hitting a breakpoint related to [break on warnings](https://stackoverflow.com/questions/62835806/react-dev-tools-deactivate-break-on-warnings) because, apparently, you enabled the _break on warnings_ feature in React DevTools (but you actually never enabled it, and it's actually unchecked), you need to check it, then uncheck it, so it stops bugging you! I'm guessing a recent update introduced a bug that has it on by default without checking the state of the settings. 💥

💬 [Create an issue to discuss!](https://github.com/stefcameron/website/issues/new?title=react-devtools-break-on-warnings&template=blog-post-discussion.md&labels=discussion)
