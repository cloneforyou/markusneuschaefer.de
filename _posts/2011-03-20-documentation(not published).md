---
layout: post
date: 2011-03-20 12:36
published: false
title: "Documentation - Configuration & First Steps"
description: Basic information about the Steve.
comments: false
category:
- docs
- help
tags:
- documentation
- steve
- jekyll
---

Note:

## youtube-iframes:

change iframe

    src="https://youtube.com/ ..."

to

    src="" data-src="https://youtube.com/ ..."


{% highlight ruby linenos %}
#!/usr/bin/ruby
$LOAD_PATH << '.'
require "support"

class Decade
include Week
   no_of_yrs=10
   def no_of_months
      puts Week::FIRST_DAY
      number=10*12
      puts number
   end
end
d1=Decade.new
puts Week::FIRST_DAY
Week.weeks_in_month
Week.weeks_in_year
d1.no_of_months
{% endhighlight %}


### Configuration
All configuration options are in the <code>\_config.yml</code> file.

<figure>
    <img src="/assets/img/2017_oerde17_logo_award.png" />
    <figcaption>
    Bild: Logo des OER-Award 2017. Quelle: <a href="https://open-educational-resources.de/veranstaltungen/17/award/oer-award-2017-laudatio-qualitaet-fuer-oer/">open-educational-resources.de</a>
    </figcaption>
</figure>

<!-- more -->

