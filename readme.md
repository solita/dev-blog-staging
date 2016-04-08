# /dev/solita staging

This is the staging environment for http://dev.solita.fi/. Try out your changes here before creating a pull request to the production repository.

Instructions for setting up the blog locally in the production repo: https://github.com/solita/solita.github.com

## How to use staging

Add this repository as a remote in the local clone of your /dev/solita/ -fork.

E.g. like this:

```bash
git remote add staging git@github.com:solita/dev-blog-staging.git
git checkout -b gh-pages
git branch -u staging/gh-pages
```

Now you can (rebase and) merge your local changes to gh-pages branch and push them straight to staging.