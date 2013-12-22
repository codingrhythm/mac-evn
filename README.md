mac-evn
=======

Django Development Environment Configuration on Mac OSX

## Install XCode

## Install Homebrew
You may need to keep XCode open while installing Homebrew to accept the agreement.

```
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
```

## Install Python via Homebrew
```
brew install python --with-brewed-openssl
```


## Install MySQL Server
Download and install from http://dev.mysql.com/downloads/mysql/

## Install PostgreSQL
```
brew install postgresql
```

To make it auto start on login, you have to run
```
ln -sfv /usr/local/opt/postgresql/*.plist ~/Library/LaunchAgents
```

Download and install PGAdmin from
```
http://www.pgadmin.org/
```

Start postgreSQL server
```
pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start
```

Stop postgreSQL server
```
pg_ctl -D /usr/local/var/postgres stop -s -m fast
```

Update login method in
```
vim /usr/local/var/postgres/pg_hba.conf
```

## Install Virtual Env

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

create .bash_profile
```
vim ~/.bash_profile
```
with following contents
```bash
PATH="/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin:/usr/local/mysql/bin/:/usr/local/Cellar/postgresql/9.3.2/bin/:$PATH"
export PATH

[[ -s ~/.bashrc ]] && source ~/.bashrc
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

just type ```deactivate``` to deactivate current envrionment

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
psycopg2
```

install packages
```
pip install -r pip_packages
```

## Install MySQL GUI

Download from http://dev.mysql.com/downloads/tools/workbench/

## Install Github App

## Install CocoaPods

```
sudo gem install cocoapods
```
