
# Bash Shell Commands

## Get your Ip Address

There are better ways, but this works:

	$ ifconfig | grep inet 

## mv

Ever wanted to make a folder structure like Proj/Foo?

	$ mkdir Proj
	$ cd Proj
	$ mkdir Foo
	$ cd Foo

Well, that's annoying. Using -p makes it better. It's also undocumented in a lot of systems:

	$ mkdir -p Foo/Bar
	
Does it all in one go.

## find

You can do pretty much everything with *find* and a few pipes.

* Ignore all folders that start with .
* Ignore a given set of folders
* Exclude a pattern match

## sort
**Too many to list, trying to break it down well**

## du

**Too many to list, trying to break it down well**

## grep
**Too many to list, trying to break it down well**

Patern search with or without case sensitivity.

## ln
**Too many to list, trying to break it down well**

Make symbolic links.

## which

	$ which `python`
Tells you what command will be executed when you enter *python at the command line.


# Redirect errors to null

`$ find / -name "*foo*" -print 2>/dev/null`

The '2>/dev/null' redirects stderr to /dev/null so you don't have to see all the spammy errors that even sudo doesn't help with.

## How do I force a new line in MarkDown?

Just add an extra blank line.

Like this.