##### General Settings
* **name**: Your name.
* **job_title**: Your job title.
* **email**: Your email. There are two cases where email is used. First, if you entered the email and you've activated **show_email** option the end result will be a visible social email icon in the sidebar. The second use of your email is when you do not set your own avatar. In this case your email is used by the gravatar plugin to automatically fetch your gravatar.
* **description**: Describe yourself with a couple of words.
* **avatar**: Write down the full path to the avatar <code>http://mysite.com/blog/assets/images/avatar.jpg</code>. If you comment this row, "Steve" checks if you have an email and shows your gravatar if you have any.
* **favicon**: Want a favicon? Enter the full path here. For example <code>http://mysite.com/blog/assets/favicon.ico</code>.
* **twitter_handler**: Add your Twitter username without the @. It will be used for [Twitter Cards](https://dev.twitter.com/cards/overview){:target="_blank"}. The default card type for "Steve" is [Summary Card with Large Image](https://dev.twitter.com/cards/types/summary-large-image){:target="_blank"}.
* **analytics_code**: Add your Google Analytics Tracking ID. Example ID: *UA-XXXXXXX-2*.
* **disqus**: Add your website shortname from Disqus.

**Important Note:** Keep in mind that **name**, **job_title**, **twitter_handler** and some of the post specific variables are used as default meta data in some cases.

<!--more-->

##### Social Accounts
* **social_networks**: Here you can find the list of all the available social networks that you can currently use. Of course you can always add a new one by yourself or ask for it to be available in the next version of the theme. If you don't want a specific social network to be seen, just leave the url value empty or delete the line.

**Important:** Do not change the names of the social networks!

##### Modules Settings
One thing to remember - 1 is **on**, 0 is **off**.

* **show_categories**: If it is on and you've added categories in the post itself the categories will be visible. If it is off and you've added categories in the post they will be hidden. This option is helpful if you want to turn on/off categories for all your posts at once.
* **show_tags**: If it is on and you've added tags in the post itself the tags will be visible. If it is off and you've added tags in the post they will be hidden.  This option is helpful if you want to turn on/off tags for all your posts at once.
* **show_email**: If this is turned on and you've entered an email value in **email**, an email icon will appear next to your social media accounts and all your readers will be able to contact you.
* **show_rss**: If this is turned on, a new RSS button will appear in the sidebar next to your social media accounts.
* **show_comments**: If it is on and you've added <code>comments: true</code> in the post itself the comments will be visible. If it is off and you've added <code>comments: true</code> in the post the comments will be hidden. This option is helpful if you want to turn on/off comments for all your posts at once.
* **show_menu**: If it is on the main menu will be visible.
* **fixed_sidebar**: If it is on the sidebar will be fixed (sticky).

##### Defaults
* **defaults**: The only available option at the moment is whether to enable the comments automatically in the post or not. The default value is <code>true</code>.

##### Serving
These options are pretty important, so take a closer look. If you experience any problems with your paths you should check them here.

* **url**: Enter your domain! Example: <code>https://mysite.com</code>
* **baseurl**: The baseurl can remain empty if you’re not going to host your site in a subfolder. But if you want your site to be something like <code>htttp://mysite.com/blog</code> you should write down <code>/blog</code> here.

##### Includes

* **include**: Force the inclusion of the pages directory.

##### Outputting

* **permalink**: By default your links will look like this <code>http://mysite.com/categories/post-name.html</code>. If you want a different permalink check [Jekyll documentation](https://jekyllrb.com/docs/permalinks/){:target="_blank"}.
* **category_dir**: The default directory is <code>categories</code>, so for example if you go to random category index you will see something like this <code>http://mysite.com/categories/category-name/postname.html</code>.

##### Pagination
* **paginate**: You should enter a number that stands for the number of posts per page.
* **paginate_path**: The default path is <code>/page:num/</code>, so for example if you go to second page you will see something like this <code>http://mysite.com/page2/</code>.

**Important Note:** Pagination is currently working only on home page due to Jekyll limitations.

##### Conversion
* **markdown**: Choose your Markdown renderer. Different Markdown renderers supported by Jekyll sometimes have extra options available. I suggest to stick with the default.
* **excerpt_separator**: By default when you're writing a post, you should add <code>&lt;!--more--&gt;</code> to define excerpt. You have three options - to leave it as is, to change the tag or to completely remove it but in this case you'll always see the full content.

##### Assets Settings
* **sass**: Choose the path to all of yours SCSS partials and the compression method for the final file.

If you need extra help, just check out the [official Jekyll documentation](https://jekyllrb.com/docs/home/){:target="_blank"}.

### Additional Configuration

<dl>
	<dt>How to change your default theme color?</dt>
	<dd>Just go to <code>/assets/partials/_vars.scss</code> and change the color of the <code>$primary-color</code> variable.</dd>

	<dt>How Facebook knows which image to use for sharing?</dt>
	<dd>By default the script gets the first image in the post so take that in mind when you write a blog post.</dd>
</dl>

### Adding Post

The next thing after you are done with the configuration file is to add your first post. You will need to have at least basic knowledge of HTML or Markdown.

All you need to do is to create a new file with name <code>YYYY-MM-DD-my-first-post</code> and <code>.markdown</code> or <code>.md</code> extension. Create it in the <code>_posts</code> folder. By default the name of the file is composed by date and title but you can overwrite these in the post's front matter.

In the beginning of the every post you have a so called [front matter](https://jekyllrb.com/docs/frontmatter/){:target="_blank"} block which contains some data about the post. Here is the short description of the options.

**layout**: The post layout.

**date**: Exact date when the post is published. The date is actually pretty important and I suggest you never change it. Specific date helps Jekyll to order correctly all the posts. Also, the date is used to generate a unique ID, so Disqus can always get the right comments for the right post, even when you change the title.

**title**: Post's title.

**description**: Meta description used for better SEO.

**comments**: By default they are always <code>true</code>, but if you want to turn them off for a specific post just set this to <code>false</code>.

**category**: List the categories in which you want your post to appear.

**tags**: List your tags here.

### Adding Page

Adding page is even simpler than adding post. Just create a sub-folder to the pages directory and inside that sub-folder create index.md file. The folder name is your page name. Every folder must contain index file. Pages are also using front matter to add information to your page.

**layout**: The page layout.

**title**: Page's title.

**permalink**: This is important. If you do not enter the permalink, your url will be something like this <code>http://example.com/_pages/about</code>. Enter the permalink and get rid of <code>/_pages/</code> part. Do not forget the trailing slash!

That's it! Do not hesitate to ask if you have any questions. Also you can send me feature requests. There are some nice features that are planed for the upcoming versions. Happy blogging!

---

Markdown (or Textile), Liquid, HTML & CSS go in. Static sites come out ready for deployment.

#### Headings

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

#### Blockquote

> No more databases, comment moderation, or pesky updates to install—just your content.

#### Unordered List

* Jekyll
    * Nested Jekyll
    * Nested Ruby
* Ruby
* Markdown
* Liquid

#### Ordered List

1. Jekyll
    1. Nested Jekyll
    2. Nested Ruby
2. Ruby
3. Markdown
4. Liquid

#### Link

This is <a href="http://example.com/" title="Title">an example</a> inline link.

#### Paragraph w/ strong, em, etc.

These are just a few of the *available* **configuration** options. Many configuration options can <strike>either</strike> be specified as flags on the <abbr title="Command Line Tool">command line</abbr>, or alternatively (and more commonly) they can be specified in a _config.yml file at the root of the source directory. Jekyll will <a href="http://joro.me/" target="_blank">automatically use</a> the options from this file when run. For example, if you place the following lines in your _config.yml file.

#### Image
<figure class="aligncenter">
	<img src="https://images.unsplash.com/photo-1449452198679-05c7fd30f416?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&s=73181f1c6d56b933b30de2bfe21fdf3b" />
	<figcaption>Photo by <a href="https://unsplash.com/rmaedavis" target="_blank">Rachel Davis</a>.</figcaption>
</figure>

#### Video

<iframe width="560" height="315" src="" data-src="https://www.youtube.com/embed/iWowJBRMtpc" frameborder="0" allowfullscreen></iframe>

#### Default Code Block

    This is code blog.

#### Styled Code Block

{% highlight ruby linenos %}
#!/usr/bin/ruby
$LOAD_PATH << '.'
require "support"

class Decade
include Week
   no_of_yrs=10
   def no_of_months
      puts Week::FIRST_DAY
      number=10*12
      puts number
   end
end
d1=Decade.new
puts Week::FIRST_DAY
Week.weeks_in_month
Week.weeks_in_year
d1.no_of_months
{% endhighlight %}

#### Definition Lists

<dl>
    <dt>Definition Title</dt>
    <dd>Definition Description</dd>
</dl>

#### Paragraphs w/ Aligned Images

The Jekyll gem makes a jekyll executable available to you in your Terminal window. You can use this command in a number of ways.

<figure class="alignleft">
	<img width="250" src="https://images.unsplash.com/photo-1432821596592-e2c18b78144f?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&s=3f9c78df0edb464244bbabb04d1797d8" />
	<figcaption>Photo by <a href="https://unsplash.com/dustinlee" target="_blank">Dustin Lee</a>.</figcaption>
</figure>

This site aims to be a comprehensive guide to Jekyll. We’ll cover topics such as getting your site up and running, creating and managing your content, customizing the way your site works and looks, deploying to various environments, and give you some advice on participating in the future development of Jekyll itself.

Jekyll is a simple, blog-aware, static site generator. It takes a template directory containing raw text files in various formats, runs it through a converter (like Markdown) and our Liquid renderer, and spits out a complete, ready-to-publish static website suitable for serving with your favorite web server. Jekyll also happens to be the engine behind GitHub Pages, which means you can use Jekyll to host your project’s page, blog, or website from GitHub's servers for free.

<figure class="alignright">
	<img width="250" src="https://images.unsplash.com/photo-1442037025225-e1cffaa2dc23?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&s=7fe04b68b0cb123bf568c6951c14b177" />
	<figcaption>Photo by <a href="https://unsplash.com/lobostudiohamburg" target="_blank">LoboStudio Hamburg</a>.</figcaption>
</figure>

Throughout this guide there are a number of small-but-handy pieces of information that can make using Jekyll easier, more interesting, and less hazardous. Here's what to look out for.

If you come across anything along the way that we haven’t covered, or if you know of a tip you think others would find handy, please file an issue and we’ll see about including it in this guide.

The front matter is where Jekyll starts to get really cool. Any file that contains a YAML front matter block will be processed by Jekyll as a special file. The front matter must be the first thing in the file and must take the form of valid YAML set between triple-dashed lines.
