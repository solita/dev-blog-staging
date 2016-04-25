# /dev/solita/greetings

Here are some developer-oriented thoughts from [Solita Oy](http://www.solita.fi/). Our stories have not yet been told. More will come. Stay tuned at <http://dev.solita.fi>.

## Writing

We use a combination of Jekyll and Github Pages to run the site.

If you want to write a post, here's how:

1. Fork this project to yourself (upper right corner)
  - You need a Github account to do this
2. Clone your own fork to your computer (git clone)
3. Add your author info to `_config.yml`
  - The email value is a MD5 hash of your email
4. Write a new post under the `_posts` folder using Markdown, look at other posts for example of what to write there
5. If you have Ruby and Jekyll, preview your post locally (instructions below)
6. Create a pull request at https://github.com/solita/solita.github.com/pull/new/master
  - Choose your fork on the right
  - Write some info about the post
7. Wait for comments and publish!


## Previewing posts

You need Ruby and Jekyll if you want to preview your posts locally on the blog. If you're fine with just previewing the Markdown, you can use a Markdown preview script, like [this one for Sublime Text](https://github.com/revolunet/sublimetext-markdown-preview).


### Option A, Running a virtual machine (standardized environment)

1. Install Vagrant
2. Install Virtualbox
3. `cd vagrant`
4. `vagrant up blag`
5. Wait patiently as the ruby goodness is downloaded and configured
6. http://localhost:4444 now should serve your version of the blog

If anything goes wrong, good luck. vagrant ssh blag and try figure it out.

When you're done you might want to shutdown the virtual machine. vagrant destroy or something like that.


### Option B, Installing Ruby on your workstation

For Windows, download & install the latest Ruby 2.x and Development
Kit from http://rubyinstaller.org/downloads/

**Note:** Make sure to tick the checkbox "Add Ruby to PATH" (or
something). You can also try: https://github.com/vertiginous/pik/

For Debian (Jessie), the easiest path seems to be:

1. ``sudo apt-get install bundler zlib1g-dev``
2. ``bundle install``
3. ``bundle exec jekyll serve --watch``

For OSX, use the instructions below. If you have installed Xcode, you
might have ruby already. No guarantees
about this working with that so use RVM

1. `curl -L https://get.rvm.io | bash -s stable --ruby=2.2.1`
2. fork this repo
3. go to your working copy of solita.github.com
4. `rvm use 2.2.1`
5. verify that 2.2.1 used by `ruby -v`
(On linux you might need to fix gnome-termina: http://rvm.io/integration/gnome-terminal)
6. `gem install bundler`
7. Run `bundle install` for depencies
8. Make sure the installation succeeds
9. Type in: `bundle exec foreman start`
10. Open browser to: http://localhost:4000/

## Development

For development, you need Ruby and Jekyll. If you want to tweak the CSS, you need Compass. Also, if you want to make stuff easier, install foreman.

1. Install Ruby (above)
2. Go to your cloned copy of solita.github.com
3. To install Jekyll, Compass and foreman, type into a command prompt or terminal: `bundle install`
4. Make sure the install succeeds
5. Type in: `bundle exec foreman start`
6. Jekyll and Compass should start!

### Updating to Jekyll 3

**Note:** This concerns only people who forked this repo when it was still running Jekyll 2 (prior to 25.4.2016).

GitHub has recently moved from using Jekyll 2 to Jekyll 3. Starting from 1.5.2016 GitHub will only support Jekyll 3, so this repository has been updated to use the new version also.

If you're interested in the changes the update brings, you can read about them here https://github.com/blog/2100-github-pages-now-faster-and-simpler-with-jekyll-3-0. The way posts are written does not change at all, so for a blog author the changes are practically unnoticable.

#### Option A, if you're using Vagrant

If you're using Vagrant, you only need to sync your local fork with the main repository to get the updated files and then start Vagrant with ``vagrant up blag`` like before.

If you don't know how to sync your fork, GitHub has good instructions for it. First you need to add the main repository as a remote (https://help.github.com/articles/configuring-a-remote-for-a-fork/) after which you can sync your fork (https://help.github.com/articles/syncing-a-fork).


#### Option B, if you're using Ruby

Jekyll 3 only supports Ruby 2. First check which version you have with ``ruby -v``.

If already have Ruby 2.x simply update the local gems with ``bundle update``. 

If you currently have Ruby 1.x, you must first install Ruby 2 and then install the packages in the gemfile. For Windows, you can get Ruby 2 from http://rubyinstaller.org/downloads/. For OSX, you can install Ruby 2 with RVM:

1. `rvm install 2.2.1`
2. `rvm use 2.2.1`
3. `gem install bundler`
4. `bundle install`

## Technology stack

/dev/solita is built using all the hippiest hip technologies available:

    git, Github Pages, Ruby, Jekyll, Markdown, Sass, Compass, foreman, jQuery, Gravatar, disqus, Google Analytics, AddThis
