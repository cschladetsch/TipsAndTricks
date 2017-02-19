# Git Tricks and Tips
By [Christian](mailto:christian.schladetsch@gmailcom).
This is also [on githib](https://github.com/cschladetsch/TipsAndTricks).

I am not an expert at all. This is just where I am keeping some tips I've found useful.

You may want to start with reading from [someone who knows](https://github.com/git-tips/tips#show-helpful-guides-that-come-with-git).

## Reset origin from local

So, you've done some work and pushed to remote and all good. Then you do some more work and screw everything up - but you already pushed the changes.

What to do?

There are many ways to deal with this. My favorite is to just get the local state back to where you want it to be (ie, before you screwed up and pushed the bad changes). Then just:

	git push -f origin [branch-name]
	
Ths will force your current branch over the remote branch.

Use with care: I use this only when I screw up, and don't want to muck about with reverting commits etc.

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
