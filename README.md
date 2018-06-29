# Decision Lab website

A quick way for everyone to learn how to use GitHub and Markdown. (Site design based on [al-folio](https://github.com/alshedivat/al-folio).)

## The super-basics
Hopefully, everyone in the lab will be able to:
- Update their own "team" profile
- Update the list of publications
- Add news posts

To do this, you'll first need to understand a little about: 
1. **GitHub**. For our purposes, you can think of GitHub as being like Google Docs, but for pieces of code. Multiple people can work on the same code in GitHub, and it keeps track of who made what changes and when, and makes it easy to reverse changes that have been made. One really nice feature for this site: instead of directly editing the HTML (which is not really meant for humans to understand), you'll be giving GitHub information in two human-readable formats, which a GitHub tool called Jekyll will use to generate the HTML. 
2. **Markdown**. This README.md file is written in Markdown. Markdown allows for simple formatting like **bold** (double asterisks like this: `**bold**`), *italics* (single asterisks like this: `*italics*`), and [hyperlinks](http://www.ucsf.edu) (put the linked text in square brackets immediately followed by the address in parens, like: `[hyperlinks](http://www.ucsf.edu)`). See [this cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) for more details; you can also check out the markdown in this README file by opening [winstonchiong.github.io/README.md](https://github.com/winstonchiong/winstonchiong.github.io/blob/master/README.md) and clicking "Raw."
3. **YAML**. YAML is a structured data format that uses space-indents (no tabs!) to show structure and colons to associate fields and values. For example:
    ```
    - name: Alex Beagle
      position: Medical Student
      email: alex.beagle (at) ucsf.edu
    - name: Julia Heunis
      position: Medical Student
      email: julia.heunis (at) ucsf.edu
    - name: Carson Quinn
      position: Medical Student
      email: carson.quinn (at) ucsf.edu
    ```
    This list has three entries. Each entry has fields for name, position, and e-mail address. Note that you don't have to put strings within quotation marks, although sometimes this is helpful if your string has special characters like colons or quotation marks.
    
## How to update (or add) a team profile
Two steps:
### Edit the team member data in the YAML file /_data/members.yml


A simple and clean [Jekyll](https://jekyllrb.com/) theme for academics.

[![Screenshot](assets/img/full-screenshot.png)](https://alshedivat.github.io/al-folio/)

Originally, **al-folio** was based on the [\*folio theme](https://github.com/bogoli/-folio) (published by [Lia Bogoev](http://liabogoev.com) and under the MIT license).
Since then, it got a full re-write of the styles and many additional cool features.
The emphasis is on whitespace, transparency, and academic usage: [theme demo](https://alshedivat.github.io/al-folio/).

## Getting started

For more about how to use Jekyll, check out [this tutorial](https://www.taniarascia.com/make-a-static-website-with-jekyll/).
Why Jekyll? Read this [blog post](https://karpathy.github.io/2014/07/01/switching-to-jekyll/)!

### Installation

Assuming you have [Ruby](https://www.ruby-lang.org/en/downloads/) and [Bundler](https://bundler.io/) installed on your system (*hint: for ease of managing ruby gems, consider using [rbenv](https://github.com/rbenv/rbenv)*), first fork the theme from `github.com:alshedivat/al-folio` to `github.com:<your-username>/<your-repo-name>` and do the following:

```bash
$ git clone git@github.com:<your-username>/<your-repo-name>.git
$ cd <your-repo-name>
$ bundle install
$ bundle exec jekyll serve
```

Now, feel free to customize the theme however you like (don't forget to change the name!).
After you are done, **commit** your final changes.
Now, you can deploy your website to [GitHub Pages](https://pages.github.com/) by running the deploy script:

```bash
$ ./bin/deploy [--user]
```
By default, the script uses the `master` branch for the source code and deploys the webpage to `gh-pages`.
The optional flag `--user` tells it to deploy to `master` and use `source` for the source code instead.
Using `master` for deployment is a convention for [user and organization pages](https://help.github.com/articles/user-organization-and-project-pages/).

**Note:** when deploying your user or organization page, make sure the `_config.yml` has `url` and `baseurl` fields as follows.

```
url: # should be empty
baseurl:  # should be empty
```

### Usage

Note that `_pages/about.md` is built to index.html in the published site. There is therefore no need to have a separate index page for the project. If an index page does exist in the root directory then this will prevent `_pages/about.md` from being added to the built site.

## Features

#### Ergonomic Publications

Your publications page is generated automatically from your BibTex bibliography.
Simply edit `_bibliography/papers.bib`.
You can also add new `*.bib` files and customize the look of your publications however you like by editing `_pages/publications.md`.

Keep meta-information about your co-authors in `_data/coauthors.yml` and Jekyll will insert links to their webpages automatically.

#### Collections
This Jekyll theme implements collections to let you break up your work into categories.
The example is divided into news and projects, but easily revamp this into apps, short stories, courses, or whatever your creative work is.

> To do this, edit the collections in the `_config.yml` file, create a corresponding folder, and create a landing page for your collection, similar to `_pages/projects.md`.

Two different layouts are included: the blog layout, for a list of detailed descriptive list of entries, and the projects layout.
The projects layout overlays a descriptive hoverover on a background image.
If no image is provided, the square is auto-filled with the chosen theme color.
Thumbnail sizing is not necessary, as the grid crops images perfectly.

#### Theming
Six beautiful theme colors have been selected to choose from.
The default is purple, but quickly change it by editing `$theme-color` variable in the `_sass/variables.scss` file (line 72).
Other color variables are listed there, as well.

#### Photos
Photo formatting is made simple using rows of a 3-column system.
Make photos 1/3, 2/3, or full width.
Easily create beautiful grids within your blog posts and projects pages:

<p align="center">
  <a href="https://alshedivat.github.io/al-folio/projects/1_project/">
    <img src="assets/img/photos-screenshot.png" width="75%">
  </a>
</p>

#### Code Highlighting
This theme implements Jekyll's built in code syntax highlighting with Pygments.
Just use the liquid tags `{% highlight python %}` and `{% endhighlight %}` to delineate your code:

<p align="center">
  <a href="https://alshedivat.github.io/al-folio/blog/2015/code/">
    <img src="assets/img/code-screenshot.png" width="75%">
  </a>
</p>

## Contributing

Feel free to contribute new features and theme improvements by sending a pull request.
Style improvements and bug fixes are especially welcome.

## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
