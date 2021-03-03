# Philipp Eisenhauer's Personal site

## Instructions

### Build Locally

This website uses Jekyll.

For official guides to install Jekyll, see [Installation | Jekyll • Simple, blog-aware, static sites](https://jekyllrb.com/docs/installation/).

For GitHub's guide to locally build and test the website, see [Testing your GitHub Pages site locally with Jekyll - GitHub Docs](https://docs.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll).

The basic building steps are:

1. Clone this repository to local machine.
1. Run `jekyll --version` to make sure you have jekyll installed correctly.
1. Run `bundle install` to make sure you have all the dependencies installed.
    - Alternatively, if file `Gemfile.lock` already exists, run `bundle update`.
1. Run `bundle exec jekyll serve --livereload --safe` to start local server.
    - Note: you should access the `Server address` (for example, `http://127.0.0.1:4000`) instead of `LiveReload address`. 
    - The `safe` flag is necessary since GitHub Pages does not allow non-whitelisted plugins.

### Add A Page

1. Add a file under the folder `_pages`
2. Create link to this page. Either:
    - In the main navigation bar: add an entry in `_data/navigation.yml`
    - Insert link to this page in existing pages.
