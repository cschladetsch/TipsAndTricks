# Git Tricks and Tips
By [Christian](mailto:christian.schladetsch@gmailcom).
This is also [on githib](https://github.com/cschladetsch/TipsAndTricks).

I am not an expert at all. This is just where I am keeping some tips I've found useful.

You may want to start with reading from [someone who knows](https://github.com/git-tips/tips#show-helpful-guides-that-come-with-git).

## Basics
Just type these in every now and then:

	$ git help everyday
	$ git help -g

## Prettifying Log

There are simple ways to make it easier to visualise the status of a Git repo without resorting to tools like *SourceTree* or *GitKraken*.

Add to the follwing your *~/.bashrc*:

	git config --global alias.lg "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative"
	
	alias gl="git lg"
	
## Autocompletion of git commands and arguments

This does require you to install a script first, but it's painless:

1. **Get the required script add add to your home folder:**

	`curl https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash -o ~/.git-completion.bash`

1. **Invoke from your bash start-up:**

	`if [ -f ~/.git-completion.bash ]; then
	  . ~/.git-completion.bash
	fi`


## Showing Untracked files

	$ git clean -n
	
To then remove them:

	$ git clean -f 		// remove files
	$ git clean -fd 	// remove untracked directories
	$ git clean -fX 	// remove ignored files
	$ git clean -f -x 	// remove ignore and non-ignored files 
	
## Automated Tips

[Get Some](https://www.npmjs.com/package/git-tip) random git tips every time you open a shell.

### Usage

	$ git-tip [options]

Options

* **help**: Provides usage help (Shows the current page)
* **all**: Gives all the git tips <keyword> Gives the git tips consisting of the keyword
* **\<keyword\>**: Gives the git tips consisting of the ***keyword***

### Examples

	$ git-tip bypass
	 
	Bypass pre-commit and commit-msg githooks
	  => git commit --no-verify
 
 Or more generally:
 
	$ git-tip
