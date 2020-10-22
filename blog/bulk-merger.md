<details>

```yaml
summary: 'Scripts to manage bulk PR merging from the command line'
updated: '2020/09/28'
```
</details>

# Bulk-merging GitHub PRs from the command line

I was getting [tired](./bulk-github-pr-merging.md) of manually approving tons of [Dependabot](https://dependabot.com/) PRs -- especially for patch updates which, for our project's dependencies, I've come to know are 99% safe and don't need to be eyeballed every single time. GitHub Web, however, doesn't have any bulk operations on open PRs: Can't bulk-approve, can't bulk-merge.

I went looking on Google and found that [Gov.uk](https://github.com/alphagov) (who has an OSS design system of their own!) has a [bulk-merger](https://github.com/alphagov/bulk-merger) repo for this very purpose!

One [fork](https://github.com/stefcameron/bulk-merger) and [commit](https://github.com/stefcameron/bulk-merger/commit/f5334dc119661ae00a219dc4608f293da06a02f2) later (well, I also merged 3 other small commits from 2 other forks too, but that was the main one) and voila! bulk-merging from the command line for any repo in any org with any query and any topic. 💪

With branch protection in place (which all our GH repos have), the script will fail gracefully if a PR didn't pass tests.

Dependabot is very smart too: If it can't merge the PR on its own because of merge conflicts (which happens often in the lock files), it will automatically rebase the PR, and (most of the time) merge it on its own (since it was approved), though sometimes you may still have to manually merge it (not sure what makes the difference there).

## Update 2020/09/28

Dependabot 2.0](https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/about-github-dependabot-version-updates) (what I call the rebooted version that's now natively integrated into GitHub post-acquisition) no longer supports auto-merging [under any circumstances](https://github.com/dependabot/dependabot-core/issues/1973#issuecomment-640918321). So a script is _definitely_ in order.

Unfortunately, my `bulk-merger` often gets API rate-limited, but thankfully, it's sometimes possible to use the new [GitHub CLI](https://cli.github.com/) to accomplish similar things:

```bash
$ gh pr list -R focus-trap/tabbable
$ for id in 1 2 3 4 5; do gh pr merge $id -s -R focus-trap/tabbable; sleep 5; done
```

> The `-R ORG/REPO` option is not needed if you're in the git dir itself. `sleep 5` (or at least _some_ pause) is needed between merges in order to give GitHub a chance to figure out if any outstanding PRs have merge conflicts as a result of this merge. `-s` does a "squash & merge".

💬 [Create an issue to discuss!](https://github.com/stefcameron/website/issues/new?title=bulk-merger&template=blog-post-discussion.md&labels=discussion)
