## Purpose
How to host your static resume on github?

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
6. Next you'll need to create a github project on your computer.
    1. Open up a terminal window and navigate to where you want to save this project.
    2. Run 'git init {repo_name_of_your_choice}
    3. cd {repo_name_of_your_choice}
    4. run 'jekyll new --skip-bundle .'
    5. This creates a bunch of directories and files for 'minima' jekyll template. Since we don't really need them and want to only do simple resume hosting, we can delete the extra stuff. So delete the _posts directory and delete the about.md file
    6. Update _config.yaml, 
