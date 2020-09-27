# Jest run in-band

<details>

```yaml
summary: 'Run jest in-band when testing a Hapi server'
updated: '2020/04/09'
```
</details>

Running into random test failures with [jest](https://jestjs.io/) while testing a [HapiJS](https://hapi.dev/) [NodeJS](https://nodejs.org/) server because of `EADDRINUSE` errors?

Jest's `--runInBand` CLI option is your friend!

Jest runs tests in parallel by default, so without this setting, you will get many server starts without stops, causing address conflicts. 💥

💬 [Create an issue to discuss!](https://github.com/stefcameron/website/issues/new?title=jest-run-in-band&template=blog-post-discussion.md&labels=discussion)
