# notes for setting up git(hub)
begin the process on the github site.  once you have added your ssh public key and created the initial repository, you can clone it to your local device

## setup github
> add ssh key
- goto settings  ( select 'Settings' from icon menu in top right corner )
- select 'SSH and GPG keys'
- select 'New SSH key'
- Title: enter hostname and/or username
- Key: copy the entire text of the public key  ( cat ~/.ssh/id_rsa.pub )
- select 'Add SSH key'
- enter github password  ( if prompted )

> add repository
- go to repositories  ( select 'Your repositories' from icon menu in top right corner )
- select 'New'  ( green box in upper right corner )

	- repository name: dotfiles
	- description: optional
	- select radio button 'private'
	- select checkbox 'Initialize this repository with a README'
	- select 'Create repository'  ( green box near bottom of page )

- select 'Code'  ( green box in middle of screen )
- select 'Use SSH' if it says 'Clone with HTTPS'
- select clipboard icon to right of 'git@github.com' string
  ( you'll get a string like this:  git@github.com:myridonn/process.git )

## on your local device
> setup global variables
```sh
git config --global user.name myridonn
git config --global user.email myridonn@gmail.com
git config --global --list
```

> clone existing repository
```sh
cd ~/git
git clone git@github.com:myridonn/process.git
```

> to create a new repository
create and initialize directory
```sh
mkdir ~/dotfiles
cd ~/dotfiles
git init
```
create new file
```sh
touch .vimrc
git add .vimrc
git commit -m 'Initial revision'
```
push file to github
```sh
git remote add dotfiles git@github.com:myridonn/dotfiles.git
git push -u dotfiles master
```

this can be done all in one line

```sh
git add git.md ; git commit -m 'more' ; git push
```

```sh
-------------------------------------------------------------------------------
# https
git remote add dotfiles https://github.com/myridonn/dotfiles
git push -u dotfiles master

- or -

# ssh
git remote add dotfiles git@github.com:myridonn/dotfiles.git
git push -u dotfiles master
-------------------------------------------------------------------------------
```

git pull dotfiles master

# after you add rsa public key to github account  ( check, switch to ssh, check again )
git remote -v
git remote set-url dotfiles git@github.com:myridonn/dotfiles
git remote -v

# you should no longer be required to provide username/password for github acct
pit push dotfiles

The authenticity of host 'github.com (140.82.113.4)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'github.com,140.82.113.4' (RSA) to the list of known hosts.
Everything up-to-date

fedora% git push dotfiles
Everything up-to-date

# if you want to switch back to https:
git remote set-url dotfiles https://github.com/myridonn/dotfiles

-------------------------------------------------------------------------------
	procedure
-------------------------------------------------------------------------------

# after globals have been established and public key has been added to github
mkdir ~/dotfiles
cd !$
git remote add dotfiles git@github.com:myridonn/dotfiles.git
git remote -v
git pull dotfiles master

-------------------------------------------------------------------------------
	changes
-------------------------------------------------------------------------------

git add .
git commit -a
git push

-------------------------------------------------------------------------------
	other info
-------------------------------------------------------------------------------

https://guides.github.com/activities/hello-world/

-------------------------------------------------------------------------------
	installing
-------------------------------------------------------------------------------

	windows:	msysgit
			gitextensions

-------------------------------------------------------------------------------
