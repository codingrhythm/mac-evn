mac-evn
=======

Mac Development Environment Configuration

## Install XCode

## Install MySQL Server
Download and install from http://dev.mysql.com/downloads/mysql/

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
```bash
# pip should only run if there is a virtualenv currently activated
export PIP_REQUIRE_VIRTUALENV=true
# cache pip-installed packages to avoid re-downloading
export PIP_DOWNLOAD_CACHE=$HOME/.pip/cache
```

reload bash environment
```
. ~/.bash_profile
```

#### Restricting pip to virtual environments

Add the following to ```~./bashrc```
```bash
syspip(){
   PIP_REQUIRE_VIRTUALENV="" pip "$@"
}
```

If in the future we want to upgrade our global packages, the above function enables us to do so via:
```
syspip install --upgrade pip setuptools virtualenv
```

#### Test Virtual Evnrionments

```
mkdir ~/Projects
```

```
cd ~/Projects
```

```
virtualenv test
```

```
cd test
```

activate it
```
. bin/activate
```

create file pip_packages with following content
```
distribute
Django
MySQL-python
PIL
django-compressor
python-memcached
pyOpenSSL
boto
requests
humanize
```

## Install MySQL GUI

Download from http://dev.mysql.com/downloads/tools/workbench/

## Install Github App