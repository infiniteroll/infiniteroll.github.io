---
layout: post
title:  Jekyll via docker
#date:   2015-11-14 16:52:07
categories: container
tags: container docker jekyll github-pages

---

Jekyll is a simple, blog-aware, static site generator. It takes a template directory containing raw text files in various formats, runs it through a converter (like Markdown) and the Liquid renderer, and spits out a complete, ready-to-publish static website suitable for serving with our favorite web server.


I always preferred **github** for hosting any website which does not include backend operations. Getting a _**website**.github.io_ is pretty simple. Create a new organization under the name of preferred subdomain and create a repository named _**subdomain**.github.io_.


Back to the point. Installing the **github-pages** Gem without any dependency issues is always a painful task. We can use the docker concept to easily get the jekyll installation.

Got to the dirctory of your Jekyll website and run

`sudo docker run --rm -v "$PWD:/src" grahamc/jekyll build`

this will create your website in the \_site directory


For more ease of use, you use can set alias


`alias jekyll='sudo docker run --rm -v "$PWD:/src" -p 4000:4000 grahamc/jekyll'`

Now you can use the **jekyll** command to run all normal tasks like _build_, _serve_ etc...
