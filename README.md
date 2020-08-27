# Renaming the default branch from `master`

Many communities, both on GitHub and in the wider Git community, are considering renaming the default branch name of their repository from `master`. GitHub is gradually renaming the default branch of our own repositories from `master` to `main`. We're committed to making the renaming process as seamless as possible for project maintainers and all of their contributors. This repository is our up-to-date guidance on how and when to rename your default branch.

We're not the only organization in the Git ecosystem making these changes: there are upcoming changes in the Git project ([statement](https://sfconservancy.org/news/2020/jun/23/gitbranchname/), [code change](https://lore.kernel.org/git/pull.656.v4.git.1593009996.gitgitgadget@gmail.com/)), as well as coordinated changes from multiple vendors.

## What we're changing :pencil2:

We’re making changes to GitHub in a few phases, designed to cause as little disruption to existing projects as possible.

### Now: supporting early movers 🚚

Some projects on GitHub have already renamed their default branch. As a result, any links to those projects that contained the old branch name would previously have been broken.

So, our first change, shipped on [July 17th](https://github.blog/changelog/2020-07-17-links-to-deleted-branches-now-redirect-to-the-default-branch/), updates GitHub.com to redirect links that contain a deleted branch name to the corresponding link in the repository's default branch.

This change supports projects that have already moved. **If you haven’t moved yet, we recommend not moving right now, and waiting until [later this year](#later-this-year). We’re investing in tools to make the renaming the default branch of an existing repository a seamless experience for both maintainers and contributors.**

### Now: GitHub Pages from any branch 📰

Until recently, GitHub Pages required that you use either the `master` or the `gh-pages` branch. As of [July 31](https://github.blog/changelog/2020-07-31-build-and-deploy-github-pages-from-any-branch-beta/), repositories that use GitHub Pages can now build and deploy from any branch. Publishing to the special `gh-pages` branch will still work the same as it always has, but now you can choose a different branch in your repository as the publishing source.

### Now: a configurable default for new repositories 🆕

We've heard from users, organization owners, and enterprise administrators that want to ensure all new repositories they create use the default branch name of their choice.

To enable that choice, on [August 26th](https://github.blog/changelog/2020-08-26-set-the-default-branch-for-newly-created-repositories/) we added new user, organization, and enterprise settings to set the default branch name for all newly-created repositories on GitHub.com. These settings cover repositories created through [GitHub.com](https://github.com/new) and the [GitHub API](https://developer.github.com/v3/guides/getting-started/#create-a-repository). If you’re a GitHub Enterprise Server user, these same settings are coming in version 2.23.

Git 2.28 added a similar setting to control the default branch used when you run `git init` on the command line. Learn more about the new `init.defaultBranch` setting in [the Git 2.28 blog post](https://github.blog/2020-07-27-highlights-from-git-2-28/#introducing-init-defaultbranch).

[GitHub Desktop](https://desktop.github.com/) will also introduce a default branch setting for new repositories later this month.

#### From `master` to `main` on October 1, 2020

`main` is the most popular replacement for `master` that we’re seeing across GitHub. We like it because it’s short, it keeps your muscle memory intact, and it translates well across most languages. We’re using `main` for our newly-created repositories and for the repositories we’re moving now, like [dependabot-core](https://github.com/dependabot/dependabot-core).

On **October 1, 2020,** if you haven't changed the default branch for new repositories for your user, organization, or enterprise, it will automatically change from **`master`** to **`main`**. You can **opt out of this change** at any time:

1. For users, on the https://github.com/settings/repositories page
2. For organization owners, on the `https://github.com/organizations/YOUR-ORGANIZATION/settings/repository-defaults` page
3. For enterprise administrators, on the `https://github.com/enterprises/YOUR-ENTERPRISE/settings/member_privileges` page

This setting **does not impact any of your existing repositories.** Existing repositories will continue to have the same default branch they have now.

<a name="later-this-year"></a>

### Later this year: seamless move for existing repositories 🚀

For existing repositories, renaming the default branch today causes a set of challenges:

- Open pull requests need to be retargeted to the new branch
- Draft releases need to be retargeted to the new branch
- Branch protection policies need to be transferred to the new branch

By the end of the year, we'll make it seamless for existing repositories to rename their default branch. When you rename the branch, we’ll retarget your open PRs and draft releases, move your branch protection policies, and more - all automatically. And, we’re also looking into redirecting users who `git fetch` or `git clone` the old branch name to the new branch name (with a warning and instructions to update their local clone), so it’s easy for your contributors to move. You’ll be able to do a rename from GitHub.com, GitHub Desktop, or the CLI.
