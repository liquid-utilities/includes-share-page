# Includes Share Page
[heading__top]:
  #includes-share-page
  "&#x2B06; Builds list of links for sharing on social media sites"


Builds list of links for sharing on social media sites


## [![Byte size of Includes Share][badge__main__includes_share_page__source_code]][includes_share_page__main__source_code] [![Open Issues][badge__issues__includes_share_page]][issues__includes_share_page] [![Open Pull Requests][badge__pull_requests__includes_share_page]][pull_requests__includes_share_page] [![Latest commits][badge__commits__includes_share_page__main]][commits__includes_share_page__main] [![includes-share-page Demos][badge__gh_pages__includes_share_page]][gh_pages__includes_share_page]


------


- [:arrow_up: Top of Document][heading__top]

- [:building_construction: Requirements][heading__requirements]

- [:zap: Quick Start][heading__quick_start]

  - [:memo: Edit Your ReadMe File][heading__your_readme_file]
  - [:fountain: Your Layout File][heading__your_layout_file]
  - [:telescope: Your Privacy Policy][heading__your_privacy_policy]
  - [:floppy_disk: Commit and Push][heading__commit_and_push]

- [&#x1F9F0; Usage][heading__usage]

  - [:construction: Post FrontMatter Example][heading__post_frontmatter_example]
  - [:spider_web: Post Share List Example][heading__post_share_list_example]
  - [:paintbrush: CSS Styling][heading__css_styling]

- [:symbols: FrontMatter API/Configuration][heading__frontmatter_api_configuration]

- [&#x1F5D2; Notes][heading__notes]

- [:card_index: Attribution][heading__attribution]

- [:balance_scale: Licensing][heading__license]



------



## Requirements
[heading__requirements]:
  #requirements
  "&#x1F3D7; Prerequisites and/or dependencies that this project needs to function properly"


This repository depends upon [Jekyll][jekyll_rb__home] which is supported by [GitHub Pages][github_docs__github_pages__jekyll], further details about setup can be found from [documentation][jekyll_rb__github_pages] published by the Jekyll maintainers regarding GitHub Pages.


___


## Quick Start
[heading__quick_start]:
  #quick-start
  "&#9889; Perhaps as easy as one, 2.0,..."


This repository encourages the use of Git Submodules to track dependencies


**Bash Variables**


```Bash
_module_name='includes-share-page'
_module_https_url="https://github.com/liquid-utilities/includes-share-page.git"
_module_base_dir='_includes/modules'
_module_path="${_module_base_dir}/${_module_name}"
```


**Bash Submodule Commands**


```Bash
cd "<your-git-project-path>"

git checkout gh-pages
mkdir -vp "${_module_base_dir}"

git submodule add\
 -b main --name "${_module_name}"\
 "${_module_https_url}" "${_module_path}"
```


------


### Your ReadMe File
[heading__your_readme_file]:
  #your-readme-file
  "&#x1F4DD; Suggested additions for your ReadMe.md file so everyone has a good time with submodules"


Suggested additions for your _`ReadMe.md`_ file so everyone has a good time with submodules


```MarkDown
Clone with the following to avoid incomplete downloads


    git clone --recurse-submodules <url-for-your-project>


Update/upgrade submodules via


    git submodule update --init --merge --recursive
```


------


### Your Layout File
[heading__your_layout_file]:
  #your-layout-file
  "&#x26F2; How to include source code from this project within your Layout"


Add an include statement, _`{% include modules/includes-share-page/share-page.html %}`_, within the chosen Layout file, for example if utilizing the [`minima/jekyll`](https://github.com/jekyll/minima) theme modifications may be similar to...


**`_layouts/post.html`**


```HTML
---
layout: default
license: MIT
source: https://raw.githubusercontent.com/jekyll/minima/v2.0.0/_layouts/post.html
---
<article class="post" itemscope itemtype="http://schema.org/BlogPosting">

  <header class="post-header">
    <h1 class="post-title" itemprop="name headline">{{ page.title | escape }}</h1>
    <p class="post-meta"><time datetime="{{ page.date | date_to_xmlschema }}" itemprop="datePublished">{{ page.date | date: "%b %-d, %Y" }}</time>{% if page.author %} • <span itemprop="author" itemscope itemtype="http://schema.org/Person"><span itemprop="name">{{ page.author }}</span></span>{% endif %}</p>
  </header>

  <div class="post-content" itemprop="articleBody">
    {{ content }}
  </div>

  {%- unless page.share == false -%}
    {% include modules/includes-share-page/share-page.html %}
  {%- endunless -%}

  {% if site.disqus.shortname %}
    {% include disqus_comments.html %}
  {% endif %}
</article>
```


------


### Your Privacy Policy
[heading__your_privacy_policy]:
  #your-privacy-policy
  "&#x1F52D; Suggestions for editing your privacy policy"


It is a good idea (and in some regions, a requirement) to edit your privacy policy such that clients of your site are notified of information shared with third-parties. For example a notice such as...


> **Notice**, clicking on share links will share the URL, page metadata with that site, and (if you are logged at that site) that you have shared a link. Data that you share with these third-parties are subject to the policies of those sites.


... May be sufficient, however, you should consult with your own legal counsel to ensure compliance with the laws local to the clients that your site serves.


------


### Commit and Push
[heading__commit_and_push]:
  #commit-and-push
  "&#x1F4BE; It may be just this easy..."


```Bash
git add .github/README.md _layouts/post.html


git commit -F- <<'EOF'
:heavy_plus_sign: Adds `liquid-utilities/includes-share-page#1` submodule



**Adds**


- `.gitmodules`, tracks submodules AKA Git within Git _fanciness_

- `_modules_/includes-share-page`, Builds list of links for sharing on social media sites

- `_layouts/post.html`, modified default layout from `jekyll/minima` theme


**Edits**


- `README.md`, updates installation and updating guidance
EOF


git push origin gh-pages
```


**:tada: Excellent :tada:** your project is now ready to begin unitizing code from this repository!


___


## Usage
[heading__usage]:
  #usage
  "&#x1F9F0; How to utilize this repository within anther project"


Set defaults for entire site within your `_config.yml` file...


**`_config.yml` (snip)**


```YAML
share:
  disable_linkedin: true
  figcaption: Share this elsewhere via...
```


------


### Post FrontMatter Example
[heading__post_frontmatter_example]:
  #post-frontmatter-example
  "&#x1F6A7; Post FrontMatter configuration example"


Modify `share` configurations via individual page/post FrontMatter...


**`_posts/2020-07-06-example-post.md` (FrontMatter)**


```YAML
---
layout: post
title: Example Post
description: 'Tests list generated by `includes-share-page/share-page.html` project'
categories: programming webdev
date: 2020-07-19 15:23:03 -0700
share:
  disable_linkedin: true
  text: Customized text for when someone shares a link to this post
---
```


------


### Post Share List Example
[heading__post_share_list_example]:
  #post-share-list-example
  "&#x1f578; HTML example output"


**`2020/07/19/example-post.html` (snip)**


```HTML
<figure class="social-share__container">
  <figcaption>Share this elsewhere via...</figcaption>
  <ul class="social-share__list">

    <li class="social-share__item">
      <a href="https://www.facebook.com/sharer.php?u=https%3A%2F%2Fauthor.github.io%2Frepo-name%2Fprogramming%2Fwebdev%2F2020%2F07%2F06%2Fexample-post.html"
         class="social-share__link facebook-share fa fa-facebook"
         data-name="Facebook">
        Facebook
      </a>
    </li>

    <li class="social-share__item">
      <a href="https://reddit.com/submit?url=https%3A%2F%2Fauthor.github.io%2Frepo-name%2Fprogramming%2Fwebdev%2F2020%2F07%2F06%2Fexample-post.html&title=Example%20Post"
         class="social-share__link reddit-share fa fa-reddit"
         data-name="Reddit">
        Reddit
      </a>
    </li>

    <li class="social-share__item">
      <a href="https://www.twitter.com/intent/tweet?url=https%3A%2F%2Fauthor.github.io%2Frepo-name%2Fprogramming%2Fwebdev%2F2020%2F07%2F06%2Fexample-post.html&hashtags=programming,webdev&text=Customized%20text%20for%20when%20someone%20shares%20a%20link%20to%20this%20post"
         class="social-share__link twitter-share fa fa-twitter"
         data-name="Twitter">
        Twitter
      </a>
    </li>

  </ul>
</figure>
```


------


### CSS Styling
[heading__css_styling]:
  #css-styling
  "&#x1f58c; Tips on how to style listed share links"


This project is compatible with Font Awesome, include a `link` to their style sheet for easy icons...


```HTML
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
```

This project utilizes BEM (Block Element Modifier) syntax for HTML/CSS class names, the `block` may be modified via page FrontMatter and/or site configuration file...


```YAML
share:
  element_class_block: social-share
```


The unordered list can be re-styled via CSS by targeting the `.social-share__list` class, for example the following can remove default list style _bullets_...


```CSS
.social-share__list {
  list-style: none;
  margin: 0;
  padding: 0;
}
```


___


## FrontMatter API/Configuration
[heading__frontmatter_api_configuration]:
  #frontmatter-apiconfiguration
  "&#x1F523; FrontMatter properties under `share` that can modify the behavior of this project"


FrontMatter properties under `share` that can modify the behavior of this project;


- `disable_facebook` Boolean, default `nil`, if `true` disables sharing to Facebook

- `disable_linkedin` Boolean, default `nil`, if `true` disables sharing to LinkedIn

- `disable_reddit` Boolean, default `nil`, if `true` disables sharing to Reddit

- `disable_twitter` Boolean, default `nil`, if `true` disables sharing to Twitter

- `disable_text` Boolean, default `nil`, if `true` displays name of site that share link corisponds to

- `element_class_block` String, default `"social-share"`, defines CSS class prefix for each element

- `figcaption` Boolean (`false`) or String, default `nil`, if `false` disables figcaption text, otherwise if _truthy_ then value becomes the figcaption text

- `tags` Boolean (`false`) or list, default `page.categories` default `page.category`, list of tags for use when sharing to sites such as Twitter

- `text` Boolean (`false`) or String, default `page.description` default `page.excerpt`, if not `false` then auto-fills text when sharing


The `figcaption` text as well as the link text can be suppressed by defining the following configurations within page FrontMatter or site configuration file...


```YAML
share:
  disable_text: true
  figcaption: false
```


___


## Notes
[heading__notes]:
  #notes
  "&#x1F5D2; Additional things to keep in mind when developing"


This repository may not be feature complete and/or fully functional, Pull Requests that add features or fix bugs are certainly welcomed.


- [Fork][includes_share_page__fork_it] this repository to an account that you have write permissions for.

- Add remote for fork URL. The URL syntax is _`git@github.com:<NAME>/<REPO>.git`_...


```Bash
cd ~/git/hub/liquid-utilities/includes-share-page

git remote add fork git@github.com:<NAME>/includes-share-page.git
```


- Commit your changes and push to your fork, eg. to fix an issue...


```Bash
cd ~/git/hub/liquid-utilities/includes-share-page


git commit -F- <<'EOF'
:bug: Fixes #42 Issue


**Edits**


- `<SCRIPT-NAME>` script, fixes some bug reported in issue
EOF


git push fork main
```


> Note, the `-u` option may be used to set `fork` as the default remote, eg. _`git push fork main`_ however, this will also default the `fork` remote for pulling from too! Meaning that pulling updates from `origin` must be done explicitly, eg. _`git pull origin main`_


- Then on GitHub submit a Pull Request through the Web-UI, the URL syntax is _`https://github.com/<NAME>/<REPO>/pull/new/<BRANCH>`_


> Note; to decrease the chances of your Pull Request needing modifications before being accepted, please check the [dot-github](https://github.com/liquid-utilities/.github) repository for detailed contributing guidelines.


___


## Attribution
[heading__attribution]:
  #attribution
  "&#x1F4C7; Resources that where helpful in building this project so far."


- [CSS Tricks -- The Simplest (and Most Performant) Way to Offer Sharing Links for Social Media](https://css-tricks.com/simple-social-sharing-links/)

- [GitHub -- `github-utilities/make-readme`](https://github.com/github-utilities/make-readme)

- [GitHub -- `bradvin/social-share-urls`](https://github.com/bradvin/social-share-urls)

- [StackOverflow -- How do I make my own simple social media buttons that grab the current URL automatically?](https://stackoverflow.com/questions/24046807)

- [StackOverflow -- How to semantically provide a caption title, or label for a list in HTML](https://stackoverflow.com/questions/1141639)

- [StackOverflow -- How to make a custom linkedin share button -- Answer by `HoldOffHunger`](https://stackoverflow.com/questions/10713542/61583006#61583006)

- [Shopify Help -- `url_param_escape`](https://help.shopify.com/en/themes/liquid/filters/string-filters#url_param_escape)

- [Twitter Developer -- Tweet Button](https://developer.twitter.com/en/docs/twitter-for-websites/tweet-button/overview)

- [W3 Schools -- How TO - Social Media Buttons](https://www.w3schools.com/howto/howto_css_social_media_buttons.asp)


___


## License
[heading__license]:
  #license
  "&#x2696; Legal side of Open Source"


```
Builds list of links for sharing on social media sites
Copyright (C) 2020 S0AndS0

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, version 3 of the License.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

```


For further details review full length version of [AGPL-3.0][branch__current__license] License.



[branch__current__license]:
  /LICENSE
  "&#x2696; Full length version of AGPL-3.0 License"


[badge__commits__includes_share_page__main]:
  https://img.shields.io/github/last-commit/liquid-utilities/includes-share-page/main.svg

[commits__includes_share_page__main]:
  https://github.com/liquid-utilities/includes-share-page/commits/main
  "&#x1F4DD; History of changes on this branch"


[includes_share_page__community]:
  https://github.com/liquid-utilities/includes-share-page/community
  "&#x1F331; Dedicated to functioning code"

[includes_share_page__gh_pages]:
  https://github.com/liquid-utilities/includes-share-page/tree/
  "Source code examples hosted thanks to GitHub Pages!"

[badge__gh_pages__includes_share_page]:
  https://img.shields.io/website/https/liquid-utilities.github.io/includes-share-page/index.html.svg?down_color=darkorange&down_message=Offline&label=Demo&logo=Demo%20Site&up_color=success&up_message=Online

[gh_pages__includes_share_page]:
  https://liquid-utilities.github.io/includes-share-page/index.html
  "&#x1F52C; Check the example collection tests"

[issues__includes_share_page]:
  https://github.com/liquid-utilities/includes-share-page/issues
  "&#x2622; Search for and _bump_ existing issues or open new issues for project maintainer to address."

[includes_share_page__fork_it]:
  https://github.com/liquid-utilities/includes-share-page/
  "&#x1F531; Fork it!"

[pull_requests__includes_share_page]:
  https://github.com/liquid-utilities/includes-share-page/pulls
  "&#x1F3D7; Pull Request friendly, though please check the Community guidelines"

[includes_share_page__main__source_code]:
  https://github.com/liquid-utilities/includes-share-page/
  "&#x2328; Project source!"

[badge__issues__includes_share_page]:
  https://img.shields.io/github/issues/liquid-utilities/includes-share-page.svg

[badge__pull_requests__includes_share_page]:
  https://img.shields.io/github/issues-pr/liquid-utilities/includes-share-page.svg

[badge__main__includes_share_page__source_code]:
  https://img.shields.io/github/repo-size/liquid-utilities/includes-share-page


[jekyll_rb__home]:
  https://jekyllrb.com/
  "Jekyll home page"

[jekyll_rb__github_pages]:
  https://jekyllrb.com/docs/github-pages/
  "Jekyll documentation for GitHub Pages setup"

[github_docs__github_pages__jekyll]:
  https://docs.github.com/en/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll
  "GitHub Pages documentation on Jekyll setup"
