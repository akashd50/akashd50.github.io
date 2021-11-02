# Hosting your resume on Github Pages using Jekyll

## Purpose
The instructions below provide a guide on how to host your resume on Github Pages using a static-site generator like Jekyll.

## Prerequisites
Before you start, its important that you have the prerequisites listed below:
1. A resume written in markdown. This will be required to follow along with this. If you need help in getting your resume ready, you can check [a good markdown tutorial here](https://www.markdowntutorial.com/). It should be enough to get you started.
2. Install Git on your computer as it'll be required to work locally with Github repository. You can simply download it for your system here: https://git-scm.com/downloads.
3. Install Jekyll on your computer as it'll be required as well. The steps on how to install for different operating systems are listed here: https://jekyllrb.com/docs/installation/.

## Instructions
In the book, Modern Technical Writing, Andrew E. points out these advantages of having your content on version control systems. Git is the version control tool that was used while creating these instructions. Having your site hosted on a distributed version control makes it incredibly easy to track changes and make new updates. 

1. Create a Github account   
    1. If you already have a Github account, please skip this section. Otherwise, follow the steps below to create one:
    2. Visit https://github.com. 
    3. In the top right section of the page, you should see the option to 'Sign in' or 'Sign up'.
    4. Click 'Sign up' and the webpage will lead to a section where you'll need to enter some information to create your account, including your email address, a new password and a username.
    5. In some cases, Github may also require you to verify your email address before anything else. If that happens, please follow the instructions provided by Github to verify your email address.
    6. Github may also ask your some more questions about your interests and such. So, please go through the steps to finish the signup process.
    7. Once you've completed all the steps, your account should be created and we can now move on. 
    8. For more information, check [Github signup help page](https://docs.github.com/en/get-started/signing-up-for-github/signing-up-for-a-new-github-account).

2. Create a Github repository
    1. Visit [Github](https://github.com) and log into your account.
    2. Click the 'Create Repository' button. 
    3. For a static-site hosted on Github pages, the repository name should be `{your username}.github.io`. You can follow the demo below to see the full process.
    ![Create Repo Demo](/resources/create_repo_github.gif)

3. Create local Git repository and initialize Jekyll project   
Andrew E. also talks about static websites and the advantages they provide when it comes to hosting content like product documentation or in our case, a resume, which doesn't require any dynamic content. What makes static sites so good is the fact that they don't need any server side code, no dependencies and no dynamically generated content. This makes them fast and pretty much crash resistant. Jekyll is the static-site generator which we use in conjunction with Github Pages for this project. It uses markdown file format and generates static webpage from that. Its light-weight and readable even without being on the webpage so its easy to transfer.
 
    1. On your computer, open up a terminal window and navigate to where you want to save this project.
    2. Then run the following commands:
        1. `git init {repo_name_of_your_choice}`
        2. `cd {repo_name_of_your_choice}`
        3. `jekyll new --skip-bundle .`
    3. Next, sync your local Git directory with the Github repository you created earlier:
        1. `git add .`
        2. `git commit -m "Initial Setup"`
        3. `git remote add origin https://github.com/{your_username}/{your_username}.github.io.git`
        4. `git push -u origin master`
        ![Git demo](/resources/create_repo_local.gif)

4. Update Jekyll files with your own information
    1. Jekyll, by default uses a template called `minima` and creates a bunch of extra files that you won't need in the beginning, so lets clean that up. 
    2. Delete the `_posts` directory, `about.md` file and, `404.html`.
    3. Update `Gemfile`:
        1. Comment out the line `gem "jekyll", "~> 4.2.1"` i.e. add `#` to the beginning of the line.
        2. Update the line starting with `gem "github-pages"` to `gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins`, where `GITHUB-PAGES-VERSION` is the latest version of the github pages gem, which at this time is `219`. You can find the latest version here: https://pages.github.com/versions/
        3. Add `gem "webrick"` under `group :jekyll_plugins do`
        4. Save and close the file.  
        5. If you need clarification, follow the demo below.
            ![Gem file update](/resources/gem_file_edit_final.gif "Logo Title Text 1")
    4. Update `index.md`:
        1. Remove everything that's in the file since we won't be using the template.
        2. Copy and paste your resume markdown here.   
        This markdown content will be whats shown on the webpage. Now you can tell how easy it'll be to update it if you ever need to change anything in the future. You'll simply need to update this one file, commit and push your changes and within a few minutes your website will be update. This is exactly what Andrew E. meant by the convenience of using static-site generator like Jekyll to host your website.

    5. Update `_config.yaml`:
        1. Update your page title, email address and such here.
        2. Update the line that starts with `theme` to `theme: jekyll-theme-slate`.   
        Jekyll comes with a bunch of pre-loaded themes which you can apply to your website with a few clicks. You'll see how to do that in _Section 7_ of these instructions.

5. View website locally
    1. Run the following commands:
        1. `bundle install`
        2. `bundle update`
        3. `bundle exec jekyll serve`
    2. Visit http://127.0.0.1:4000/.

6. View website on Github
    1. Commit and push your changes to Github. Run the following commands:
        1. `git add .` 
        2. `git commit -m "{commit_message}"`
        3. `git push`
    2. Visit `{your_username}.github.io` and your website should be there.

7. Changing the website theme
    1. Navigate to your Github repository.
    2. Click on `Settings` from the top menu bar.
    3. Click on `Pages`, from the left menu bar.
    4. Click on the button titled `Change Theme`
    5. You will be navigated to the themes page, where you can scroll through different themes and select a new one for your webpage.
    6. The demo below showcases this:
    ![Change theme](/resources/change_theme.gif)

8. More resources:
    * [Modern Technical Writing: An Introduction to Software Documentation](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS) by Andrew Etter.
    * Getting started with Markdown - [Markdown Tutorial](https://www.markdowntutorial.com/).
    * Getting started with Jekyll - [Jekyll Installation](https://jekyllrb.com/docs/installation/windows/).

## Authors and Acknoweldgements
* Etter, Andrew. Modern Technical Writing, 2016.

Also thanks to my group members: 
* 

## FAQs
1. Why is hosting information using markdown to host with Jekyll better than simply hosting html files?   
Jekyll provides a lot of built-in templates for creating such static websites quick and easy. Since the web-content is written in markdown, its easier to move this to a different source and its readable on its own, even without a markdown viewer. On the other hand, writing in html can be quite tedious and there's a lot of special formatting and tags you need to remember, which makes it inconvenient.

2. Why is my resume theme not updating?   
After your select a theme through the Github's theme selector as shown above in the instructions, sometimes it may take a couple minutes for the page to update. Simply close and re-open the webpage, or just try reloading the page after a couple of minutes.
