## Purpose
Host your static resume on github.

## Prerequisites
Before we start, its important that you have a resume written in markdown, since that will be required to follow along with this. If you need help in completing this task and getting your resume ready, you can check a good markdown tutorial here. It should be enough to get you started.

1. Install Git on your computer as it'll be required to work locally with Github repository. You can simply download it for your system here: https://git-scm.com/downloads
2. Install Jekyll on your computer as it'll be required as well. The steps on how to install for different operating systems are listed here: https://jekyllrb.com/docs/installation/.

## Instructions
1. First, make sure that you have a github account. If you don't follow the steps below to create one:
    1. Visit https://github.com.
    2. In the top right section of the page, you should see the option to 'Sign in' or 'Sign up'.
    3. Since you need a new account, click 'Sign up' and the webpage will lead to a section where you'll need to enter some information to create your account, including your email address, a new password and a username.
    4. In some cases, Github may also require you to verify your email address before anything else. If that happens, please follow the instructions provided by Github to verify your email address.
    5. Github may also ask your some more questions about yourself and what you'll be using github for etc. so please go through the steps to finish the signup process.
    6. Once you've completed all the steps, your account should be created and we can now move on. 
    7. For more information, check ......

3. Now that you have your github account, please visit https://github.com and log into your account.
4. Click the 'Create Repository' button 
5. For static site hosted on Github pages, the repository name should be {username from step 3.}.github.io
 ![Create Repo Demo](/resources/create_repo_github.gif "Logo Title Text 1")
6. Next you'll need to create a github project on your computer.
    1. Open up a terminal window and navigate to where you want to save this project.
    2. Run 'git init {repo_name_of_your_choice}
    3. cd {repo_name_of_your_choice}
    4. run 'jekyll new --skip-bundle .'
    5. For now, we'll sync everything with Git. So follow the steps below to do that or take a look at the demo recording below for a full overview
        1. `git add .`
        2. `git commit -m 'Initial GitHub pages site with Jekyll'`
        3. `git remote add origin https://github.com/{username}/{username.github.io}.git`
        4. `git push -u origin master`
        ![Git demo](/resources/create_repo_local.gif "Logo Title Text 1")



    6. This creates a bunch of directories and files for 'minima' jekyll template. Since we don't really need them and want to only do simple resume hosting, we can delete the extra stuff. So delete the _posts directory and delete the about.md file
    7. Remove 404.html
    6. Two updates required to the Gemfile in this directory
        1. First, comment out the line `gem "jekyll", "~> 4.2.1"` i.e. add `#` to the beginning of the line.
        2. Update the line starting with `gem "github-pages"` to `gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins`, where `GITHUB-PAGES-VERSION` is the latest version of the github pages gem, which at this time is `219`. You can find the latest version here: https://pages.github.com/versions/
        3. Add `gem "webrick"` under `group :jekyll_plugins do`
        3. Now save and close this file.
         ![Gem file update](/resources/gem_file_edit_final.gif "Logo Title Text 1")
    7. Update Index.md
        1. Remove everything thats in that file since we won't be using the template.
        2. Copy and paste your resume markdown in there
    8. Update _config.yaml
        1. You can update your page title, email address and such here.
        2. Change theme to jekyll-theme-slate

    9. Then `bundle install` and `bundle update` to make sure all the bundles are up to date
    9. Run `bundle exec jekyll serve`
7. To see the website hosted on Github
    1. `git add .` and `git commit -m "{commit_message}"`
    2. `git push`
    3. Give it a couple minutes to refresh, then visit `{username}.github.io` and your website should be there.


