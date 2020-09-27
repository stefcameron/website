# Webpack Terser tree shaking

<details>

```yaml
summary: 'Tree shaking with Webpack and the Terser plugin'
updated: '2020/06/17'
```
</details>

Why is Webpack not tree-shaking `pickOwnProps()` out of `coreUtil`?

It's OK that both `omit()` and `pick()` (also in `coreUtil`) are in the resulting bundle because `chooseOwnProps()` can't know which one it will need until runtime, but `pickOwnProps()` is never called by anything in the bundle code...

I looked at https://webpack.js.org/guides/tree-shaking/ and https://webpack.js.org/configuration/optimization/ options, and they were already set the right way!

Finally, I was able to verify that Webpack's [Terser plugin](https://webpack.js.org/plugins/terser-webpack-plugin/) is also doing some optimization (likely when `minify: true`) and removing dead code from the Prod build, even though there's still some dead code in the Dev build, which is of less concern.

So Webpack does some tree shaking, and then Terser runs and does some final pruning to get rid of the loose branches that got stuck in other branches after they were cut. 🙂

💬 [Create an issue to discuss!](https://github.com/stefcameron/website/issues/new?title=webpack-terser-tree-shaking&template=blog-post-discussion.md&labels=discussion)
