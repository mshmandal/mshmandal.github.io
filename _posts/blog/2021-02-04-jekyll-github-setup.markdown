---
layout: post
title:  "How to set up your GitHub page with Jekyll"
date:   2021-02-04 00:23:23 +0900
categories: jekyll github
permalink: "/:categories/:title/"
---

GitHub pages are nice very easy to build and easy to handle with. You can serve your repository, project page as like webpage. For this, GitHub takes any markdown or html file and serves as individual pages. More on that details later. First let us move forward and make our first GitHub page. 


>We will use Jekyll to setup up our *username.github.io*

### Step 1 : Create a new repository
To be able to use a GitHub page which will be your default webpage you need to make a repository which should be named exactly as * username.github.io* . Here, you need to replace “username’ with your GitHub “username”. This is mandatory step.
So, go ahead a create a new repository named * username.github.io *  and do not create with ReadMe file or gitignore. You can set them up later. 

### Step 2 : Download Jekyll for Windows/Linux
As I am using Windows 10 64bit so, here I will be only talking about installing steps for Windows 10 64bit.
Jekyll have an excellent installation guide [here]( https://jekyllrb.com/docs/installation/windows/). Have a look at them, and then go ahead to the [download page]( https://rubyinstaller.org/downloads/).
As per [Jekyll documentation](https://jekyllrb.com/docs/installation/windows/) the installation will be four steps:

1.	Download and install *Ruby+Devkit*
2.	Run the `ridk install`
3.	Go to directory where you want to install and run `gem install jekyll bundler`
4.	Check your installation, `jekyll -v`

### Step 3 : Installing your static blog/webpage
So, if your installation was successful then let’s move ahead. I like to separate my GitHub repositories in a separate folder in my desktop. So, through command prompt I have already navigated into my main folder. There, I will clone my repository using `git clone HTTPS-url-of-your-repository`. So, git will clone the repository to your local machine. Now `cd` into the folder *username.github.io*

Next setting up your first blog will be consisting of four steps, again which is very simple and already provided with details in [Jekyll documentation]( https://jekyllrb.com/docs/). Simply they are:
1.	Install Jekyll and bundler: `gem install jekyll bundler`
2.	Create your blog: `jekyll new .` 
3.	Now serve the site locally: `bundle exec jekyll serve`
4.	Check it at http://localhost:4000 in your web browser.

Note: On the second step, if you want to create a site name ‘My Blog’, then you need to type `Jekyll new MyBlog`, so the third argument is the name of your site. But here, we want to create our site on the root directory. You can do that, and still be able to serve it. But it for technical issues I will use root. This step is helpful, when you want to create your posts using RStudio and publish them. 

### Step 4 : Basic setup of your site
If you followed along successfully you can see your site with some deafults. Therefore, you may want to change some of it,
for example site title, description etc. So, go to the directory on your computer where your site folder are
then open the `_config.yml` file. Read the file description. Now change the the tile, description, email etc to what you would like. 
And finally save it. Have a look at your site locally.

Then go ahead to the `_posts` folder and edit the deafult post, what you would like to post for the first time. If you want to create more posts, just copy and paste the file, rename the filename, write another awesome post about something you 
always wanted to write. At this point many things might be confusing but remember this is just starting point. 

And you want to learn more, there are many awesome tutorials and documentation about jekyll, search for it. 
> Here is an awesome youtube playlist [Giraffe Academy](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB)


### Step 5 : Pusing changes to Github 

Now push changes to GitHub repository.
```
git add .
git commit -m 'Add site'
git push
```
Go to your repository settings and under GitHub pages choose source `master` and `root` and save. Your site will be available at
username.github.io in few minutes. 

#### Here is a list for advanced setup for GitHub and Jekyll:
1.	GitHub has an excellent resources about setting up `Jekyll` and version management with `bundle` [here]( https://docs.github.com/en/github/working-with-github-pages/creating-a-github-pages-site-with-jekyll)
2.	Dependency versions on GitHub Pages: [Dependencies](https://pages.github.com/versions/)
3.	Ruby Gems: [Jekyll](https://rubygems.org/gems/jekyll)
4.	A useful tutorial on how to setup `bundler` with `Jekyll`: [bundler jekyll](https://jekyllrb.com/tutorials/using-jekyll-with-bundler/)
5.	Jekyll [setup](https://jekyllrb.com/docs/step-by-step/01-setup/) on your computer
