---
layout: post
title: How to get started with Chirpy Jekyll theme for your GitHub site 
date: 2022-10-31 17:30 +0100
category: [Coding]
tags: [Jekyll, GitHub]
---

## Useful links

- [YouTube -  Meet Jekyll, The Static Site Generator - A Guide by Techno Tim](https://www.youtube.com/watch?v=F8iOU1ci19Q) - Note that the video was uploaded in May 2022, some of the steps that he used did not work for me (this could be due to upgrades in Jekyll or due to differences in our software setup).
- [GitHub](https://github.com/)
- [Jekyll](https://jekyllrb.com/)
- [Jekyll Compose](https://github.com/jekyll/jekyll-compose) - Used to automatically generate templates for new posts, not requried, but useful.
- [Jekyll Troubleshooting](https://jekyllrb.com/docs/troubleshooting/)
- [Chirpy Theme - GitHub](https://github.com/cotes2020/jekyll-theme-chirpy)
- [Chirpy Theme - Guide](https://chirpy.cotes.page/)

## Hardware and OS

These steps were completed on macOS Version 12.6.1 running on a MacBook Pro Early 2015. If they do not work for you, feel free to get in touch and I may be able to provide assistance.

## Installation process

1. If you don't already have one, open a (free) [**GitHub**](https://github.com/) account. GitHub will be used both for version control and for hosting your website.
2. The next steps are related to getting **Jekyll** up and running. They are based on the Jekyll documentation which can be found [here](https://jekyllrb.com/docs/installation/macos/). The steps are repeated below (with some additional explanations).
    - Install Homebrew (if you don't already have it) by typing the following into your terminal:

        ```terminal
        /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
        ```

    - Use Homebtew to install chruby and ruby-install, by typing the following into your terminal:

        ```terminal
        brew install chruby ruby-install xz
        ```

    - Install Ruby, by typing the following into the terminal (don't be suprised if this step takes some time complete):

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
    - To check that everything is working type the following into your terminal. It should output 'ruby 3.1.2p20 (2022-04-12 revision 4491bb740a)' or a newer version.

        ```terminal
        ruby -v
        ```

3. Now that Jekyll is installed, you can start to work with the **Chirpy** template. The following steps are based on the documentation on the Chirpy website, which can be found [here](https://chirpy.cotes.page/posts/getting-started/#option-1-using-the-chirpy-starter).
    - First clone the Chirpy Starter repository by clicking [here](https://github.com/cotes2020/chirpy-starter/generate). The 'Repository name' should be set as yourusername.github.io:
        ![Cloning the GitHub Chirpy Starter repository](/assets/github-newrepo.png)

    - Navigate to your new repository and go to Settings -> Pages -> Build and deployment. Set Source as 'GitHub Actions':
    ![Setting repository 'Build and deployment' settings](/assets/github-pages.png)

4. You now have a copy of the Chirpy template in your GitHub account. The next step is to sync it down to your computer so that you can personalise the template. To do this you need to make sure that you have **Git** installed and configured. If you already use Git, then you can skip the next few steps.

    - Install git by typing the following into your terminal:

        ```terminal
        brew install git
        ```

    - Set your git username (note that this does not have to be your GitHub account user name, although it can be if you want). Git uses a username to associate commits with an identity.

        ```terminal
        git config --global user.name 'firstName secondName'
        ```

        To check that the username has been set correctly:

        ```terminal
        git config --global user.name
        ```

    - Set your commit email address:

        ```terminal
        git config --global user.email 'youremail@address.com'
        ```

        To check that it has been set correctly:

        ```terminal
        git config --global user.email
        ```

    - Cache your GitHub credentials in Git (i.e. link Git to GitHub). Type the following in your terminal and follow the promts:

        ```terminal
        gh auth login
        ```

5.

## Troubleshooting

- Navigate to your .zshrc file (it should be located in 'Macintosh HD/yourusername/.zshrc') and check that it contains the following (it may also contain other lines of code, that's fine):

```text
source /usr/local/opt/chruby/share/chruby/chruby.sh
source /usr/local/opt/chruby/share/chruby/auto.sh
chruby ruby-3.1.2
```

If it does not, then add these lines to the file and save.

- Check your Gemfile and gem environment for common problems by running the following code in the terminal whilst navigated to your Jekyrll folder. If it tells you that you have issues, try to resolve them.

```terminal
bundle doctor
```
