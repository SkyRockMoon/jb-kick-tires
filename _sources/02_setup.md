(setup)=
# Setting up jupyter-book

Jupyter-book is a collection of complex tools that, in my opinion, perform a series of consecutive miracles every time you run them to generate a very professional looking output. I call the output a book, but there are lots of other things you could call it - website, paper, technical documentation, interactive notebook, etc.

The installation process described here is very windows 10 centric and may not be to everyone's taste. If you work on a linux machine you might be able to install jupyter-book in a [single command](https://jupyterbook.org/intro.html#install-jupyter-book)! In most cases sophisticated users should be able to recognize how many of these instructions apply generally to their system. For the uninitiated, this setup guide will take you from zero to jupyter-book hero. 

If you are truly new to the jupyter ecosystem take the [easy path](easy-path) and install Anaconda on your machine. This is a much easier way to get started than taking the [hard path](hard-path), and if you decide you like jupyter-book then you can always go back and follow the more advanced setup. The manual installation described on the [hard path](hard-path) provides a slightly more streamlined workflow when writing. Over the course of developing a book, it might be worth the investment of setting up streamlined workflow, but is unnecessary to just kick the tires. 

(easy-path)=
## Easy Path: Anaconda

The easy path describes how to get up and running with jupyter-book as quickly as possible. It will describe how to install one program that contains virtually everything that you need. Here is what to expect:

1. Install [Anaconda](install-anaconda)
1. Setup a [GitHub account](github-easy) 
1. Clone (download) and build a [sample book](clone-easy)
1. Optional: Install [VS Code](vscode-easy)

(install-anaconda)=
### Install Anaconda

``````{margin}
```{tip}
If you already have anaconda installed on your machine and need to upgrade python see this [thread](https://stackoverflow.com/questions/58568175/upgrade-to-python-3-8-using-conda/59348995).
```
``````

