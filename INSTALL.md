# Install log

## Try 4 (conda alternative aka 'easy way')

conda env create -f environment.yml


## Try 3  (this worked, aka 'hard way')

- [Build python 3.8+ from source(]https://linuxize.com/post/how-to-install-python-3-8-on-ubuntu-18-04/)
    1. Upgrade: `sudo apt update`
    1. Install packages needed to build python`sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev`
    1. Download source code `wget https://www.python.org/ftp/python/3.8.7/Python-3.8.7.tgz`. Change 3.8.7 to the latest version as needed (two places in url!). See the [python downoads page](https://www.python.org/downloads/source/) for the latest
    1. extract archive `tar -xf Python-3.8.7.tgz`
    1. switch to source directory `cd Python-3.8.7`
    1. Check dependencies `./configure --enable-optimizations`
    1. Find number of cores on my machine `nproc` - result was:
    1. Build python 3.8 `make -j 8`
    1. Install binaries `sudo make altinstall`
    1. Check the version number `python3.8 --version`

- Create venv `python3.8 -m venv kick_tires_38`

- Start venv `. kick_tires_38/bin/activate

- Check python version again `python` (should see 3.8.7)

- Ensure pip is up to date `pip install --upgrade pip`

- Install jupyter book: `pip install -U jupyter-book`. Get comfortable, this will take a while. `-U` tells pip to update all packages to the latest.

- Check jupyter-book version `jupyter-book --version`. When written, jupyter-book was at 0.9.1

1. Write requirements to a text file in case you need them later: `pip freeze > requirements.txt`

1. Install latex libraries for generating PDFs `sudo apt-get install texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended texlive-fonts-extra texlive-xetex latexmk`

## Try 2 (python 3.8 would not install)

1. Upgrade: `sudo apt update`
1. deadsnakes PPA did not work for me

## Try 1 (didn't work, error executing main.py)

1. On WSL, navigate to desired project directory, and create a python 3 virtual environment" `python3 -m venv kick_tires`.
1. Then install jupyter book: `pip install -U jupyter-book`. Get comfortable, this will take a while.
1. Write requirements to a text file in case you need them later: `pip freeze > requirements.txt`