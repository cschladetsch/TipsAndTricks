# Running two copies of Unity 
...on two different projects at the same time.

This is a bit involved, but really it's very simple. Just follow these steps till someone makes a script to do it all for you... ;)

Make multiple identical instances of your local Unity app install:

* Copy /Applications/Unity to:
	* /Applications/Unity-A
	* /Applications/Unity-B
	* ...
	* /Applications/Unity-N

For how many different projects you want open at once.

## A common script for each project
Make a shell called 'edit' in the Unity/ folder of each project:

	#!/bin/sh
	open /Applications/Unity-$1/Unity.app --args -logFile ./log.out -projectPath `pwd`

# The final touch

Make one top-level script called 'spawn' like so:

	# $1 is folder name containing the Unity project
	# $2 is the version of unity to use
	cd $1/Unity && ./edit $2

Then say you have two projects: Client and another Server. For a networking test for example.

Your folder structure would look like:

* Projects/Client/Unity
* Projects/Server/Unity

You also have three shell scripts: the spawn script in both Client/Unity and in Server/Unity. These scripts are identical.

Now put spawn in Projects.

# Running both projects at once

From the Projects folder, type:

	$ ./edit Client A
	$ ./edit Server B

And you will have two instances of Unity3d, editing two different projects at the same time, and using different log files.

# COnclusion

It takes a little setting up:

1. Make multiple copies of Unity in
	2. /Applications/Unity-A
	3. /Applications/Unity-B
	4. etc...

1. Copy the spawn script to each Unity/ project folder
2. Copy the edit script to the parent folder for all your sub-projects
3. Edit the projects by typing './edit Client A' or './edit Client B'


Ask [me](mailto: christian.schladetsch@gmail.com) me if any questions.

