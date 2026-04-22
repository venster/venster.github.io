---
layout: post
title:  "First Post - Getting back to the Swing of Things"
date:   2026-04-21 13:46:41 -0700
categories: jekyll update
---
## Let's start...
Today I've decided to actually sit down and develop my skills again.  It has been 3 months since I've been laid off.  The market is hard right now and it always feels like I don't have enough to make it out there right now. That's why I've decided to try to develop my skills and make this blog to keep track of what I've done and keep myself accountable.  

## First step - Setting up to make a blog

Looking online, I saw I could make a [blog on Gitub using Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll). It has been a while since I've done any Ruby development, so I had to relearn about updating it and setting up [Bundler](https://bundler.io/).  

I remembered at my previous job, I was taught about [pyenv](https://github.com/pyenv/pyenv) to help keep the installation of different python versions clean, so I wondered if Ruby had something similar. I asked Gemini for help on this and it suggested [rbenv](https://github.com/rbenv/rbenv).  Didn't know pyenv had a Ruby equivalent, haha.

## Second Step - Setting up Jekyll and github action

After setting up the repo, I initiated the Jekyll project.  

```
jekyll new --skip-bundle .
``` 

Then put this line in the Gemfile as said in the tutorial.
```
gem "github-pages", "~> 232", group: :jekyll_plugins
```

Unfortunately this is where I hit my first error. After doing `bundle install`, apparently the `github-pages` gem could only work with `jekyll = 3.10.0` and it was currently using `jekyll ~> 4.4.1`.  According to Gemini, I could use Github Actions to fix this.  I never used Github Actions before, but it kinda reminded me of Jenkins. 

Following Gemini's instructions, I did these steps:
1. Create a folder `.github/workflows/`
2. Go to Github > Settings > Pages > Build and deployment > Source
3. Change the dropdown from "Deploy from a branch" to "GitHub Actions"
4. Let Github create the `jekyll.yml` file for me

And...... it wasn't deploying successfully. 

Looked in to the deployment logs and according to Gemini, the automatically generated `jekyll.yml` I created was using `ruby-version: '3.1'` when I actually had to use `ruby-version: '3.2'` 

Now it worked. Blog site is working!

## Using AI thoughts:  
When it comes to using AI, I'm one of those who support using AI as a tool, but to create actual content is a no-go. Using Gemini definitely made things a lot easier to go through than having to look through possibly outdated documents.  It even taught me about Github Actions, which I never heard of before in my life.  The only downfall for it is that it can get really.... stuck on track.  

I was using Gemini to help me install the [Beautiful-theme](https://github.com/daattali/beautiful-jekyll/tree/master/_layouts) and it was so adamant for me to add this setting to the config file 

```
about_me_sidebar: true
```

Nothing was different.  I kept asking what was wrong with my code, kinda ending up going in circles.  I decided to look in to the repository for the theme and I was pretty sure I didn't see that setting at all in it.   I told Gemini that it probably didn't exist, then it came out with a layout page saying to implement the sidebar.  Why in the world did Gemini want me to make this sidebar so badly?  I didn't even ask for it haha. AI can get weird sometimes.  Its good for guidance, but you gotta be cautious with it. 

## TO DOs
1. Finish the layout
2. Create an Archive Page for blog posts