# Renaming the default branch from `master`

Many communities, both on GitHub and in the wider Git community, are considering renaming the default branch name of their repository from `master`. GitHub is gradually renaming the default branch of all our repositories from `master` to `main`. We're committed to making the renaming process as seamless as possible for project maintainers and all of their contributors. This repository is our up-to-date guidance on how and when to rename your default branch.

We're not the only organization in the Git ecosystem making these changes: there are upcoming changes in the Git project ([statement](https://sfconservancy.org/news/2020/jun/23/gitbranchname/), [code change](https://lore.kernel.org/git/pull.656.v4.git.1593009996.gitgitgadget@gmail.com/)), as well as coordinated changes from multiple vendors.

## What we're changing :pencil2:

We’re making changes to GitHub in a few phases, designed to cause as little disruption to existing projects as possible.

### Now: supporting early movers 🚚

Some projects on GitHub have already renamed their default branch. As a result, any links to those projects that contained the old branch name would previously have been broken. 

So, our first change, shipped on [July 17th](https://github.blog/changelog/2020-07-17-links-to-deleted-branches-now-redirect-to-the-default-branch/), updates GitHub.com to redirect links that contain a deleted branch name to the corresponding link in the repository's default branch.

This change supports projects that have already moved. **If you haven’t moved yet, we recommend not moving right now, and waiting until [later this year](#later-this-year). We’re investing in tools to make the renaming the default branch of an existing repository a seamless experience for both maintainers and contributors.**

### This summer: a configurable default for new repositories 🆕

Our next step helps users and organization admins that want to ensure all new repositories they create use the default branch name of their choice.

To enable that choice, later this summer we’re adding new user and organization settings to set the default branch name for all newly-created repositories on GitHub.com. These settings will cover all the ways you can create a GitHub repository, including through: [GitHub.com](https://github.com/new), the [GitHub API](https://developer.github.com/v3/guides/getting-started/#create-a-repository), [GitHub Desktop](https://desktop.github.com/), and [GitHub CLI](https://cli.github.com/). If you’re a GitHub Enterprise Server user, we’re also planning to add organization and instance settings to set the default branch name for all newly-created repositories on a GitHub Enterprise Server in version 2.22.

#### From `master` to `main`

`main` is the most popular replacement for `master` that we’re seeing across GitHub. We like it because it’s short, it keeps your muscle memory intact, and it translates well across most languages. We’re using `main` for our newly-created repositories and for the repositories we’re moving now, like [dependabot-core](https://github.com/dependabot/dependabot-core).

One month after the new settings are available in GitHub.com, we will set the default to `main` for any user or organization that hasn't chosen a default branch for new repositories. We'll do the same in GitHub Enterprise Server 2.23. You can opt out of this at any time by configuring the default branch name for new repositories to `master` or any other word.

<a name="later-this-year"></a>

### Later this year: seamless move for existing repositories 🚀

For existing repositories, renaming the default branch today causes a set of challenges:

- Open pull requests need to be retargeted to the new branch
- Draft releases need to be retargeted to the new branch
- Branch protection policies need to be transferred to the new branch
- GitHub Pages expects content in the `master` or `gh-pages` branch

By the end of the year, we'll make it seamless for existing repositories to rename their default branch. When you rename the branch, we’ll retarget your open PRs and draft releases, move your branch protection policies, and more - all automatically. We’re updating GitHub Pages to allow building from any branch. And, we’re also looking into redirecting users who `git fetch` or `git clone` the old branch name to the new branch name (with a warning and instructions to update their local clone), so it’s easy for your contributors to move. You’ll be able to do a rename from GitHub.com, GitHub Desktop, or the CLI.
