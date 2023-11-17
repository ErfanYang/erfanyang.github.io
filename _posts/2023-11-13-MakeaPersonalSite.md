---
share: true
title: Make a Personal Site
sharepath: 
sharetitle: Make a Personal Site
mermaid: false
---
## Quick start
If you don't want to rent a server, [Github Pages](https://pages.github.com/) is one of the best choice. Simply create a new repository named _username_.github.io and fork any template that you like, then you'll find your site at https:username.github.io !😎This is the key step. Others are all about html, css, markdown, etc.
Note:
- Luckily Github Pages supports Markdown (md) files. Unluckily, Github itself has a unique markdown engine, which makes it imcompatible to compile md files in other grammar. GitHub's grammar, called Github flavored markdown(GFM), extends the standard markdown syntax. More info see [GitHub Flavored Markdown Spec](https://github.github.com/gfm/#:~:text=GitHub%20Flavored%20Markdown%2C%20often%20shortened%20as%20GFM%2C%20is,dialect.%20GFM%20is%20a%20strict%20superset%20of%20CommonMark.) or  [github_markdown语法大全整理 - 简书 (jianshu.com)](https://www.jianshu.com/p/40ba812dd973)
## Work with Obsidian
Plugins: Github Publisher & Frontmatter
- [使用Obsidian+GitHub Pages部署在线博客 · Leo's Blog (leoz2050.github.io)](https://leoz2050.github.io/DigitalGarden/2023/09/03/Build-Blog-Online.html)
- [obsidian发布的免费替代品 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/634583092)
## Basic web background
### HTML
### CSS
## Photo wall
Source: [How to create a responsive image gallery with CSS flexbox - LogRocket Blog](https://blog.logrocket.com/responsive-image-gallery-css-flexbox/)
Example: [Static Template (csb.app)](https://sts6l7.csb.app/)
Useful tools: Upload photos by [PicGo](https://picgo.github.io/PicGo-Doc/zh/guide/config.html#github%E5%9B%BE%E5%BA%8A)
## Native compilation
### What is Ruby and gem?
### The entire process
If you are lucky enough, you may find this in your cmd window:
```
Configuration file: C:/Users/12150/myblog/_config.yml
To use retry middleware with Faraday v2.0+, install `faraday-retry` gem
   GitHub Metadata: site.name is set in _config.yml, but many plugins and themes expect site.title to be used instead. To avoid potential inconsistency, Jekyll GitHub Metadata will not set site.title to the repository's name.
            Source: C:/Users/12150/myblog
       Destination: C:/Users/12150/myblog/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
       Jekyll Feed: Generating feed for posts
                    done in 2.461 seconds.
 Auto-regeneration: enabled for 'C:/Users/12150/myblog'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
```
Simply enter the server address http://127.0.0.1:4000 and you'll find your site! Jekyll will regenerate the site in seconds as long as you change any file. Hooray!🥳
### How to upload to Github: Git
#### What is git and how can I use it?
See [CS61B materials of UC Berkeley](https://fa23.datastructur.es/materials/lab/lab01/)
#### The process
```
git init
git add . (Note that there is a dot!😣)
git commit -m "Your message"
git push
```
### Common errors I met
#### Too slow when installing or updating some packages
I encountered this problem because I was in China. Try VPN first. If it doesn't work, try to add the mirror path ' https://gems.ruby-china.com/ '. The command I used is 
```
bundle config mirror.https://rubygems.org https://gems
.ruby-china.com
```
#### Cannot load such file
```
cannot load such file -- rexml/parsers/baseparser (LoadError)
```
First try "bundle add webrick". If it does not work, try "bundle install" or "bundle update". But the latter command does not always update all gems so sometimes you have to update it manually by changing the version command in "Gemfile" (can be openned in Notepad).
In the process of updating, you might encounter a new error about version control. For example,

```
Fetching gem metadata from https://gems.ruby-china.com/.........
Resolving dependencies...
Could not find compatible versions
Because github-pages >= 9, < 14 depends on kramdown = 1.2.0
  and github-pages < 9 depends on kramdown = 1.0.2,
  github-pages < 14 requires kramdown = 1.0.2 OR = 1.2.0.
And because github-pages >= 14, < 32 depends on kramdown = 1.3.1,
  github-pages < 32 requires kramdown = 1.0.2 OR = 1.2.0 OR = 1.3.1.
And because github-pages >= 178 depends on jekyll-sass-converter = 1.5.2
  and jekyll >= 4.3.0 depends on jekyll-sass-converter >= 2.0, < 4.0,
  jekyll >= 4.3.0 requires kramdown = 1.0.2 OR = 1.2.0 OR = 1.3.1.
So, because jekyll >= 4.3.0 depends on kramdown >= 2.3.1, < 3.A
  and Gemfile depends on jekyll ~> 4.3.2,
  version solving has failed.
```

P.S. I also met a weird error like this
```
[!] There was an error parsing `injected gems`: You cannot specify the same gem twice with different version requirements.
You specified: webrick (~> 1.8) and webrick (>= 0). Gem already added. Bundler cannot continue.

 #  from injected gems:1
 #  -------------------------------------------
 >  gem "webrick", ">= 0"
 #  gem "(~", ">= 0"
 #  -------------------------------------------
```
Somehow it can be solved after I corrected the Gemfile. I haven't figure out why because I'm not quite familiar with Ruby and Jekyll.