Anaconda is a python environment that tries to bundle everything you might need from the python ecosystem into a single easy to use windows installer. It includes jupyter-book, plus many other useful libraries. Jupyter-book requires python 3.8+, and as of mid-2020 Anaconda was shipping with python 3.8. Download the free personal edition of Anaconda [here](https://www.anaconda.com/products/individual) and follow the isntallation instructions.

(github-easy)=
### Setup Github
[GitHub](https://github.com) is a code repository hosting service. You can store your source code on GitHub, and they will host the website version of your book for free. GitHub is entirely optional. GitHub us used to kick the tires on jupyter-book because it is very easy to use.

If you don't have an account, you can [sign up](https://github.com/join) for one for free.

(clone-easy)=
### Clone the sample book
In this section you will clone (download) a sample book that you can play with to see if jupyter-book is a good fit for you. To accomplish this take the following steps:

1. Open the anaconda **prompt**. The anaconda navigator is the graphical user interface and is not what you want to be using.
1. Navigate to where you want to store the sample book on your machine. I store all my code projects in a folder called projects on my C drive, so I would navigate to that folder like this: `cd C:\projects`. Note that the next step will create a folder called `sample-book` so you don't need to create a dedicated directory to keep your projects folder clean.
1. Clone the sample book using git: `git clone https://github.com/SkyRockMoon/sample-book.git`
1. Navigate into your cloned directory with `cd sample-book`
1. Setup your environment with `conda env create -f environment.yml`
1. Build the book with `jupyter-book build book`
1. Watch the console for errors, if everything goes well it will give you a link to your book. Use the link to open the book in an internet browser. Alternatively, use windows file explorer to locate `book/_build/html/index.html` and open that file in your browser.  

(vscode-easy)=
### Optional: Install VS Code
[VS Code](https://code.visualstudio.com/) is an amazing, free, text editor (among other things) that can be used to edit the files in the sample-book. Visit the [downloads page](https://code.visualstudio.com/Download) and install it on your machine if you don't already have a similar tool installed on your machine that can be used for editing text files.

### Conclusion of the easy path
You have successfully installed everything you need to kick the tires on jupyter-book. If you decide you want slightly more powerful tooling, consider some or all of the instructions in the [hard path](hard-path). Until you are sure jupyter-book is right for you, I wouldn't bother spending the time adding bells and whistles to your setup. Next you will fully exercise your newly installed environment by [building/publishing](build-pub) a book two different ways.

(hard-path)=
## Hard Path: Manual Install
The [easy path](easy-path) is great for getting up and running quickly so you can kick the tires on jupyter-book. If you are certain jupyter-book is right for you, then you can gain some moderate workflow efficiency improvements by following some or all of the instructions here. 

Here is what you can expect to accomplish:

1. Install the [windows subsystem for linux](wsl). Basically this is a little linux machine installed inside windows. This is necessary because jupyter-book is a essentially a linux tool.
1. Install [VS Code](vs-code). VS Code is an *integrated development environment* that includes code editing and a command line all in one place. This is where you will do all your work.
1. Build [python3.8](python) from source code! It sounds scary, but it is actually really hard to mess up and better than the alternative.
1. Install and register for the collaboration tools [git and GitHub](git)
1. [Clone](clone) the mini-book repository onto your machine
1. Duplicate the mini-book python environment, and [build](build) the mini-book 🎉

(wsl)=
### Linux on windows
Jupyter-book is fundamentally a linux tool. Installation instructions for the Windows Subsystem for Linux (WSL) on Windows 10 are beyond the scope of this document and [is documented by Microsoft](https://docs.microsoft.com/en-us/windows/wsl/install-win10). I personally used [these instructions](https://superuser.com/questions/1271682/is-there-a-way-of-installing-ubuntu-windows-subsystem-for-linux-on-win10-v170/1272559#1272559), which assume some pre-existing knowledge of linux. 

```{attention}
These instructions assume that you install Ubuntu 18.04 as your linux distribution.
```

After installation, from a windows command prompt run `ubuntu1804.exe`. In my specific case I had to run `C:\Users\<user-name>\ubuntu1804.exe`, where `<user-name>` is my computer user name. 

#### Update your linux distribution
Make sure you update everything with an `sudo apt update` after logging into the WSL "machine" as everything will be out of date. This step will take a minute.

(vs-code)=
### Install VS Code
Authoring content with jupyter-book involves lots of typing (your content) and issuing the same command on the command line umpteen billion times. A modern interactive development environment (IDE) will make this process much less tedious. [VS Code](https://code.visualstudio.com/) is an amazing, and free, IDE that bridges the gap between the windows and linux world very effectively. Visit the [downloads page](https://code.visualstudio.com/Download) and install it on your machine. 

When VS code opens for the first time it expects you to tell it what folder to work out of. It does not matter what folder you use for the next few steps, any project folder will suffice. Later we will change the working folder.

```{note}
For the remainder of the setup process work out of VS Code. You can close your windows command prompt at this point.
```

### Make WSL/BASH default terminal in vscode
1. In VS code, make the terminal visible: View > Terminal, or use the (Ctrl + `) shortcut
2. From the dropdown in the terminal window, select 'Set default shell'
1. Select WSL/bash (C:\WINDOWS\System32\wsl.exe) as the default shell. If this option is not available see the note below.
1. Close and reopen the terminal. If all went well the drop down will now indicate 'wsl' as the shell. Try `bash --version` to verify you are in the bash terminal 

```{note}
If you have issues with this step, see [this document](https://medium.com/@janelgbrandon/a-guide-for-using-wsl-for-development-d135670313a6) for additional instructions.
```

#### Install oh-my-zsh
This step will make everything in the console look prettier, which in turn makes using the command line easier to use. 
- Install the z-shell, `apt install zsh`
- Install [oh-my-zsh](https://ohmyz.sh/), `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

Close, and then reopen the terminal to see your new oh-my-zsh.

#### Link a linux folder to a windows folder
Files inside your WSL machine are buried in a hard to remember location that you really should not be messing with. Create a link to a folder on your C drive to make the linux to windows things work better.

1. Move to your home directory `cd`
1. Create a folder named projects on your C drive `mkdir /mnt/c/projects`
1. Use your *windows* file explorer to verify that this step succeeded and you have a new folder named projects. If it failed check [this site](https://medium.com/@janelgbrandon/a-guide-for-using-wsl-for-development-d135670313a6) for detailed debugging details.
1. Create a link to this location with `ln -s /mnt/c/projects`, this will create a projects directory in your home drive
1. Test that your link works with `touch ~/projects/newfile.txt`
1. Again, use your *windows* file explorer to verify that newfile.txt was created in the projects folder
1. Clean up with `rm ~/projects/newfile.txt`

#### Install latex libraries
These libraries are used when building a pdf. Install them with this 'one-liner':

    sudo apt-get install texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended texlive-fonts-extra texlive-xetex latexmk

(python)=
### Build python 3.8 from source
Jupyter-book requires python 3.8+. When this document was written the usual way of installing python (`sudo apt install python3`) would install python 3.5.3, so you need to build python3.8 from source. Follow these steps:

1. Upgrade with `sudo apt update`, if you didn't do it earlier
1. Install packages needed to build python `sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev`
1. Move to a temporary directory, `cd /tmp` for example
1. Download the source code `wget https://www.python.org/ftp/python/3.8.7/Python-3.8.7.tgz`. Change 3.8.7 to the latest version as needed. See the [python downloads page](https://www.python.org/downloads/source/) for information on the latest version. When this document was written python3.9 was available for download, but jupyter-book is tested with python3.8 so that is the version I would use for now. This step will take a minute to complete.
1. Extract the archive you just downloaded with `tar -xf Python-3.8.7.tgz`
1. Switch to the source directory `cd Python-3.8.7`
1. Check the dependencies `./configure --enable-optimizations`
1. Find number of cores on your machine with `nproc`. In my case the result was 8, but adjust the next step to match with your machine
1. Build python 3.8 `make -j 8`, where `8` represents the number of cores your machine has
1. Install the binaries with `sudo make altinstall`
    ```{warning}
    If you don't use `altinstall` you will overwrite the default system python3 binary.
    ```
1. Check the version number of your install with `python3.8 --version`
1. You can now remove the source files from your tmp directory with 

    $ cd /tmp
    $ rm -fr Python-3.8.7 
    $ rm Python-3.8.7.tgz

Next a few tools that support the use of python need to be installed.

#### Install Pip
Much like `apt` is used for linux packages, Python has its own package manager `pip`. Install pip with `sudo -H apt install python3-pip`

#### Install virtualenv
A virtual environment allows you to install multiple version of the same library for different projects. 

```{note}
This might seem like overkill if you are just installing python for jupyter-book, but for anyone that uses python frequently a virtual environment will save your sanity! Plus it makes duplicating an environment trivial. For example it can automate the installation of an environment that matches with the environment that I used to write this mini-book.
```
Install the python virtual environment tool with `sudo pip3 install virtualenv`

(git)=
### Install Git and register with GitHub
Git is a popular version control system. When used in conjunction with GitHub, a popular code hosting platform, you will have access to some very powerful collaboration tools. Git is notorious for being user hostile, so we will use only the most basic functionality.

```{note}
Because of the complexity of git you can find all kinds of conflicting advice on the internet. If you want to learn how to use git (and actually understand what is happening) there are a couple of good tutorials out there. The [GitHub learning lab](https://lab.github.com/) uses a hands on approach to learning. The [bitbucket tutorials](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud) (a direct competitor of GitHub) are also a good reference source.
```

#### Install git
From the command line install git with `sudo apt install git`. We will use git in the next section to download the source code of this mini-book.

#### Register for a GitHub account
If you don't have an account, you can [sign up](https://github.com/join) for one for free. GitHub is certainly not your only option for code repository hosting, but it is used here because it is free and easy.

(clone)=
### Clone and build the mini book
In this section we will clone - or download - the source for the mini-book that you are reading so you can modify and then rebuild it later. Up to this point we have been working from an arbitrary working folder. In VS code use `file > open folder` to navigate to your project folder (C:\projects) you created earlier. Then clone the mini-book repository from my GitHub account to your local drive using `git clone https://github.com/SkyRockMoon/sample-book.git`.

Move into the cloned directory with `cd sample-book` and then view the directory contents with `ls -a`. You should see a listing of files and folders that includes:

- book: this is the source code for the book
- requirements.txt: this defines all the packages needed to exactly duplicate my python environment
- .gitignore: this helps git avoid tracking unnecessary files

All of the source code is located in the book directory, but before we build the book we need to install the python environment so you can build the mini-book using jupyter-book.

(build)=
### Build the mini-book

1. Create a virtual environment with `python3.8 -m venv sample-book-venv` 
1. Activate the virtual environment `source sample-book-venv/bin/activate`
    ```{note} 
    At this point your command prompt should change to indicate that you are inside the virtual environment. The command prompt should change from:
        $ sample-book

    To look like this once the virtual environment has been activated:
        $ (sample-book-venv) sample-book

    It is no longer necesary to denote a specific version of python. For example issue the command `python --version` and the version number should be 3.8.7. Also pip is actually pip3.
    ```
1. Ensure pip is up to date `pip install --upgrade pip`

1. Install jupyter-book (finally!) and all the other libraries that are needed to create and build the book: `pip install -r requirements.txt`. Get comfortable, this will take a minute or two.

1. Check the jupyter-book version `jupyter-book --version`. When this was written, jupyter-book was at 0.9.1.

    ```{tip}
    When you want to leave the kick-tires virtual environment issue the command `deactivate` and you will be returned to your regular command prompt. Jupyter-book is installed *inside* the virtual environment, so if you leave the virtual environment `jupyter-book --version` will throw a 'command not found' error. A `source sample-book-venv/bin/activate` will reactivate your virtual environment.
    ```

1. Build the book with `jupyter-book build book`. Wait for the console to show you the status of the build. You should expect to see something like this:
    
```md
The HTML pages are in book/_build/html.

===============================================================================

Finished generating HTML for book.
Your book's HTML pages are here:
    book/_build/html/
You can look at your book by opening this file in a browser:
    book/_build/html/index.html
Or paste this line directly into your browser bar:
    file:///mnt/c/projects/jb_kick_tires/book/_build/html/index.html

===============================================================================
```
1. From VS code ctrl + click on the link to open the book in your browser (your not using [chrome, right?!?!](https://www.mozilla.org/en-US/firefox/unfck/))

1. If you see the sample-book then congrats. You survived the entire install process! 🎉🥴

(gh-actions)=
### Host your website on GitHub

```{warning}
This section assumes that you have GitHub account. If you don't have an account, you can [sign up](https://github.com/join) for one for free.
```

```{tip}
If you didn't [clone](clone) the sample-book repository, or you are starting from scratch, follow [their instructions](https://docs.github.com/en/github/getting-started-with-github/create-a-repo) for creating a new repository.
```

Install the github pages importer tool to make publishing your book as a website a one command job:

```bash
pip install ghp-import
```

Then from your working directory deploy your book to a webpage with: 

```bash
ghp-import -n -p -f book/_build/html
```

This will move the files from book/_build/html to a branch called `gh-pages` and commit/push the branch. GitHub knows to look for a branch with that name, and will publish your book as a website at `https://<user-name>.github.io/<repo-name>`. Where `<user-name>` is your GitHub username, and `<repo-name>` is the name of the code repository that you are developing your book in.

(notebooks)=
### Notebooks
Jupyter-book is part of the jupyter ecosystem. The star at the center of the jupyter ecosystem is the jupyter notebook. A notebook is a computational tool that allows you to break a computation into a series of smaller cells. Each cell in a notebook can be executed individually. In addition to code you can write markdown in notebook cells to describe what the code is doing. This turns out to be such a powerful construct that you can write entire books in a jupyter notebook. Jupyter-book *simply* makes notebooks look presentable in web and book format.

To see what a jupyter notebook looks like:
1. Open a new terminal with the plus sign in the VS code terminal window
1. Activate the kick-tires virtual environment `source sample-book-venv/bin/activate`
1. Open jupyter notebook with `jupyter notebook --no-browser`
1. Follow the link provided in the console to open the jupyter notebook in a browser

The chapter on [authoring content](content) will delve into the use of jupyter notebook with jupyter-book. If you are unfamiliar with jupyter notebook there are some [useful tutorials](https://realpython.com/jupyter-notebook-introduction/#creating-a-notebook).

### Conclusion of the hard path
Congrats, completing the manual install is certainly an acomplishment. You have successfully installed everything you need to kick the tires on jupyter-book. Next you will fully exercise your newly installed environment by [building/publishing](build-pub) a book two different ways.  





