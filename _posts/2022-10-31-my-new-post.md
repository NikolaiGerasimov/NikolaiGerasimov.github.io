---
layout: post
title: [WORK IN PROGRESS]How to get started with Chirpy Jekyll theme for your GitHub site 
date: 2022-10-31 17:30 +0100
category: [Coding]
tags: [Jekyll, GitHub]
---

## Useful links:
- [YouTube -  Meet Jekyll, The Static Site Generator - A Guide by Techno Tim](https://www.youtube.com/watch?v=F8iOU1ci19Q) - Note that the video was uploaded in May 2022, some of the steps that he used did not work for me (this could be due to upgrades in Jekyll or due to differences in our software setup))
- [GitHub](https://github.com/)
- [GitHub Desktop](https://desktop.github.com/)
- [Jekyll](https://jekyllrb.com/)
- [Jekyll Compose](https://github.com/jekyll/jekyll-compose)
- [Jekyll Troubleshooting](https://jekyllrb.com/docs/troubleshooting/)
- [Chirpy Theme - GitHub](https://github.com/cotes2020/jekyll-theme-chirpy)
- [Chirpy Theme - Guide](https://chirpy.cotes.page/)

## Prerequists

- [GitHub](https://github.com/) account
    - The GitHub account will be used for both version control and for hosting your website
- Once you have a GitHub account the next step is to complete the Jekyll setup steps as described [here](https://jekyllrb.com/docs/installation/macos/). The steps are repeated below:
    - Install Homebrew (if you don't already have it) by typing the following into your terminal:
        ```terminal
        /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
        ```
    - Now that you have Homebrew installed you can use it to install chruby and ruby-install, by typing the following into your terminal:
        ```terminal
        brew install chruby ruby-install xz
        ```
    - Next, install the latest version of Ruby, by typing the following into the terminal (this step took around 5 minutes to complete for me):
        ```terminal
        ruby-install ruby
        ```
    - Configure your shell to automatically use chruby, by entering the following three lines into your terminal:
        ```terminal
        echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
        echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
        echo "chruby ruby-3.1.2" >> ~/.zshrc # run 'chruby' to see actual version
        ```
    - Quite and relaunch the terminal
    - To check that everything is working type, you should show 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a)' or a newer version.
        ```terminal
        ruby -v
        ```

- Follow [these](https://chirpy.cotes.page/posts/getting-started/#option-1-using-the-chirpy-starter) steps to get started with the Chirpy Starter folder (by creating a new repository from chirpy-starter)
- Name the new repository 'yourgithubusername/yourgithubusername.github.io'
- NAvigate to your new repository and go to Settings -> Pages -> Build and deployment. Set Source as 'GitHub Actions'
- Download a local copy of the repository (I use GitHub desktop)
- Navigate to the location of the repository using your terminal

## Troubleshooting
- Navigate to (it should be located in  Macintosh HD/yourusername/.zshrc) your .zshrc file and check that it contains the following (it may also contain other lines of code, that's fine):
```
source /usr/local/opt/chruby/share/chruby/chruby.sh
source /usr/local/opt/chruby/share/chruby/auto.sh
chruby ruby-3.1.2
```
If it does not, then add these lines to the file and save.

- Check your Gemfile and gem environment for common problems by running the following code in the terminal whilst navigated to your Jekyrll folder. If it tells you that you have issues, try to resolve them.
```
bundle doctor
```