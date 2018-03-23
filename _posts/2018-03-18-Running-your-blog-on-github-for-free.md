---
title:  HOWTO run your blog on github for free
description: Run your blog for free on github using github pages, cloudflare & disqus
---

I have been meaning to do this for a long time. I used to run my blog on a WordPress instance in bluehost.com and it was painful to keep the wordpress site up to date and I finally gave up and stopped blogging altogether. I am now back online using github pages to blog and what follows is a quick howto on getting you up and running on github pages. And the whole setup is completely free.

[Github Pages](https://pages.github.com/){:target=_blank} allows you to host a static site directly from your github repository. It uses the [Jekyll](https://jekyllrb.com/){:target="_blamk"} static website generator.

Before we get started, you will need the following pre requisites:

 * [Docker community edition](https://www.docker.com/community-edition#/download){:target="_blank"} for your platform. We will use docker to run Jekyll locally when you are authoring a new blog post or adding pages to your site.
 * [Free disqus account](https://disqus.com/home/explore/){:target="_blank"}. You will need a disqus account if you want the option for people to leave comments on your blog posts.

Start with a new repository  in your github account with the same name as your blog url, for eg., mine is [chandraonline.github.io](https://github.com/chandraonline/chandraonline.github.io){:target="_blank"}. Your repository name should be your your-username.github.io.

Copy over the files from the [Scaffold Repository](https://github.com/chandraonline/scaffold.github.io){:target="_blank"} to your repository to get started with your own blog. You can either clone the scaffold directory and copy over the files or download the zip file from github. 

## Setting up  disqus comments

Head over to disqus.com and create a new site. You will find [install instructions](https://disqus.com/admin/install/platforms/jekyll){:target="_blank"} for jekyll which you can follow to get the universal embed code. You should then copy the embed code in _includes/comments.html and change the disqus site name in _layouts/default.html.

## Configuring your blog

You can update _config.yml to configure the blog title, author etc.

To test the jekyll site, simply run :

```
docker-compose up
```

You should be able to go to [http://0.0.0.0:4000](http://0.0.0.0:4000){:target="_blank"} and test your blog locally.

When you make changes to your posts or add new posts , it will show up in the local site automagically. If you are not seeing changes in the local site (for eg when you do changes to _config.yml, simply remove all files under _site/ and restart with the docker-compose up.

Once you are satisfied with the changes , you can push the changes to github.com and it will automatically build the jekyll site and make it available at your-user-name.github.io.

