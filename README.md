# style

We have a standard format for commits to keep things tidy, just follow the following rules and you'll be fine:

1. If files you will be changing aren't formatted by our `.prettierrc.json` standards, format all files and create a commit for formatting all files, which should look like this: `🧹 All: Format Files`
2. Commits should serve one clear purpose, e.g: add one feature
3. Commit titles should start with an emoji, then a category, and then a clear, brief message, so for example: `⚙ Swamp: Add Settings Page`
4. Commits should have a longer body explaning the commit:
   ```
   ⚙ Swamp: Add Settings Page

   This commit adds a settings page in swamp.settings, using our swarm.ui.settings
   system.

   This is a work-in-progress and needs more options.
   ```
5. If your commit does not follow these rules, use `git rebase -i HEAD~1` to rewrite the timeline. Change the number after the tilda to rewrite multiple commits.

## Merging

Always create a branch for your overarching project, such as `settings-page`, where you can have multiple commits working towards your goal.
Do not merge this via `rebase`, but instead via a [pull request](https://github.com/swarm-team/style/pulls)

## Using Command Line Tools

If you feel unsure of the magic spells you need to cast to make git work read below.

To start adding a feature create a branch for that feature so you can make a PR later.
```bash
git checkout -b settings-page # Create branch locally
git push origin settings-page # Create branch on remote
git push --set-upstream origin # Link the two branches
```

Then you can make your changes.
```bash
git commit \
-m "⚙ Swamp: Add Settings Page" \
-m "This commit adds a settings page in swamp.settings, using our swarm.ui.settings system." \
-m "This is a work-in-progress and needs more options."
git push
```

And if you have the Github CLI you can make a PR quickly.
```bash
gh pr create
```