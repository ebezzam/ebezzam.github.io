---
layout: posts
title:  "Site setup with GitHub Pages"
date:   2018-07-11 17:37:56 +0200
permalink: /blog/site-setup
toc: true
---

This first post is more of a reminder for me how to setup this website, but hopefully can be of interest/use to others!

---

## Quick setup for blogging

Simple Jekyll setup after setting up Ruby environment (modified from [here](https://jekyllrb.com/docs/quickstart/)):

```bash
gem install jekyll bundler

# create website at current directory
# this will auto-generate a few files for a simple website
jekyll new . 

# build and display
bundle exec jekyll serve

# Now browse to http://localhost:4000
```

Now it is possible to make blog posts by using the correct file naming convention.

The generated site will be placed in a directory called `_site`.  It’s probably a good idea to add this to your `.gitignore` file, which may automatically be done.

In the generated `_config.yml` file, feel free to modify the entries, such as 
`title`, to customize your website!

---

## Minimal mistakes template

We now switch to [this tutorial](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) for a nice template. It is assumed that
the previous steps have been completed.

### Updating `Gemfile`

As we will be using GitHub Pages, we will replace `gem "jekyll"` in `Gemfile` with:

```ruby
gem "github-pages", group: :jekyll_plugins
```

Run `bundle update` from the terminal to make sure that all gems are properly installed.

### Modifying generated content

* Replace the generated `index.md` file with this [HTML file](https://github.com/mmistakes/minimal-mistakes/blob/master/index.html).
* Remove `about.md`.
* For any files in `_posts_`, change the `layout` entry at the top to `posts`.

### Edit configuration file `_config.yml`

* Copy or re-create this [`_config.yml` file](https://github.com/mmistakes/minimal-mistakes/blob/master/_config.yml).
* Make sure the following line is there and uncommented:

```
remote_theme           : "mmistakes/minimal-mistakes"
```

As before, feel free to modify the entries to customize your website. You can refer to [here](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) for an in-depth explanation of each setting.

---

## Adding masthead (top navigation bar) and pages

Create a `_data` directory in your project and add a [`_navigation.yml`](https://github.com/mmistakes/minimal-mistakes/blob/master/_data/navigation.yml) file inside. As seen in the example `_navigation.yml` file, you can place multiple `title` entries which will correspond to the options on the "masthead" at the top of your webpage. Clicking a particular option will navigate to the url specified by the `url` entry in the `_navigation.yml` file.

For example, the following entry
```
- title: "Quick-Start Guide"
  url: https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/
```
will create a "Quick-Start Guide" option at the masthead to go the link specified by the `url` entry.

It also possible to link internally to your own pages such as an "About" page:
```
- title: "About"
  url: /about/
```
where `/about/` should be a _permalink_ within your website structure, such as at the header of the file `_pages/about.md`.

See [here](https://mmistakes.github.io/minimal-mistakes/docs/pages/) for clear instructions on how to create pages.

---

## Finer detail customization

For stylistic modifications, it is very likely you will need to [change the default theme](https://mmistakes.github.io/minimal-mistakes/docs/overriding-theme-defaults/).

This can be done by copying the following directories:
```
_includes
_layouts
_sass
```
from [here](https://github.com/mmistakes/minimal-mistakes) (you can download the repository as a `.zip` file, extract, and then copy the desired folders).

At this [link](https://mmistakes.github.io/minimal-mistakes/docs/stylesheets/), they describe some styles modifications that can be made.


### Adjusting text width for `posts` and `pages`

Perhaps you find the default text width to be too narrow. This can be adjusted by going inside the `_sass` files.

Inside `_sass/minimal-mistakes/_page.scss` (for `pages`) and `_sass/minimal-mistakes/_archive.scss` (for `posts`), adjust the `padding-right` parameter that appears under the `width` entry as such:

```
@include breakpoint($large) {
    float: right;
    width: calc(100% - #{$right-sidebar-width-narrow});
padding-right: $right-sidebar-width-narrow;
}
```

or remove the `padding-right` line completely. Related GitHub issues: [#1265](https://github.com/mmistakes/minimal-mistakes/issues/1265) and [#1373](https://github.com/mmistakes/minimal-mistakes/issues/1373).


