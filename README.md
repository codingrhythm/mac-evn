mac-evn
=======

Mac Development Environment Configuration

## Install XCode

## Install MySQL Server

## Install Virtual Env

#### Install Homebrew
```
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
```

#### Install Python via Homebrew
```
brew install python --with-brewed-openssl
```

#### Install Virtualenv
```
pip install virtualenv
```

#### Edit or add bashrc for current user
```
vim ~/.bashrc
```

with content
```shell
# pip should only run if there is a virtualenv currently activated
export PIP_REQUIRE_VIRTUALENV=true
# cache pip-installed packages to avoid re-downloading
export PIP_DOWNLOAD_CACHE=$HOME/.pip/cache
```

## Install MySQL GUI

## Install Github App