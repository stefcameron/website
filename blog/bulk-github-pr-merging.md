<details>

```yaml
summary: 'Merging GitHub PRs in bulk'
updated: '2020/07/13'
```
</details>

# Bulk GitHub PR merging

I've been using [Dependabot](https://dependabot.com/) for nearly a year now on multiple repositories, public and private. It's the best thing since sliced bread, as they say! I highly recommend its services. BUT: It's a lot of work to merge all those PRs, especially if you have daily, or even weekly updates (I wouldn't recommend monthly since things change too fast and you'll get behind too quickly). 

GitHub still doesn't offer bulk PR management features in its web UI which would greatly help in this:
-   Multi-select PRs and approve them.
-   Multi-select PRs and merge them -- choosing whether to simply merge, or "squash and merge".

Dependabot, while it can auto-merge __once you approve__ one of its PRs, [will not support](https://github.com/dependabot/feedback/issues/949#issuecomment-640918321) auto-merging based on rules like "patches only" or "patches and minor updates" anytime soon, for security reasons.

In my case, while I used to review changes going into patch-level updates, I've now grown confident enough in our project's dependencies to just want to auto-approve anything that's a patch, as long as the build and tests passed in CI. Dependending on the project, I may not really care about minor updates either.

So I went looking and found that GOV.uk created a [bulk-merger](https://github.com/alphagov/bulk-merger) and shared it under MIT! 🎉 Unfortunately, the script hard-codes some of their org and user values, but I looked at the forks (only 4 at the time of writing this) and found 2 of them had additional useful commits:
-   [parameterized username and org/topic](https://github.com/deanwilson/bulk-merger/commit/d85b75563b1be5c59a74f7902fefec5339ac6c68)
-   [rebase instead of merge](https://github.com/dhlparcel/bulk-merger/commit/b1926b9bf169427d49435defc53e3449c5c10475)
-   [squash instead of rebase](https://github.com/dhlparcel/bulk-merger/commit/b414ba7527c3ee500cc38a875b9b7e890c1625c0) (an update to the previous one)

Since GOV.uk continues to update their `bulk-merger`, I'm going to fork from them directly, but I'll [cherry-pick those fork commits](https://stackoverflow.com/a/5120074/6465363) into my own fork so I can control when I pull from upstream.

💬 [Create an issue to discuss!](https://github.com/stefcameron/website/issues/new?title=bulk-github-pr-merging&template=blog-post-discussion.md&labels=discussion)
