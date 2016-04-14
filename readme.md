# /dev/solita staging

This is the staging environment for /dev/solita. Try out your changes here before creating a pull request to the production repository. Changes pushed to gh-pages branch will automatically appear in http://dev-staging.solita.fi

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

## Important

When you merge your feature branch to staging, make sure you don't accidentally overwrite the CNAME-file. CNAME defines the URL of the environment, which must remain as 'dev-staging.solita.fi'.

One way to make sure you don't accidentally change the CNAME is to run make git ignore any changes to the file. This can be done by running the following command in your local clone:

```bash
git update-index --assume-unchanged CNAME
```

After this git will ignore any changes in the file. If you do this and one day need to change the file, you can run this command to undo the index update:

```bash
git update-index --no-assume-unchanged CNAME
```