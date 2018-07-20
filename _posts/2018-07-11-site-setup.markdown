---
layout: post
title:  Site setup with GitHub Pages
date:   2018-07-11 17:37:56 +0200
permalink: /blog/site-setup
comments: true
---

This first post is more of a reminder for me how to setup a basic website with GitHub Pages, but hopefully it can be of interest/use to others!

<br />
We start off with the most [basic example](#quick) which should only take a couple of minutes to set up after installing the proper Ruby and Jekyll libraries (see [here](https://jekyllrb.com/docs/installation/)).

<br />
We [then](#mm) go over setting up the popular [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) theme, which this website is based off of. [Finally](#this), we go over the setup for the template you see here!

<br />
If you have the Ruby and Jekyll libraries installed, you can skip directly to the setup for this website. However, it is recommended to go over the [Jekyll documentation](https://jekyllrb.com/docs/home/) if you are new to it.

<br />
Let me know if you have any problems with the steps detailed here! I hope others will find this post to be a useful reference :)

---

## <a name="quick"></a>Quick setup for blogging

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

<br />
The generated site will be placed in a directory called `_site`.  It’s probably a good idea to add this to your `.gitignore` file, which may automatically be done.

<br />
In the generated `_config.yml` file, feel free to modify the entries, such as 
`title`, to customize your website!

---

## <a name="mm"></a>Minimal mistakes template

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


### Adding masthead (top navigation bar) and pages

Create a `_data` directory in your project and add a [`_navigation.yml`](https://github.com/mmistakes/minimal-mistakes/blob/master/_data/navigation.yml) file inside. As seen in the example `_navigation.yml` file, you can place multiple `title` entries which will correspond to the options on the "masthead" at the top of your webpage. Clicking a particular option will navigate to the url specified by the `url` entry in the `_navigation.yml` file.

<br />
For example, the following entry
```
- title: "Quick-Start Guide"
  url: https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/
```
will create a "Quick-Start Guide" option at the masthead to go the link specified by the `url` entry.

<br />
It also possible to link internally to your own pages such as an "About" page:
```
- title: "About"
  url: /about/
```
where `/about/` should be a _permalink_ within your website structure, such as at the header of the file `_pages/about.md`.

<br />
See [here](https://mmistakes.github.io/minimal-mistakes/docs/pages/) for clear instructions on how to create pages.

### Finer detail customization

For stylistic modifications, it is very likely you will need to [change the default theme](https://mmistakes.github.io/minimal-mistakes/docs/overriding-theme-defaults/).

<br />
This can be done by copying the following directories from [here](https://github.com/mmistakes/minimal-mistakes) (you can download the repository as a `.zip` file, extract, and then copy the desired folders):
```
_includes
_layouts
_sass
```
At this [link](https://mmistakes.github.io/minimal-mistakes/docs/stylesheets/), they describe some styles modifications that can be made.

#### Setting font and font size

[Issue #1352](https://github.com/mmistakes/minimal-mistakes/issues/1352).

<br />
Line 78 in `_pages.scss`.


#### Adjusting text width for `posts` and `pages`

Perhaps you find the default text width to be too narrow. This can be adjusted by going inside the `_sass` files.

<br />
Inside `_sass/minimal-mistakes/_page.scss`, the following variables can be adjusted to vary the column widths

```
$right-sidebar-width-narrow: 400px !default;
$right-sidebar-width: 250px !default;
$right-sidebar-width-wide: 500px !default;
```
Otherwise, inside `_sass/minimal-mistakes/_page.scss` (for `pages`) and `_sass/minimal-mistakes/_archive.scss` (for `posts`), remove the `padding-right` line completely (when underneath a `width` line):

```
@include breakpoint($large) {
    float: right;
    width: calc(100% - #{$right-sidebar-width-narrow});
    padding-right: $right-sidebar-width-narrow;
}
```
Related GitHub issues: [#1265](https://github.com/mmistakes/minimal-mistakes/issues/1265) and [#1373](https://github.com/mmistakes/minimal-mistakes/issues/1373).

---

## <a name="this"></a>This template!

The original code for the template used in this website can be found [here](https://github.com/jponttuset/jponttuset.github.io). I find this to be a fantastic template due to its simplistic design and the well-designed publications page. More about the template can be read in the [blog of the creator](http://jponttuset.cat/building-an-academic-website/).  

### Basic steps for reproducing and customizing
Copy/clone/fork the repository, navigate to the directory from a Terminal, and run `bundle update` to make sure that all gems are properly installed.

<br />
For editing the author info, you'll again have to dig into the `_config.yml` file.

<br />
To modify the "CV" ("Curriculum" in the original code) and "Publications" pages, you'll have to edit the correspondings HTML files in `_layout`. Very basic HTML coding is needed, so not to worry!

<br />
Adding new pages (such as "Teaching" in this website) simply requires adding a markdown file in the main directory and adding the appropriate link in the `_config.yml` file, e.g.:
```
links:
  - title: CV
    url: /cv/
  - title: Publications
    url: /publications/
  - title: Projects
    url: /projects/
  - title: Teaching
    url: /teaching/
  - title: Blog
    url: /blog/
```

<br />
You can remove the Twitter feed by removing the following snippet in `_layouts/home2.html`:
```html
<a class="twitter-timeline" href="https://twitter.com/jponttuset" data-widget-id="338001751854686210">Tuits de @jponttuset</a>
      <script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+"://platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");</script>
```
Or to add your own timeline, replace the above snippet with the HTML code generated by following [these instructions](https://help.twitter.com/en/using-twitter/embed-twitter-feed).


