# notes for setting up git/github

setup global varaibles

```sh
git config --global user.name myridonn
git config --global user.email myridonn@gmail.com
git config --global --list
```

initialize local directory/repository

```sh
mkdir ~/dotfiles
cd ~/dotfiles
git init

touch .vimrc
git add .vimrc
git commit -m 'Initial revision'
```

this can be done all in one line

```sh
git add git.md ; git commit -m 'more' ; git push
```

## setup reposity on github before proceeding

- login to github
- go to repositories
- select 'New'  ( green box in upper right corner )
- repository name: diotfiles
- description: optional
- private
- select 'Create repository'  ( green box near bottom of page )

```sh
git remote add dotfiles git@github.com:myridonn/dotfiles.git
git push -u dotfiles master
```

-------------------------------------------------------------------------------

# https
git remote add dotfiles https://github.com/myridonn/dotfiles
git push -u dotfiles master

- or -

# ssh
git remote add dotfiles git@github.com:myridonn/dotfiles.git
git push -u dotfiles master

-------------------------------------------------------------------------------

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
